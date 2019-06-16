---
layout: post
categories: posts
title: 원격수업 LTI 개발
subtitle: 학교의 운영 방침에 맞게 원격 수업(인터넷 강의)의 기준 요건을 설정하는 LTI(Learning Tools Interoperability) 개발
featured-image: /images/portfolio/distancelearning/distancelearning-main.jpg
tags: [business project, web]
date-string: MAY, 2019
---


# 요약
- 개발자: 김인근, 이주희 (Xinics 개발팀)
- 개발 기간: 2019.05 ~ 2019.05 (약 3주)
- Github Repository: Private

# 도입 기관
- 마산대학교
- 경성대학교
- 한남대학교

# 프로젝트 목표
다음의 상호 연관된 2가지 LTI를 개발하는 것을 목표로 한다.

1. 학습설계진단설정 LTI: 대학의 *운영자*가 교육부가 발표한 **'원격 수업 운영 기준'**, 또는 **'학점은행제 운영 기준'**에 맞춰 원격수업의 기준요건을 설정하는 LTI
2. 학습설계진단 LTI: 원격수업의 *교수자*가 수업을 설계할 때, 대학 운영자가 위 LTI를 통해 설정한 기준에 부합하는지 가시적으로 파악할 수 있도록 하는 LTI

# 기술 스택
- PHP 7.2
- React
- MongoDB
- Postgresql

### Library
#### PHP
- Laravel

#### Javascript
- Kendo Grid

<hr>

# 프로젝트 설명

## 개요
- 2018년 교육부는 [원격 수업 운영 기준](https://www.moe.go.kr/boardCnts/view.do?boardID=337&lev=0&statusYN=W&s=moe&m=030308&opType=N&boardSeq=75423)을 발표하여 `원격 수업으로 인정받기 위한 기준`을 공식적으로 발표하였다.
- 2018년 교육부는 [학점인정 등에 관한 법률 시행령](https://www.moe.go.kr/boardCnts/fileDown.do?m=0503&s=moe&fileSeq=4ca907ef37ff71db5cd124fc270917ec)을 개정하여 K-MOOC을 통한 `학점은행제 기준`을 공식적으로 발표하였다.
- Xinics가 개발한 LMS(Learning management system)인 LearningX가 제공하는 기능을 통해 교수자는 주차별, 차시별로 강의동영상과 과제 및 퀴즈, 토론 등을 업로드하여 과목을 설계할 수 있다.
- 학생의 모든 시청기록, 다운로드 기록 등은 LearningX와 연결된 Xinics가 개발한 부속 시스템을 통해 DB 및 Log에 저장되며 이를통해 교수자는 원격 수업에서 성적을 부여할 수 있다.
- 대학은 **학점 은행제 기준**과 **원격 수업 운영 기준** 중 하나를 선택하여 적용해야 한다.

## 기존 상황
- LearningX는 과목 설계에 있어서 학습 컨텐츠들의 '양'을 정량적으로 분석하지는 않는다.
- 교육부 개정 기준에 따르면 과목의 강의 컨텐츠가 1분이라도 부족할 경우, 최악의 경우 원격 수업으로 인정되지 않을 수 있다.
- 이에 따라 대학에서는 개설한 원격 수업 과목을 설계할 때 교육부 지침을 따르고 있는지 여부를 판단하는 시스템이 필요했다.

## 예상 효과
- 국내 LMS 중 최초로 정부의 정책을 시스템에 이식하여 '정부 정책의 빠른 현실화'을 이룰 수 있다.
- 기준 미달의 원격 수업 개설을 원천 차단하는 것이 정부의 목표인 만큼, LTI를 도입함으로써 대학의 원격수업의 전반적 퀄리티를 높인다.
- 원격 수업 개설에 있어서의 Human error를 제거하여 규제의 도입과정에 항상 존재하는 불필요한 시시비비를 차단한다.

<hr>

# 프로젝트 결과

## 학습설계진단설정 LTI
### 주차별 설정(학점은행제 운영 기준)
![Admin Credit Bank](/images/portfolio/learningx/distancelearning/admin-distancelearning-credit.jpg)

### 차시별 설정(원격수업 운영 기준)
![Admin Distance Learning](/images/portfolio/learningx/distancelearning/admin-distancelearning-distance.jpg)

## 학습설계진단 LTI
### 주차별 설정(학점은행제 운영 기준)
![Credit Bank](/images/portfolio/learningx/distancelearning/distancelearning-credit.jpg)

![Credit Bank GIF](/images/portfolio/learningx/distancelearning/distancelearning-credit.gif)

### 차시별 설정(원격수업 운영 기준)
![Distance Learning](/images/portfolio/learningx/distancelearning/distancelearning-distance.jpg)

![Distance Learning GIF](/images/portfolio/learningx/distancelearning/distancelearning-distance.gif)
