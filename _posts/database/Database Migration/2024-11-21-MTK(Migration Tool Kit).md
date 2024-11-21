---
title: "MTK(Migration Tool Kit)n"
description: "MTK(Migration Tool Kit)"
date: 2024-11-21
categories: [ Database, Database Migration ]
tags: [ Database, Database Migration ]
---

# ***Oracle → EDB PostgreSQL Conversion***

### ***테스트 환경***

- Oracle 11g Express Edition
- EDB PostgreSQL 16.4.0
- migration toolkit 55.6.1

### ***Oracle 스키마, 테이블, 프로시저, 트리거 생성***

```sql
create user test_schema identified by 1234;
drop user test_schema cascade;

grant connect to test_schema;
grant create table to test_schema;
grant create trigger to test_schema;
grant create procedure to test_schema;
grant unlimited tablespace to test_schema;
```
> 오라클 11g는 Multitenant Architecture를 지원하지 않으므로 CDB(Container Database) 또는 PDB(Pluggable Database) 개념이 없다. 

### ***toolkit.propertries 파일 속성 변경***

```yml
SRC_DB_URL=jdbc:oracle:thin:@localhost:1521:xe  # sid 일 경우 
jdbc:oracle:thin:@//localhost:1521/xepdb1       # service name 일 경우
SRC_DB_USER=test_schema
SRC_DB_PASSWORD=1234

TARGET_DB_URL=jdbc:edb://localhost:5444/edb
TARGET_DB_USER=enterprisedb
TARGET_DB_PASSWORD=1234
```

### ***mtk 명령어***

```bash
runMTK.bat -schemaOnly TEST_SCHEMA
runMTK.bat -dataOnly TEST_SCHEMA
```
  
```log
원본 Oracle 데이터베이스 서버에 연결 중...
MTK-11009: Error Connecting Database "Oracle"
java.lang.ClassNotFoundException: oracle.jdbc.driver.OracleDriver

원본 Oracle 데이터베이스 서버에 연결 중...
Connected to Oracle, version 'Oracle Database 11g Express Edition Release 11.2.0.2.0 - 64bit Production'
대상 EDB Postgres 데이터베이스 서버에 연결 중...
Exception in thread "main" java.lang.NoClassDefFoundError: com/edb/Driver
```
> lib > ojdbc 추가  
> lib > edb-jdbc 추가  
  
🌟 **테이블, 제약조건, 트리거, 프로시져 모두 마이그레이션 되는 것 확인 완료!**

<br/>
<hr>

# ***추가 테스트***

### ***스키마 내 특정 테이블 및 약 1억개 데이터 옮기기***

```sql
-- 프로시저
CREATE OR REPLACE PROCEDURE TEST_SCHEMA.add_test_data
IS
    -- 커밋 주기 설정 (10,000건마다 커밋)
    commit_count CONSTANT NUMBER := 10000; 
BEGIN
    FOR i IN 1..100000000 LOOP
        INSERT INTO test_table2 (id, name, created_at)
        VALUES (i, 'Name_' || i, SYSDATE);

        -- 주기적으로 커밋 수행
        IF MOD(i, commit_count) = 0 THEN
            COMMIT;
        END IF;
    END LOOP;

    -- 최종 커밋
    COMMIT; 
END;

-- 프로시저 실행
BEGIN
  TEST_SCHEMA.ADD_TEST_DATA;
END;
```

<br/>

```bash
runMTK.bat -tables TEST_TABLE2 TEST_SCHEMA

[test_schema.TEST_TABLE2] 테이블 데이터 로드 요약 정보 : 총 소요 시간(sec): 664.919 총 로드 행 수: 96060000 총 크기(MB): 4101.256
데이터 로드 요약 정보: 총 소요 시간(sec): 664.919 총 로드 행 수: 96060000 총 크기(MB): 4101.256
스키마 TEST_SCHEMA이(가) 성공적으로 임포트되었습니다.

마이그레이션 절차가 성공적으로 완료되었습니다.
Total Elapsed Migration Time (sec): 666.545
```

### ***파티셔닝된 테이블 옮기기***

- 파티셔닝은 Enterprise Edition 이상에서만 지원된다. 
  - Standard Edition 또는 Express Edition이라면, 해당 Edition에서는 파티셔닝 기능을 사용할 수 없어 테스트 불가