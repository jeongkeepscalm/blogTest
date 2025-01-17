---
title: "[U-KNOU] 클라우드 컴퓨팅"
description: "[U-KNOU] 클라우드 컴퓨팅"
date: 2024-11-13
categories: [ U-KNOU, Cloud Computing ]
tags: [ U-KNOU, Cloud Computing ]
---

# ***1장. 클라우드 컴퓨팅의 이해***

- 클라우드 컴퓨팅
  - 언제 어디서나 필요한 만큼의 IT 리소스를 필요한 신칸마큼 인터넷을 통해 활용할 수 있는 컴퓨팅 방식
- CSP(Cloud Service Provider)
  - 클라우드 사업자
- SLA(Service Level Agreement)
  - IT 리소스를 대여하는 CSP가 사용자에게 제공하는 서비스의 수준을 정량화하여 명확하게 제시하고 미달할 경우 손해를 배상하도록 하는 서비스 품질 보장 계약
- 프로비저닝
  - IT 리소스를 실시간으로 사용 가능한 상태로 만드는 기술
  
### ***온프레미스***

- 정의
  - 기업이 IT 시스템 운용에 요구된느 다수의 하드웨어와 소프트웨어 설비를 자체적으로 보유하고 운용하는 방식
- 서버의 종류와 기능
  - 애플리케이션 서버
  - HTTP 서버
  - 데이터베이스 서버
  - 메일 서버
  - DNS 서버
  - 그룹웨어 서버
  - 네트워크 관련 서버
  - 인증 서버
  
- 온프레미스 시스템 구축 과정
  - 요구기능 수집 → 설계 → 조달 → 구축 → 운영
  - 용량 계획(Capacity Planning)
    - 서비스에서 요구되는 하드웨어 등 IT 리소스의 필요량을 추정하고 확보하기 위한 계획
  
- 온프레미스 비용
  - CapEx(Capital Expenditure)
    - 물리적 인프라에 대한 비용을 초기에 지출한 다음, 시간이 지남에 따라 납입고지서에서 비용을 공제하는 지출 방식
  - 직접 비용: 실제 비용. IT 장비를 도입하기 위한 외주 비용
    - OS 및 소프트웨어
    - 하드웨어
    - 로드 밸런싱 및 방화벽
    - 백업 및 네트워크 장치
  - 간접 비용: IT 장비를 사용하기 위해 사용되는 유지비용과 기회비용
    - 직무교육
    - 장비 관리 인력
    - H/W & S/W 유지보수

### ***클라우드 기반 시스템 구축***

- 조달 → 구축 → 운영 단계가 매우 단축(CSP가 원스톱으로 제공)
- OpEx(Operational Expenditure)
  - 현재 서비스에 대해 균등하게 지출되어 청구되고 있는 비용
  
- 리프트 앤 시프트(lift and shift)
  - 온프레미스를 사용하는 기업은 작은 업무부터 클라우드로 이관하여 클라우드 기반 시스템의 경험을 축적한 후 인프라 및 관리 비용을 절감하기 위해 점진적으로 이동
  
### ***클라우드 컴퓨팅 서비스 모델 3가지***

- IaaS(Infrastructure as a Service)
  - <img src="/assets/img/knou-cloud-computing/5.png" width="500px" />
  - 서버 및 저장소 + 네트워킹 방화벽 및 보안 + 데이터 센터 물리적 공장, 건물
- PaaS(Platform as a Service)
  - <img src="/assets/img/knou-cloud-computing/4.png" width="500px" />
  - IaaS + 운영체제 + 개발도구, 데이터베이스 관리, 비지니스 분석
- SaaS(Software as a Service)
  - <img src="/assets/img/knou-cloud-computing/3.png" width="500px" />
  - PaaS + 호스팅된 응용 프로그램, 앱
  - ERP
    - 전사적 자원 관리를 클라우드로 제공
  - CRM
    - 고객관리 소프트웨어를 클라우드로 제공
  - SCM
    - 공급망 관리를 클라우드로 제공
  - 문서편집
    - 문서편집 및 그에 관련된 소프트웨어를 클라우드로 제공
  - e.g. 구글 워크스페이스
  
- 기타 클라우드 서비스 모델
  - <img src="/assets/img/knou-cloud-computing/2.png" width="600px" />
  - Faas(Functions as a Service)
    - PaaS와 유사해 보이지만 함수 호출이 요청될 경우에만 연산을 수행하며 요청이 없을 때는 IT 리소스를 사용하지 않는다.
    - e.g. AWS-람다, GOOGLE-클라우드 펑션, AZURE-함수앱
  - CaaS(Container as a Service)
    - 동일한 환경 구축 및 제공이 가능한 컨테이너 기술을 구동할 수 있는 환경을 제공한다. 
    - e.g. AWS-ECS(Elastic Container Service), MS-AKS(Azure Kubernetes Service)
    - 대표적인 컨테이너 관리 플랫폼: 도커
      - 컨테이너 방식
        - 도커가 호스트 OS의 커널을 통해 컨테이너 실행한다. 즉, 별도로 가상머신 이미지를 생성하고 그 안에 OS를 설치하여 리소스를 관리하지 않기 때문에 실행하기 가볍고 호스트 OS를 공유하기 때문에 성능도 호스트 환경에서 실행하는 것과 유사하다.
        - 컨테이너 기반이 되는 컨테이너 엔진의 이미지만 있다면 어디서든 애플리케이션 실행이 가능하여 이식성 또한 높다.
  
