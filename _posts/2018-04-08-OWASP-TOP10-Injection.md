---
layout:	post
title:	OWASP TOP 10 - A1 Injection
date:	2018-04-08 
summary:	OWASP Top10 중 Injection 취약점
categories:	jekyll pixyll
---

#OWASP TOP 10 - A1
![OWASP_TOP10_2017](http://blogfiles7.naver.net/MjAxNzA0MTZfMTUx/MDAxNDkyMzEzMzk5NTgz.NdNij63gUTzeiku_dWjXmdVyenFdFF5L35YQRd4bKCsg.Qwk2TKKm-2oVj3pjUK0eHZ0uHpYq9-zliJwYDUnsFcQg.JPEG.nologout/OWASP_Top10_2017_virusmyths.jpg, http://blogfiles7.naver.net/MjAxNzA0MTZfMTUx/MDAxNDkyMzEzMzk5NTgz.NdNij63gUTzeiku_dWjXmdVyenFdFF5L35YQRd4bKCsg.Qwk2TKKm-2oVj3pjUK0eHZ0uHpYq9-zliJwYDUnsFcQg.JPEG.nologout/OWASP_Top10_2017_virusmyths.jpg)

####**A1 - Injection**

==**공격 기법**==
SQL Injection은 DB와 연동된 웹 애플리케이션에서 SQL 질의문에 대한 필터링이 제대로 이루어지지 않을 경우 공격자가 입력이 가능한 폼 (웹 브라우저 주소 입력창, 로그인 폼 등)에 조작된 쿼리를 삽입하여 공격자에게 공개되지 않은 웹 서버의 DB정보를 열람 또는 조작 하는 공격

==**공격 유형**==
- 인증 우회 (AB, Auth Bypass)
 : 보통은 아이디와 패스워드를 입력하는 로그인 페이지를 타겟으로 하여 행해지는 공격기법이며, SQL 쿼리문의 TRUE/FALSE의 논리적 연산 오류를 이용하여 로그인 인증 쿼리문이 무조건 TRUE의 결과값이 나오게 하여 인증을 무력화 시킨다. 
- 데이터 노출 (DD, Data Disclosure)
 : 타겟 시스템의 주요 데이터 절취를 목적으로 하는 방식이며, Error based, Union based, Blind based방식이 있다.
- 원격명령 실행 (RCE, Remote Command Excute) 
 : MS SQL에서 주로 사용되는 방법으로 MSSQL의 Stored Procedure(저장 프로시저)를 이용하여 공격한다.

==**대응 방안**==
웹 방화벽에서의 필터링 규칙을 적용하거나 소스코드 상에서 해당 명령어들을 필터링 하는 방법이 있다.
