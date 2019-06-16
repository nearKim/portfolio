---
layout: post
categories: posts
title: 학생 종합성적부 LTI 개발
subtitle: 학기 종료후 학생 성적 평가 및 조정을 용이하게 하기 위한 종합성적부 LTI(Learning Tools Interoperability) 개발
featured-image: /images/portfolio/learningx/totalgradebook/gradebook-main.jpg
tags: [business, web]
date-string: MAY, 2019
---


# 요약
- 개발자: 김인근, 이주희 (Xinics 개발팀)
- 개발 기간: 2019.05 ~ 2019.06 (약 3주)
- Github Repository: Private

# 도입 기관
- 동서대
- 마산대
- 한남대

# 프로젝트 목표
학기 종료 후 교수가 학생의 성적을 평가할 때, Xinics가 제공하는 LMS(Learning management system)인 LearningX에 등록된 과제, 퀴즈 및 성적 데이터와 각 대학별 설정한 등급 기준을 기반으로 학생의 성적을 자동부여해주는 종합성적부 LTI를 개발하는 것을 목표로 한다. 교수는 학생별 가산점(또는 감점)을 통하여 개별 성적을 조정할 수 있다.

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
- 모든 대학은 대학별 성적 등급 부여기준을 가지고 있다. 교수는 기준이 허용하는 범위 내에서 자율적으로 성적 부여가 가능하다.
- 모든 대학은 대학별 F등급 부여 기준을 가지고 있다. 교수는 F등급 부여 기준이 허용하는 범위 내에서 자율적으로 F등급 기준을 설정할 수 있다.
- 모든 과목은 절대평가, 상대평가 중 하나를 선택하여 평가해야 한다.
- LearningX LMS는 오픈소스인 `Canvas`를 기반으로 하고 있고, Canvas는 외부개발사들이 LTI의 형태로 외부도구를 부착하는 것을 허용하고 있다.
- 종합성적부를 LMS에 적용하기 위해서는 LTI 형태로 개발해야 한다.


## 기존 상황
- 기존에는 LearningX를 통해 교육과정 관리를 진행하고 각 학생의 과제, 퀴즈, 출석별 성적을 조정하고 열람할 수 있었지만, 최종 등급을 부여하여 기능은 존재하지 않았다.
- 따라서 교수들은 각 대학별로 이미 존재하는 LMS가 아닌 외부 학사관리도구를 통해서 성적을 직접부여해야 했는데, 대부분 외부도구는 사용이 불편하였다.
- 교육과정 관리를 LearningX를 통해 진행하므로, 종합성적산출 및 등급부여를 LearningX를 통해 한번에 해결하고자 하는 needs가 존재했다.

## 예상 효과
- 성적부여에 있어서 교수들의 편의가 증진된다.
- 성적부여에 있어서 학사관리와 교육과정 관리도구가 통합되므로 대학 단과대학 운영자의 편의가 증진된다.

<hr>

# 프로젝트 결과

## 상대평가
![Relative](/images/portfolio/learningx/totalgradebook/gradebook-relative.gif)

## 절대평가
![Absolute](/images/portfolio/learningx/totalgradebook/gradebook-absolute.gif)

## 가산점 조정
![Extrascore](/images/portfolio/learningx/totalgradebook/gradebook-extrascore.gif)