### ***클라우드 시스템 배포 모델 4가지***

- 프라이빗 클라우드
  - 단일 조직이 독점적으로 데이터 센터를 구축하고 IT 리소스를 가상화하여 독점적으로 사용하는 컴퓨팅 환경
  - IT 리소스는 제 3자나 CSP가 접근할 수 없다. 
- 퍼블릭 클라우드
  - 다수 사용자가 CSP가 공급하는 서버 및 저장소와 같은 IT 리소스를 공유하여 사용하는 모델
  - CSP가 소유
  - e.g. Azure, AWS, GCP, Naver Cloud
- 하이브리드 클라우드
  - 퍼블릭 클라우드 인프라와 프라이빗 클라우드 인프라를 결합하여 사용하는 방식
  - 퍼블릭 클라우드 서비스를 활용하면서 법적 이슈로 인한 보안 데이터는 프라이빗 클라우드에 저장하여 관리하는 형식
- 커뮤니티 클라우드
  - 정책 또는 내규에 따른 공통된 보안 요구사항이 있는 여러 기업 및 조직 내 구서원들만 독립적으로 사용할 수 있도록 IT 리소스를 관리하는 형태의 클라우드
  - 커뮤니티 외부의 제 3자는 클라우드 자원에 접근할 수 없다.
  
### ***클라우드 컴퓨팅 장/단점***

- 장점
  - 민첩성: 대내외적으로 발생하는 변화에 신속하게 대처 가능
  - 탄력성: 초기 투자 비용 없이도 대규모 IT 인프라를 확보
  - 신속성
  - 경제성
  - 신뢰성: 오류 없이 올바르게 동작하는 능력
  - 가용성: 서버가 죽지 않고 정상적으로 윤영되는 능력
  - 비용 절감
  - 인력 문제 해소
- 단점
  - 보안취약성 증가
  - 책임 소재 불분명
  - 제한된 이식성
    - LOCK IN: 한 CSP에서 다른 CSP로 이동하는 것이 거의 불가능
  - 과도한 비용지출
    - 장기적 클라우드 서비스 사용
    - 지속적으로 높은 수준의 컴퓨팅 리소스 사용
  - 규제와 법적 이슈

### ***클라우드 컴퓨팅 관련 기술***

- 클러스터링 기술
  - 클러스터 컴퓨터: 고속의 네트워크로 동기화되어 단일 시스템인 것처럼 동작하는 독립적인 IT 리소스 그룹
  - 클러스터링 기술: 가용성과 신뢰성을 갖춘 컴퓨팅 환경을 구성하는데 사용하는 기술(이중화와 장애극복 기능이 내장)
- 그리드 컴퓨팅
  - IT 리소스가 플랫폼상에서 논리적 리소스 풀로 등록되어 풀에 포함된 리소스가 집합적으로 고성능의 분산클러스터를 구성, 제공하는 기술
  - 리소스의 결합성이 매우 작고, 서로 다른 기종의 리소스들이 물리적으로 분산되어 있다는 점에서 클러스터링 기술과 구분된다. 
- 가상화
  - 물리적 컴퓨터 환경상에 가상 인스턴스를 만드는데 사용되는 기술
  - <img src="/assets/img/knou-cloud-computing/1.png" width="600px" />
  - 호스트 가상화
    - OS 위에 가상화 소프트웨어 설치하는 방식
  - 하이퍼바이저 가상화
    - 하이퍼바이저 위에 게스트 OS를 설치하는 방식
    - 하이퍼바이저가 하드웨어를 직접 제어하여 불필요한 CPU나 메로리 사용이 줄어든다.
  - 컨테이너 가상화
    - 애플리케이션과 구동 환경만 가상화하여 하이퍼바이저 방식에 비해 가볍고 효율적이며 안정적인 서비스 구현이 가능하다.
    - 게스트 OS가 필요하지 않은 점을 제외하고 호스트 가상화와 유사하다.
- 서버리스 컴퓨팅 기술
  - 서버를 생성, 구성, 유지 관리하지 않고 애플리케이션 코드를 실행할 수 있는 환경
  - 요청 시에만 서버를 사용한다. 
  - e.g. 온라인 상품 주문시 메일 발송

<br>  
<hr>

# ***2장. 클라우드 컴퓨팅 서비스***

- 온디맨드 셀프서비스(on-demand self-service)
  - 사용자가 IT 리소스 필요시 전문가의 개입 없이 필요한 만큼 자동적으로 확보해 사용할 수 있는 특징
- 크라이언트-서버 모델(CS: Client-Server)
  - 크라이언트와 서버간 작업을 분리해주는 분산 애플리케이션 구조이자 네트워크 아키텍처
  - 팻 클라이언트(fat client)
    - 중앙 서버와 독립하여 직접 정보처리를 위해 풍부한 컴퓨팅 기능을 보유한 클라이언트
  - 씬 클라이언트(thin client)
    - 다른 서버에 크게 의존하는 컴퓨터나 네트워크의 클라이언트
  
