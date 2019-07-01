---
layout: post
categories: posts
title: 차세대 MOOC 플랫폼 Course Catalog 서비스 개발
subtitle: Coursera와 같은 MOOC형 강좌 통합 플랫폼인 Course Catal는g 서비스의 Front를 React 기반으로 개발한다
featured-image: /images/portfolio/coursecatalog/coursecatalog-main.jpg
tags: [business, web]
date-string: DECEMBER, 2018
---


# 요약
- 개발 기간: 2018.12 ~ 2019.02 (약 2개월)
- Github Repository: Private

# 도입 기관
- K-MOOC
- 대통령경호처
- 포항공과대학교
- 한양대학교
- 한양사이버대학교
- 한남대학교
- 수원대학교
- 마산대학교
- 동서대학교
- 경성대학교

# 프로젝트 목표
MOOC 형태로 제공되는 강좌들을 주제별, 또는 분야별로 Catalog 단위로 묶어서 사용자에게 제공하는 Course Catalog LMS(Learning management system) 웹 서비스를 제작하는 것을 목표로 한다.

1. Course Catalog의 과목들은 기존 자사 LMS(LearningX)와 연계되어야 한다.
2. MOOC 유형뿐 아니라 대학별 **비교과 프로그램** 유형의 강좌도 지원하여 기존 대학의 학사과정과 긴밀하게 연계할 수 있도록 한다.
3. 또한 K-MOOC과 같은 **학점은행제** 유형의 강좌를 지원하여 대학별, 기관별로 학점 이수가 가능토록 한다.
4. 각 카탈로그 및 메인페이지는 Widget 별로 관리되어 사용자가 쉽게 사용할 수 있도록 한다.

# 역할 및 기여
본 프로젝트에서 다음의 역할을 수행하였다.
### 프로젝트 설계
- React 와 PHP 7.2기반의 Laravel 프레임워크를 연결.
- 개발환경 폴더구조 구성 및 Routing rule 설계.
- 할당된 Front UI 범위에 맞는 React component들의 설계.

### Frontend UI 구현
- 카탈로그 운영자 페이지에서 메인/서브 카탈로그 추가 UI.
- 카탈로그 운영자 페이지에서 카탈로그 위젯 추가 UI.
- MOOC형 카탈로그 사용자 UI 중 강좌 리스트 위젯 UI.
- 비교과 카탈로그 사용자 UI 중 프로그램 리스트 위젯 UI.
- 강좌 검색 UI중 학점은행제 강좌 리스트.

### Backend Server 구현
- Laravel을 사용한 사용자 목록, 강좌 목록 Excel Download API 설계 및 구현.
- React와 Excel Download API의 연계.


# 기술 스택
- PHP 7.2
- React

- MongoDB
- Redis
- Apache

### Library
- Laravel

<hr>

# 프로젝트 설명

## 개요
- Course Catalog 서비스란 대학 또는 기관이 제공하는 여러 강좌들을 주제별로 사용자에게 제공하는 LMS 서비스를 말한다. 대표적으로 [Coursera](https://www.coursera.org/)가 있다.
- 각 대학은 자교가 제공하는 강좌들을 일반인 대상으로 공개할 수 있으며, 카탈로그에 속한 강좌를 모두 수료할 경우 수료증을 발급할 수 있다.
- Course Catalog는 다수의 Main Catalog와 Main Catalog에 속한 Sub Catalog들로 구성된다.
    - 예) Main Catalog: POSTECHx
    - 예) Sub Catalog: 온라인 지식나눔, 예비 Postechian 프로그램 등
- 웹 UI는 다은 3가지 위젯들로 구성된다. 대학의 운영자가 적절히 위젯별로 메인 페이지를 구성할 수 있다.
    - 카탈로그 위젯
    - 게시판 위젯
    - 강좌 리스트 위젯
- Course Catalog는 `MOOC형 카탈로그`와 `비교과형 카탈로그`, 그리고 `학점 은행제`로 구분된다.

#### MOOC형 카탈로그
- 온라인 강좌들로 이루어진 카탈로그이다.
- 조건에 부합하면 신청, 취소를 자유롭게 할 수 있다.

#### 비교과형 카탈로그
- 학생이 신청을 하고 운영자가 신청, 반려, 대기를 결정한다.
- 신청시작일, 마감일, 마감인원이 존재한다.
- 경우에 따라 신청서를 온라인 상으로 제출해야 한다.

#### 학점 은행제
- 교수자는 각 강좌별 '학점'을 설정할 수 있다.
- 강좌별 제한인원이 있으며, 팀별 신청은 불가능하다.
- 나머지는 MOOC형 카탈로그와 동일하다.

## 기존 상황
- 기존의 비교과 프로그램은 대학별 개별 공지나 오프라인을 통해 이뤄졌기에 학생 참여도가 저조했다.
- Coursera, Udemy등으로 시작된 MOOC 플랫폼의 성공으로 국내 대학들의 Course Catalog 서비스에 대한 needs가 존재했다.
- Xinics의 LMS 솔루션 `LearningX`는 학사과정을 통섭적으로 관리할 수 있지만, 강좌 신청 기능 및 학점 설정기능은 부재한 상태이다.

## 도입 효과 및 예상 효과
- 대학들은 정규 학사과정 이외에도 학생들이 참여할 수 있는 여러 비교과 프로그램을 쉽게 생성할 수 있었고, 이에 따라 학생 역량을 크게 증진한다.
- K-MOOC, 포항공과대학 및 한양대학교를 비롯한 유수 기관들이 MOOC 플랫폼을 운영함에 따라 전문 지식의 대중화에 기여한다.
- 한국형 MOOC 시스템의 청사진을 선제적으로 제시함으로써 국내 온라인 교육산업 측면에서 유의미한 플랫폼을 건설한다.

<hr>

# 프로젝트 결과

## 카탈로그 메인
![Login Main](/images/portfolio/coursecatalog/coursecatalog-main-2.jpg)

## 카탈로그 운영자
![Admin Main](/images/portfolio/coursecatalog/coursecatalog-admin.jpg)

## MOOC 메인 카탈로그
![Catalog Main](/images/portfolio/coursecatalog/coursecatalog-main-catalog.jpg)

## MOOC 서브 카탈로그
![Catalog Sub](/images/portfolio/coursecatalog/coursecatalog-sub-catalog.jpg)

## 비교과 카탈로그
![Compare](/images/portfolio/coursecatalog/coursecatalog-compare.jpg)

## 카탈로그 검색
![Catalog Search](/images/portfolio/coursecatalog/coursecatalog-search.jpg)



