---
title: SET-UID Program
tags: security
key: page-set_uid_program
cover: /assets/cover/cyber_security.png
mathjax: true
mathjax_autoNumber: true
---

* privileged program: 접근 권한이 적용되어 있는 프로그램
이런 프로그램에 접근하기 위해서는 2가지 방법이 필요하다. 1. Set-UID program.
2. Daemons(Services in Windows)
데몬으로 항상 띄워 놓으면 normal user가 daemon에 request를 날려서 그 프로그램을 통해 privileged program을 실행 시킬 수 있을 것이다.

## 3가지 유저의 형태

* real user ID: 실행되고 있는 프로세스의 진짜 주인.
* effective user ID: access control 안에서 사용되고 있는 ID. 즉 root권한으로 설정된 프로세스를 실행시키면 real user ID는 5000이지만 effective suer ID는 0이 된다.
* saved user ID: 


## Refrence

* [COMPUTER SECURITY: A Hands-on Approach by Wenliang Du](https://www.amazon.com/Computer-Security-Hands-Approach-Wenliang/dp/154836794X)