- 멀티테넌트 모델 기반(multi-tenant)
  - 하나의 서비스를 여러 테넌트가 함께 사용하지만 논리적으로 분리되어 있는 소프트웨어 아키텍처
  - 멀티테넌시(multi-tenancy)
    - 논리적으로 분리된 영역 내 다중 테넌트에게 개별 프로그램 인스턴스를 제공하여 각 사용자가 독립적으로 사용하게 하는 소프트웨어 프로그램의 특징
  
- 크라우드 컴퓨팅 특징 정리
  - 주문형 셀프서비스
  - 접속 용이성
  - 가상화와 분산처리
  - 유연성
  - 사용량 기반 과금제
  
### ***복합 서비스 모델***

- VDI(Virtual Desktop Infrastructure)
  - 장소와 시간에 구애받지 않고 인터넷을 통해 개인의 PC 환경을 사용할 수 있게 한다.
- CDN(Contents Delivery Network)
  - 대규모 콘텐츠 제공을 위한 네트워크 서비스

<br>  
<hr>

# ***3장. 클라우드 컴퓨팅 기술***

- 클라우드 컴퓨팅을 구성하는 기술
  - 가상화
  - 분산처리
  - 오픈 인터페이스
    - 인터넷 기반의 서비스 및 서비스 간 정보를 공유할 수 있는 접속 기술
  - 오케스트레이션
    - CSP가 실시간으로 IT 리소스를 프로비저닝하여 제공하고 서비스 요청부터 제공까지 자동화하는 기술
  - 보안 및 프라이버시 보호
  
### ***가상화***

- 물리적 IT 리소스를 가상의 IT 리소스로 전환시키는 기술
- 물리적 리소스를 여러 논리적 리소스의 형태로 재구성하여 물리적 리소스를 감추고 사용자가 요청한 물리적 리소스인 것 처럼 보여주는 기술
  
- 가상화 기술의 특성
  - 파티셔닝
    - 하나의 물리적 머신에서 여러 개의 OS 운영 가능
    - 리소스 분할-분배하여 사용량에 따라 효율적으로 사용가능
  - 캡슐화
  - 격리
  - 하드웨어 독립성
    - 하드웨어 안 VM은 독립적으로 가동되어 다른 가상화 시스템 또는 물리적 시스템 서버로 마이그레이션이 가능하다.
    - V2P(Virtual machine to Physical machine)
    - P2V(Physical machine to Virtual machine)

### ***인프라 구성***

- 인프라 구성에 필요한 장비
  - `서버`: 모든 IT 서비스의 요청부터 연산처리, 결과 제공까지 하는 완성된 컴퓨터 시스템
    - x86 및 x64
    - UNIX 서버
    - ARM 서버
    - HPC 기술
  - `스토리지`: IT 서비스에 필요한 데이터를 효과적으로 저장, 관리 및 보호하는 장비
    - HDD
    - SSD
    - Hybrid
  - `네트워크`: 사용자가 원격지에서 시스템에 접근할 수 있도록 IT 리소스를 연결하기 위한 장비
    - 스위치
      - 네트워크 단위들을 연결하는 통신 장비(허브)
      - OSI 2계층에서 사용하는 네트워크 내 패킷 전달 담당
    - 라우터
      - OSI 3계층에서 패킷의 위치를 추출하여 그 위치에 대한 최상의 경로를 지정
      - 이 경로를 따라 데이터 패킷을 다음 장치로 전향시키는 장치
    - 방화벽
      - 서로 다른 네트워크를 통과하는 데이터를 허용, 거부, 검사, 수정하는 하드웨어나 소프트웨어 장치
  - `OS`: 서버, 스토리지, 네트워크 및 클러스터 장비 등을 제어하기 위한 기술을 내장한 소프트웨어
    - 클라이언트 OS
      - 윈도우
      - Mac OS 
      - 안드로이드 OS
      - iOS
  - `미들웨어`: 하드웨어와 소프트웨어 중간에 위치한 프로그램으로 서버 OS 상에서 애플리케이션이 OS로 부터 제공받는 서비스 외에 추가적으로 이용할 수 있는 서비스를 제공하는 보조적 컴퓨터 소프트웨어
    - TP 모니터
      - 시스템과 테이터베이스 사이의 최소 처리 장치를 모니터링하고 일관성을 유지하는 트랜잭션 관리 미들웨어
    - 웹 애플리케이션 서버
    - 엔터프라이즈 서비스 버스
      - 컴포넌트화된 논리적 집합으로 묶은 핵심 미들웨어
    - 데이터베이스 미들웨어
  - `인프라 설비`: 인프라 설비와 관련된 기술을 IDC(Integrated Data Center) 관리 기술이라고 하며 IDC 기반 시설은 아래와 같다.
    - 배선
    - 공조

### ***서버 가상화***

- 호스트 가상화 기술
  - 하드웨어(호스트) 위에 기반이 되는 OS를 설치하고 그 위에 다시 가상화 소프트웨어를 설치하여 가상화를 구성
  - VM을 이용한 서버 가상화를 소프트웨어적 파티셔닝 또는 OS 이미지 가상화라고 한다. 
  
