---
layout: post
categories: posts
title: 차세대 MOOC 플랫폼 Course Catalog 서비스 개발
subtitle: MOOC형 강좌 통합 플랫폼인 Course Catalog 서비스의 Front를 React 기반으로 개발한다
featured-image: /images/portfolio/coursecatalog/coursecatalog-main.jpg
tags: [business project, web]
date-string: DECEMBER, 2018
---


# 요약
- 개발자: Xinics 개발팀 (총 5명)
- 개발 기간: 2018.12 ~ 2019.02 (약 2개월)
- Github Repository: Private

# 도입 기관
- K-MOOC (19년 6월 말 도입)
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
2. MOOC 유형뿐 아니라 대학별 **'비교과 프로그램'** 유형의 강좌도 지원하여 기존 대학의 학사과정과 긴밀하게 연계할 수 있도록 한다.
3. 각 카탈로그 및 메인페이지는 Widget 별로 관리되어 사용자가 쉽게 사용할 수 있도록 한다.


# 기술 스택
- PHP 7.2
- React

- MongoDB
- Redis

### Library
- Laravel

<hr>

# 프로젝트 설명

## 개요
- Course Catalog는 대학 또는 기관이 제공하는 여러 강좌들을 주제별 또는 분야별로 사용자에게 제공하는 LMS 서비스를 말한다. 대표적으로 [Coursera](https://www.coursera.org/)가 있다.
- 각 대학은 자교가 제공하는 강좌들을 일반인 대상으로 오픈할 수도 있으며, 카탈로그에 속한 강좌를 모두 수료할 경우 수료증을 발급할 수 있다.
- Course Catalog는 다수의 Main Catalog와 Main Catalog에 속한 Sub Catalog들로 구성된다.
    - Main Catalog: POSTECHx
    - Sub Catalog: 온라인 지식나눔, 예비 Postechian 프로그램 등
- 웹 UI는 위젯들로 구성된다.
    - 카탈로그 위젯
    - 게시판 위젯
    - 강좌 리스트 위젯
- Course Catalog는 `MOOC형 카탈로그`와 `비교과형 카탈로그`로 구분된다.

#### MOOC형 카탈로그
- 온라인 강좌들로 이루어진 카탈로그이다.
- 조건에 부합하면 신청, 취소를 자유롭게 할 수 있다.

#### 비교과형 카탈로그
- 학생이 신청을 하고 운영자가 신청, 반려, 대기를 결정한다.
- 신청시작일, 마감일, 마감인원이 존재한다.
- 경우에 따라 신청서를 온라인 상으로 제출해야 한다.

## 기존 상황
- 기존의 비교과 프로그램은 대학별 전체공지나 오프라인 공지사항을 통해 이뤄졌기에 학생 참여도가 저조했다.
- Coursera, Udemy등으로 시작된 MOOC 플랫폼의 성공으로 국내 대학들의 Catalog형 서비스에 대한 needs가 존재했다.
- Xinics의 LMS 솔루션 `LearningX`는 학사과정을 통섭적으로 관리할 수 있지만, 강좌 신청 기능은 부재한 상태이다.

## 도입 효과 및 예상 효과
- 대학들은 정규 학사과정 이외에도 학생들이 참여할 수 있는 여러 비교과 프로그램을 쉽게 생성할 수 있었고, 이에 따라 학생 역량을 크게 증진한다.
- K-MOOC, 포항공과대학 및 한양대학교를 비롯한 유수 기관들이 MOOC 플랫폼을 운영함에 따라 전문 지식의 대중화에 기여한다.
- 한국형 MOOC 시스템의 청사진을 선제적으로 제시함으로써 국내 온라인 교육산업 측면에서 유의미한 플랫폼을 건설한다.

<hr>

# 프로젝트 결과
TODO


