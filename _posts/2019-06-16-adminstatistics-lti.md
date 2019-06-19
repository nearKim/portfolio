---
layout: post
categories: posts
title: LMS 운영 통계 LTI 개발
subtitle: 대학 운영자가 상시로 LMS 이용통계를 정량적으로 파악하기 위한 운영 통계 대시보드 LTI(Learning Tools Interoperability) 개발
featured-image: /images/portfolio/learningx/adminstatistics/statistics-main.jpg
tags: [business, web]
date-string: APRIL, 2019
---


# 요약
- 개발자: 김인근, 이주희 (Xinics 개발팀)
- 개발 기간: 2019.04 ~ 2019.05 (약 2주)
- Github Repository: Private

# 도입 기관
- K-MOOC (19년 6월 말 도입)
- 경성대
- 동서대
- 마산대
- 수원대
- 한남대
- 한양대
- 한양사이버대

# 프로젝트 목표
대학의 운영자가 상시로 교수별, 과목별 LMS 이용통계를 정량적으로 집계한 후 시각화하여 보고받을 수 있는 통계 대시보드 LTI를 개발하는 것을 목표로 한다.

1. 성능 향상을 위하여 DB 직접 쿼리하는 방법으로 구현한다.
2. 학과별, 단과대별 운영자를 고려하여 하위계정 운영자도 조회가능해야 한다. 단, 하위계정운영자는 상위계정의 통계자료를 볼 수 없어야 한다.

# 기술 스택
- PHP 7.2
- React
- MongoDB
- Postgresql
- Apache

### Library
#### PHP
- Laravel

#### Javascript
- Kendo Grid

<hr>

# 프로젝트 설명

## 개요
- 교원 평가에 있어서 LMS(Learning management system)의 이용률 및 LMS상에서의 학생 참여도를 평가기준에 산입하는 대학교가 존재한다.
- Xinics가 개발한 LMS인 LearningX가 제공하는 학습 유형 데이터는 MongoDB에, Canvas가 자체 제공하는 학습 유형 데이터는 Postgresql DB에 나눠져서 저장된다.

## 기존 상황
- 대학이 신규 도입한 이후 시스템의 이용통계를 파악하고자 하는 내부적 needs가 존재했다.
- Xinics로 LMS 이용통계 데이터를 요청한 대학에 한하여 DB 직접 쿼리 방식으로 Postgres, Mongo로부터 Excel 추출하여 전달하였다.
- LearningX 도입사가 증가함에 따라 통계자료 요청에 따른 업무 리소스 투여가 급증하였다.

## 도입 효과
- 통계데이터 추출요청이 없어짐에 따라 여타 개발업무에 집중할 수 있게 되었다.
- 각 대학들의 중요한 업무 중 하나인 교원평가에서 객관적이고 정량적인 평가기준을 설정할 수 있게 되었다.

<hr>

# 프로젝트 결과

## 과목별 운영 현황
![Course](/images/portfolio/learningx/adminstatitics/statistics-course.gif)


## 교수별 운영 현황
![Prof](/images/portfolio/learningx/adminstatitics/statistics-prof.gif)