- 하이퍼바이저 가상화 기술
  - 어떠한 OS에 의존하지 않고 하드웨어에 직접 설치, 구동되는 구조
  - 하이퍼바이저가 하드웨어를 직접 제어 가능하여 상대적으로 오버헤드가 작다.
  - 하드웨어를 제어할 OS가 없어 하이퍼바이저 구동 시 DOM0라는 관리 머신이 함께 구동
  - 전가상화
    - 하드웨어를 완전히 가상화하는 방식
  - 반가상화
    - 하드웨어를 부분적으로 가상화하는 방식
    - 하이퍼 콜이라는 인터페이스를 통해 하이퍼바이저에 직접 제어 요청을 한다. 
  
- 컨테이너 가상화 기술
  - 개념
    - 호스트 OS 상에 논리적인 영역(컨테이너)을 만들고 애플리케이션을 동작시키는데 필요한 라이브러리와 애플리케이션 등을 컨테이너 안에 포함시켜 게스트 OS 없이 개별 서버와 같은 실행 환경을 구축하는 방식
    - 게스트 OS의 실행에 소요되는 오버헤드가 없어 고속으로 작동한다.
  - 도커
    - <img src="/assets/img/knou-cloud-computing/6.png" width="500px" />
    - 컨테이너 가상화 기술에서 가장 대표적으로 사용되는 솔루션
    - 리눅스 컨테이너를 기반으로 구동
    - 이미지 생성하고 배포에 특화된 기능을 제공
    - 레지스트리
      - 도커 이미지를 저장하고 저장된 이미지를 사용자가 다운로드하여 설치할 수 있는 공유 환경을 제공하는 저장소
    - 특징
      - 빠른 설치
      - 애플리케이션 이식성
      - 버전 제어, 컴포넌트 재사용
      - 쉬운 유지 관리

### ***네트워크 가상화***

- 하나의 네트워크 케이블에 연결되어 있어도 마치 어러 개의 네트워크가 있는 것처럼 처리할 수 있어 VM의 네트워크 통신을 하나의 물리 네트워크로 집약할 때 발생하는 문제를 해결할 수 있다.
- 데이터의 흐름 수준에서 제어를 통해 네트워크를 논리적으로 나누어 기존 네트워크에 논리적 영역을 만든다. 
  
- 장점
  - 네트워크 리소스 보안 향상
    - 실제적인 네트워크 그룹의 이동없이 네트워크가 분할되어 네트워크 보안 상 발생할 수 있는 문제를 차단한다. 
  - 비용절감
    - 네트워크 분할 시 스위치, 라우터 등의 네트워크 장비가 추가적으로 요구되는 반면, 네트워크 가상화 기술을 통해 분할 시 해당 장치들을 추가할 필요가 없다. 
  - 네트워크 설정 작업의 편의성
    - 간단한 설정으로 구성 및 관리 가능
  
- 네트워크 가상화를 위해 사용하는 기술
  - VLAN(Virtual LAN)
    - 서버로 부터 발신되는 모든 패킷에 서버에 부여된 고유 번호가 적힌 ***태그***를 붙여 이 태그를 통해 하나의 물리적 네트워크 안에서 네트워크를 여러 그룹으로 나누는 방법을 사용
    - 스위치 또는 라우터의 포트에 태그 정보를 설정하여 분할 네트워크를 구성
  - VPN(Virtual Private Network)
    - 불특정 다수가 이용하는 공용 네트워크에 가상으로 전용선과 같은 사설 네트워크의 효과를 제공하여 비용절감과 보안성을 동시에 얻는 기술
  - NFV(Network Functions Vitualization)
    - 네트워크 장비 도입 업시 네트워크 기능을 소프트웨어적으로 가상화로 구현하여 서버 위에 구축하는 기술
    - 장점
      - 신규 소프트 웨어 적용 시 새롭게 하드웨어 장비의 구축 불필요
      - 서비스 대응 및 트래픽 변화에 대한 신속한 대응
      - 네트워크 유지보수 비용 절감
      - 빠른 네트워크 업그레이드
  - SDN(Software Defined Network)
    - 라우터, 스위치 등 하드웨어 중심의 네트워크 인프라를 소프트웨어 형태로 진화시켜 네트워크 서비스의 유연성과 비지니스 민첩성을 향상시키는 기술
    - 데이터 플레인: 데이터 전송 기능
    - 컨트롤 플레인: 데이터 제어 기능

### ***스토리지 기술***

- 스토리지 단위
  - 파일
    - 데이터 스트림이 파일로 저장되어 폴더로 구조화되는 단위
    - 최소 데이터 처리는 파일 단위로 이루어진다. 
  - 블록
    - 스토리지 하드웨어에 가장 가까운 수준의 최소 데이터 단위
  - 데이터 세트
    - 데이터가 테이블, 단락, 레코드와 같은 형식으로 구성된 단위
  - 오브젝트
    - 데이터가 객체 단위로 구조화되는 스토리지
    - 오브젝트 스토리지의 접근에는 REST(REpresentational State Transfer) 형식의 API를 사용한다. 
    - 갱신 빈도가 적은 데이터나 대량의 데이터를 저장하고 장기 보존하는 용도로 사용된다. 
  
