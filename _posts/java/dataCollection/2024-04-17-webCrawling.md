---
title: webCrawling
description: webCrawling
date: 2024-04-17
categories: [ java, dataCollection ]
tags: [ java, dataCollection, webCrawling ]
---

## Web Crawling with Jsoap library

```java
public void WebCrawlingTest() throws IOException {

  String URL = "https://news.daum.net/";
  Document doc;

  try {
      doc = Jsoup.connect(URL).get();
      Elements els = doc.select(".item_issue a");
      for (Element el : els) {
          String href = el.attr("href");
          if (!el.text().equals("")) {
              System.out.println("title : " + el.text()+" news link : "+href);
          }
      }
  } catch (IOException e) {
      e.printStackTrace();
  }

}
```