- 스토리지의 확장성과 중복성을 향상시키면서 공유할 수 있는 대표적인 기술
  - `RAID(Redundant Arrays of Independent Disks)`
    - 복수 개의 독립적인 디스크를 동시에 구동하는 기법을 총칭
    - RAID 0 수준(데이터 스트라이핑)
      - <img src="/assets/img/knou-cloud-computing/7.png" width="500px" />
      - 가장 기본적인 수준의 구현방식
      - 데이터를 여러 디스크에 나누어 저장하는 방식
      - 데이터 중복 저장 X 
    - RAID 1 수준(미러링)
      - <img src="/assets/img/knou-cloud-computing/8.png" width="500px" />
      - 데이터 중복 저장하여 디스크 장애 발생 시 데이터 복구 가능
    - RAID 0+1 수준(스트라이핑 + 미러링)
      - RAID 0 수준으로 볼륨을 구성한 후 그 볼륨을 미러링하는 방식
    - RAID 2 수준
      - 해밍 코드를 이용해 에러 검출 및 정정하도록 되어있으나 상업적으로 지원하는 드라이브가 출시되지 않아 구현되지 않음
    - RAID 3 수준
      - <img src="/assets/img/knou-cloud-computing/9.png" width="500px" />
      - RAID 0 수준과 마찬가지로 스트라이프를 이용하여 데이터 저장하지만, 에러 검출 및 정정을 위해 별도의 패리티 디스크를 유지
      - 하나의 디스크에 장애 발생 시 패리트 비트를 이용하여 원본 데이터 복구 가능
      - 2개 이상의 디스크 장애 발생시 복구가 어렵다. 
    - RAID 4 수준
      - <img src="/assets/img/knou-cloud-computing/10.png" width="500px" />
      - RAID 3 수준과 유사하지만 차이점은 데이터 스트라이핑 단위이다. RAID 3 수준의 경우 바이트 단위의 스트라이핑을 사용하지만 RAID 4 수준의 경우 블록 단위의 스트라이핑을 사용한다. 
    - RAID 5 수준
      - 각각의 패리티가 모든 디스크에 분산 저장되어 RAID 3, RAID 4 수준의 단점을 극복한다. 
  
    - 각 RAID 수준의 목적은 디스크를 병렬적으로 구동시켜 데이터 저장의 신뢰성을 높이고 입출력 성능을 향상시키는 것이다. 
    - 신뢰성 향상
      - 데이터를 여러 디스크에 중복 저장
    - 성능 향상
      - <img src="/assets/img/knou-cloud-computing/11.png" width="500px" />
      - 병렬성: 디스크에 병렬적인 접근을 가능하게 하여 읽기 요청을 다수의 디스크가 나누어 처리함으로써 읽기 속도를 향상시킬 수 있다.
      - 각 바이트를 비트 단위로 잘라서 다수의 디스크에 나누어 저장
      - 블록단위 스트라이핑 
        - 각 블록에 논리 번호를 부여하여 다수의 디스크에 나누어 저장
  - `NAS(Network Attached Storage)`
    - <img src="/assets/img/knou-cloud-computing/12.png" width="500px" />
    - 스토리지가 컴퓨터에 직접 연결되지 않고 네트워크 장비인 스위치를 통해 연결되는 저장장치
    - 포트 수에 제한이 없어 확장성과 유연성이 뛰어나고 경제적이며 설치와 유지보수가 용이하다.
    - 네트워크에 따른 지연율 발생 가능성 존재
  - `SAN(Storage Area Network)`
    - <img src="/assets/img/knou-cloud-computing/13.png" width="500px" />
    - 대규모 사용자에게 고속의 데이터 접근 서비스를 제공하기 위해 여러 종류의 데이터 저장장치와 데이터를 사용할 서버를 파이버 채널을 사용하여 파이버 채널(fiber channel) 스위치와 연결한 고속 데이터 네트워크
    - 네트워크 구성에 확장성, 유연성, 가용성이 우수하지만 NAS와 달리 이기종 서버 환경을 지원하지 않으며 여러 서버 사이에서 특정 파일 공유 시 일관성에 문제가 발생할 가능성이 존재

### ***스토리지 가상화***

- <img src="/assets/img/knou-cloud-computing/14.png" width="500px" />
- RAID, NAS, SAN 등 디스크 다중화를 통한 대형 스토리지는 스토리지의 확장성과 데이터 공유에 많은 이점을 제공한 것은 사실이나 관리 및 유지하는데 많은 인력과 비용이 요구된다. 
- 스토리지 가상화를 통해 네트워크에 분산되어 있는 여러 스토리지 디바이스를 단일 리소스로 인식하고 프로비저닝할 수 있다. 
- 서버와 스토리지 사이의 중간 계층에서 인터페이스 역할을 한다. 
  
- 스토리지 가상화 장점
  - 스토리지 활용률
    - 스토리지를 탄력적으로 할당하고 디스크 단편화로 불용되는 스토리지의 공간을 최소화하여 기존 스토리지의 활용률을 높인다.
  - I/O 성능
    - RAID와 스트라이핑 저장 기술 등을 통해 데이터의 입출력 성능과 스토리지 가용성을 향상시킨다. 
  - 가용성
    - RAID 등을 통해 데이터를 미러링하거나 복제하여 데이터 손실을 방지한다. 
    - 무중단 디스크 교체를 통해 디스크 오류발생 시 스토리지 시스템의 다운 타임 없이 서비스 중에도 디스크 교체를 수행한다. 
  - 관리 용이성
  
- 스토리지 가상화 기술 3가지
  - 디스크 컨트롤러 가상화
    - 내부적으로 논리적 파티셔닝 기술을 사용
  - 네트워크 기반 스토리지 블록 가상화
    - 일반적으로 SAN으로 연결된 파이버 채널 네트워크를 사용
  - 소프트웨어 정의 스토리지
    - 하드웨어에서 스토리지 소프트웨어를 분리하는 스토리지 아키텍처
  
- 클라우드 서비스 무정지 기술
  - 헬스 체크
    - 감시 대상인 하드웨어 또는 소프트 웨어가 정상 상태에 있는지의 여부를 확인하는 기술
    - 온프레미스 환경에서 사용하는 헬스체크
      - 하트비트 모니터링
      - 에이전트 프로그램 사용
      - SNMP(Simple Network Management Protocol)을 사용한 장비 정보 수집 등
    - 클라우드 모니터의 자동 복구 시스템의 5가지 기능
      - 관찰 및 감시
      - 이벤트 발생 시 대응행위 결정
      - 이벤트 발생 시 대응행위 수행
      - 보고
      - 에스컬레이션
        - 장비에서 발생한 에러가 정의 된 상황에 비해 심각할 경우 CSP 또는 서비스 관리자에게 상황을 단계적으로 전달하는 것
        - 에스컬레이션 순서
          - 장애 조치 이후 배치 파일 실행
          - 시스템 로그에 콘솔 메시지 전송
          - 로그 파일 전송
          - 관리자에게 이메일 메시지 전송
          - SNMP 트랩 전송

# ***4장. 클라우드 아키텍처***

- 서비스 오케스트레이션
  - 복잡한 클라우드 리소스와 워크플로를 좀 더 쉽게 관리할 수 있도록 IT 리소스를 배치하는 자동화된 설정, 관리, 조정 기술
  
- 클라우드 서비스 관리
  - 경영 지원
    - 클라우드 IT 리소스의 과금(billing), 감사(audit) 정책을 총괄한다. 
  - 프로비저닝/구성
    - 클라우드 기반 서비스가 클라우드 IT 리소스를 추가로 필요로 하거나 줄여야 할 때, 신속하게 리소스를 배치하거나 변경, 모니터링, SLA 관리 등을 수행하는 데 목적을 둔다. 
  - 이식성/상호운용성
    - 상호윤용성: 2개 이상의 시스템 또는 애플리케이션 간에 원활하게 데이터를 교환하고 사용할 수 있는 특성
  
- 서비스 고가용성(HA: High-Availability)을 달성하기 위한 기술 전략 3가지
  - 다중 애플리케이션 서버와 부하 분산
  - 데이터베이스 또는 스토리지의 이중화
  - 여러 지러적 위치에 따른 서비스 배치

### ***리소스 풀링***

- 즉시 사용 가능한 리소스 풀로부터 리소스를 사용하는 과정
- 리소스 풀
  - 서비스에서 즉시 사용할 수 있는 서버나 스토리지 등의 IT 리소스를 담아 두는 것
  - 신속한 확장과 탄력성 확보를 위해 사용자로부터 물리적으로 가까운 위치에 구성한다. 
- 리소스 풀에 있는 리소스는 멀티테넌시 구조를 기반으로 특정 서비스에 고정되지 않고 자유롭게 배치될 수 있다. 
- 리소스 풀에 있는 리소스의 특징
  - 리소스의 구체적인 물리적 위치는 알 수 없다. (IDC에 있는 서버, 스토리지의 지리적 위치)
  - 추상화되어 있다.
  - 서비스나 애플리케이션에 따라 자유롭게 사용되고 해제된다. 
- 리소스 풀 모니터링 
  - 사용자는 리소스를 사용한 만큼 비용을 지불하기 때문에 CSP가 리소스 사용량을 감시하는 것
  - 리소스의 가용성을 확인하는 기능
- <img src="/assets/img/knou-cloud-computing/15.png" width="500px" />
  
- 그룹 풀
- 리소스 풀의 다른 구성이 리소스 형태별로 모아 놓은 풀 여러개를 큰 풀로 묶는 것
  - 그룹 풀 특징
    - 유연한 계층적 구성
    - 풀 간의 분리, 풀 내에서의 공유
    - 엑세스 제어 및 위임
    - 리소스를 하드웨어에서 분리
- 클라우드 리소스 풀링의 작동 방식
  - 감사 모니터 
    - 클라우드에서 사용되는 리소스 사용을 감시하여 스토리지 또는 메모리에 기록된 데이터에 대한 개인정보 보호 귲ㅇ 위반 여부 등을 확인한다. 
  - 클라우드 사용량 모니터  
    - 풀링된 리소스가 어떤 사용자에게 사용되었는지 기록하는 기능
  - 서버 가상화
  - 논리 네트워크 경계
  - 사용량 과금 모니터 
    - 리소스 사용 시간, 사용된 형태에 따른 과금 비용을 산출하기 위해 사용
  - 원격 운영 시스템
    - 클라우드 기반 서비스 관리자가 필요에 따라 관리할 수 있어야하기에 API 또는 웹 관리 프로그램을 지원한다. 
  - 리소스 관리 시스템
    - 리소스 풀 구성을 위한 도구와 권한 관리 옵션을 포함한다. 
- 풀링된 리소스는 단순히 풀이 구성된 것에 그치지 않고 HA를 위한 리소스 다중화, 로드 밸런싱, 클라우드 버스팅 등에 사용된다.

### ***로드 밸런싱***

- 사용 가능한 서버가 여러 대 있을 때, 사용자의 요청을 여러 대의 서버로 분산시키는 것
- 워크로드를 균등하게 배분하여 특정 리소스가 과잉으로 사용되는 문제가 발생하지 않도록 로드 밸런서가 활용된다.
  
- IT 리소스의 스케일링
  - 사용량의 요구에 따라 시스템의 용량을 탄력적으로 늘리거나 줄일 수 있는 능력
  - <img src="/assets/img/knou-cloud-computing/16.png" width="500px" />
  - 수직 스케일링
    - 하드웨어 장비 추가를 통해 IT 리소스를 즉시 이용할 수 있다. 
    - 리소스 교체되는 동안 다운 타임 발생하여 클라우드 환경에서 사용하는 확장 방식은 아니다.
    - 스케일 업
      - IT 리소스를 더 높은 사양으로 교체하는 것
    - 스케일 다운
      - IT 리소스를 더 낮은 사양으로 교체하는 것
  - 수평 스케일링
    - 유사한 유형의 IT 리소스를 추가 또는 반환하고 클러스터링 기술을 활용하여 단일 리소스로 운용하는 방식
    - 리소스 복제 및 자동 확장에 소요되는 부가적 IT 리소스가 요구되는 단점이 존재
    - 스케일 아웃
    - 스케일 인
  - <img src="/assets/img/knou-cloud-computing/17.png" width="500px" />
  
- 로드 밸런싱
  - 클라이언트와 서버 사이에 위치하여 요청을 여러 서버로 트래픽을 적절하게 분산하는 역할하는 네트워크 처리 기술
  - 여러 서버를 묶어서 하나의 고성능 가상 서버에 준하는 성능을 낼 수 있다.
  
- 클라우드에서 사용하는 작업부하 방식
  - <img src="/assets/img/knou-cloud-computing/18.png" width="500px" />
  - 로드 밸런서(L4 스위치) 추가
    - 하나의 서버에 작업이 집중되지 않도록 한다.
  - 로드 밸런싱 컴포넌트 추가
    - 별도의 네트워크 장치를 두지 않고 서버에 소프트웨어 방식의 로드 밸런싱 컴포넌트를 추가
    - 브로커
      - 로드 밸런싱 컴포넌트가 추가된 서버
    - 워커
      - 사용자의 요청을 처리하는 서버
  
- 오토 스케일링(auto scaling, 동적 확장)
  - 클라우드에서는 리소스 풀과 로드 밸런싱을 통해 오토 스케일링(auto scaling, 동적 확장)이 가능해진다.
  - 오토 스케일링을 통해 이용자의 증가, 감소에 따라 서버의 추가와 제거가 유동적으로 이루어진다.
  - 로드 밸런싱 기술을 사용하여 수평 스케일링을 자동화
  - 오토 스케일링을 위한 클라우드 요소
    - 클라우드 사용량 모니터
      - 클라우드 리소스 사용량을 감시
    - 자동화된 확장 리스너
      - 갑작스러운 사용량 증가에 대비하거나 리소스 사용을 마무리하고 리소스 풀로 반환
    - 클라우드 사용량 모니터로 리소스 사용량을 감시하다 특정 임곗값(CPU 사용률 90%)을 초과하면 자동 확장 리스너가 시스템 과부하를 해결하기 위한 조치를 수행한다. 이 과정은 스크립트를 통해 자동화된다.

### ***클라우드 버스팅***

- 프라이빗 클라우드가 요구 처리량을 감당할 수 없을 때, 일시적으로 예비 퍼블릭 클라우드에 이관하여 동적으로 짧은 시간 안에 전체 시스템의 처리 능력을 향상시키는 기술
- 프라이빗 클라우드 물리적 확장 x
- 임계값을 CPU 사용량 100%로 정하면 클라우드 버스팅 수행 불가능
- 클라우드 버스팅 3단계
  - 프라이빗 클라우드 서비스 구조 → 퍼블릭 클라우드에 구성
  - 클라우드 버스팅 사용 조건 및 이관 데이터와 애플리케이션 지정
  - 프라이빗 클라우드 데이터 및 애플리케이션을 퍼블릭 클라우드로 전송
- 버스팅 아웃
  - 프라이빗 클라우드에서 퍼블릭 클라우드로 서비스 환경을 확장하는 것
- 버스팅 인
  - 종료된 퍼블릭 클라우드의 리소스를 반환하고 다시 ㅍ라이빗 클라우드로만 작업을 처리하는 것
- <img src="/assets/img/knou-cloud-computing/19.png" width="500px" />

### ***무중단 서비스 재배치***

- 다중화
  - 장애 발생 시 서비스나 시스템의 중단없이 계속 유지할 수 있도록 가용성이 높은 시스템을 만들기 위한 대표적인 기술
  - 장애 발생 즉시 예비 장비로 페일오버(failover)하여 시스템이 연속적으로 기능할 수 있도록 한다.
  - 다중화 대상으로는 서버, 스토리지, 로드 밸런서, 네트워크 장치 등이 있다. 
  - 다중화를 통해 SPOF(Single Point Of Failure)를 없애고 무중단 및 HA 서비스를 구현할 수 있게 된다. 
  - 다중화 구성 2가지 방식
    - 액티브-액티브
    - 액티브-스탠바이
      - 백업 장비가 대기하는 방식에 따라 세가지로 구분된다.
        - 핫 스탠바이
          - 백업 장비가 액티브 장비 측과 동일하게 가동 상태를 유지하고 즉시 이용 가능한 구성
        - 웜 스탠바이
          - 백업 장비 측은 가동 후 이용 가능한 상태가 되기까지 일정 부분 준비가 필요한 구성
        - 콜드 스탠바이
          - 백업 장비 측을 정지시켜 두는 구성

# 5장. ***클라우드 컴퓨팅의 미래***

### ***엣지 컴퓨팅***

- 클라우드 컴퓨팅의 개입을 최소화하기 위해 사용자 또는 엔드포인트 단말기의 물리적 위치와 인접한 곳에서 컴퓨팅을 수행한 후, 그 수행 결과를 사용자에게 제공하여 요청에 대한 반응 시간을 단축시킬 수 있는 기술
- 데이터 센터에서 모든 데이터를 처리할 때 발생하는 과부하와 그에 따른 지연현상을 완화시키고자 제안된 기술
- 엣지 컴퓨팅을 활용한 분야
  - 게임
  - 자율주행
  
- 엣지 컴퓨팅의 구조
  - <img src="/assets/img/knou-cloud-computing/20.png" width="500px" />
  - 프론트 엔드(front end)
    - 엣지 디바이스로 연산처리를 할 수 있는 능력이 경미한 수준의 장치를 의미
  - 니어 엔드(near end)
    - 어느 정도 데이터 처리 및 저장이 엣지 노드에서 처리
  - 파 엔드(far end)
    - 리전에 위치한 클라우드 서버를 의미
    - 모든 계층을 통틀어 가장 고성능의 연산처리가 가능하고 가장 큰 볼륨의 저장 공간을 제공한다. 
    - 프론트 엔드와 니어 엔드에서 수행하지 못하는 빅데이터 관리나 머신러닝 등의 작업을 수행
  
- 엣지 컴퓨팅의 보안
  - SASE(Secure Access Service Edge)
    - 엣지 계층의 WAN에 여러 가지 네트워크 보안 요소를 합친 네트워크 아키텍처
    - SASE의 5가지 주요 기술
      - CASB(Cloud Access Security Broker)
        - 클라우드 서비스 사용자와 클라우드 애플리케이션 사이에 위치함 모든 활동을 모니터링한다. 
      - SWG(Secure Web Gateway)
        - 사용자의 웹, 인터넷상에서 소프트웨어, 멀웨어를 필터링하고 기업, 규제 정책 컴플라이언스를 시행하는 솔루션
      - ZTNA(Zero Trust Network Access)
        - 인증된 사용자, 장치, 애플리케이션 트래픽만 조직 내의 사용자, 장ㅊ, 애플리케이션에 대한 엑세스 권한이 부여되는 보안 아키텍처
      - SD-WAN
        - SDN을 WAN에 적용한 기술로 인터넷 서비스를 포함한 전송 서비스의 모든 조합을 활용
      - FWaaS(FireWall as a Service)
        - URL 필터링, 지능형 지속위협(APT), IPS, DNS 보안과 같은 엑세스 제어를 포함하는 고급 레이어 7, 차세대 방화벽(NGFW) 기능을 제공하는 클라우드 방화벽

### ***포그 컴퓨팅***

- 엣지와 클라우드 데이터 센터 사이에 위치한 또 다른 분산 네트워크 계층
- 데이터가 생성된 위치에서 데이터를 저장하는 위치로 처리하는 방식으로 엣지에서 종단점으로 가져오는 데 필요한 처리 능력 및 네트워크 연결을 포함한다. 
- 기지국 같은 곳에 컴퓨팅 리소스를 설치하여 지역적으로 분산된 엣지 리소스를 중간에 연결하고 서로 다른 통신망, 프로토콜을 매개하는 또 하나의 로컬 네트워크
  
- 포그 컴퓨팅 구조
  - <img src="/assets/img/knou-cloud-computing/21.png" width="500px" />
  - <img src="/assets/img/knou-cloud-computing/22.png" width="500px" />
  
- 포그 컴퓨팅의 장단점
  - 장점
    - 지연최소화
    - 네트워크 처리량 감소
    - 데이터 보안성 향상
    - 신뢰도 향상
    - 서비스 신속성 향상
  - 단점
    - 데이터 전송속도에 의존적
    - 가용성, 저속 전송 및 병목현상 문제
    - 포그 노드 자체에 대한 보안에 많은 주의 요구
  
- 포그 컴퓨팅 보안
  - EDR(Endpoint Detection and Response)
    - 인공지능 기술을 활용하여 엔드 포인트에서의 위험을 탐지하고 대응하는 기술