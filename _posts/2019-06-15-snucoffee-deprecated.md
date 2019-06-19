---
layout: post
categories: posts
title: 서울대학교 중앙 커피동아리 Caffein 웹사이트 제작 (Deprecated)
subtitle: 서울대학교 중앙 커피동아리 Caffein이 사용할 웹사이트를 동아리 내규에 맞춰 제작한다
featured-image: /images/portfolio/caffein/caffein-main.jpg
tags: [personal, web]
date-string: JULY, 2018
---


# 요약
- 개발자: 김인근, 박광덕
- 개발 기간: 2018.07 ~ 2019.01 (약 7개월)
- [Github Repository: Caffein2](https://github.com/nearKim/Caffein2)
    - 개발 브랜치: master
    - 알파 브랜치: alpha
    - 배포 브랜치: prod
- 웹사이트: <a style="background-color: pink;" href="https://www.snucoffee.com">SNU Coffee</a>
- 현황: 동아리 운영 상황 변화에 따른 **프로젝트 중단**. 신입들을 위한 동아리 설명 Demo용 페이지로 전환.

# 프로젝트 목표
본 프로젝트는 [Karmo HTML5 템플릿](https://technext.github.io/karmo/index.html)을 기반으로, 서울대학교 중앙 커피동아리 Caffein 회원들이 동아리 활동에 사용할 웹사이트를 제작하는 것을 목표로 한다.


# 기술 스택
- Django

- CSS
- AJAX
- Jquery

- gunicorn
- nginx

- Amazon EC2
- Amazon S3
- Amazon RDS
- Amazon ECS, ECR
- Docker
- Amazon CodePipeline
- Amazon Codebuild
- Amazon Systems Manager - Parameter Store

- Sentry

### Library
- imagekit
- [django crispy forms](https://github.com/django-crispy-forms/django-crispy-forms)
- [django user agents](https://github.com/selwin/django-user_agents)
- [django admin bootstrap](https://github.com/douglasmiranda/django-admin-bootstrap)

### 3rd Party
- [NaverMap javascript API](https://developers.naver.com/docs/map/javascriptv3/)
- [Facebook Groups API](https://developers.facebook.com/docs/groups-api/)

<hr>

# 프로젝트 설명

## 개요
- Caffein은 매 학기 시작 약 1달 전부터 신입회원, 기존회원 가입신청을 받으며 가입신청시 간단한 설문과 자기소개를 적어야 한다. 그 후 회비 입금이 확인되면 가입이 완료된다.
- 기존 회원 1명과 신규회원 2~3명으로 이뤄진 짝지를 매 학기 정해야 한다.
- 학기 중에는 커피모임(커모) 및 커피교육(교육) 및 짝지모임(짝모)가 비정기적으로 열린다.
- 페이스북 그룹 포스팅에 댓글을 다는 것으로 커모, 교육 참가신청이 이뤄진다.
- 어떤 형태로든 모임을 가진 이후 페이스북 그룹에 포스팅해야 한다.
- 각 모임에는 참가 제한인원이 있으며, 언제든지 참석 가/부를 변경할 수 있다. 참가 제한인원을 넘을 경우 대기인원으로 분류된다.
- 모임에 참석한 팀(짝지)들은 운영진이 정한 조건에 따라 점수를 부여받는다.
- 학기 종료시 최고득점을 한 짝지에게는 소정의 상품이 주어진다.

## 기존 상황
- 학기당 가입 신청인원은 평균적으로 200명에서 300명정도이고 모든 절차를 마치고 가입완료되는 인원은 매 학기 약 100명 이상이다.
- 가입신청시 설문과 자기소개는 Google Docs로 관리된다. 새로운 신청이 들어올 때마다 운영진이 일일히 확인해야 한다.
- 짝모의 경우 커모, 교육에 비해 빈도가 압도적으로 많은데, 모두 페이스북 그룹 포스팅으로 관리하므로 커모, 교육 포스팅이 피드에서 밀린다.
- 짝지를 정할 때 엑셀을 이용하는데, 실수로 중복되거나 누락된 경우 수정이 어렵다.
- 커모, 교육, 짝모 참여에 따른 점수부여는 매 학기 달라지며, 학기 종료시 운영진이 페이스북 그룹 포스팅을 일일히 확인하여 점수를 합산한다.
- 즉, 운영진의 리소스가 과다하게 투여된다.

## 예상 효과
- 가입절차를 회비입금을 제외하고 완전자동화함으로써 운영진의 부담을 획기적으로 경감한다.
- 커모, 교육 참가신청 및 제한인원을 개최자가 정할 수 있게 하고, 참가, 대기, 및 취소도 자동화한다.
- 커모, 교육 과 짝모를 보는 View를 분리하여 중요한 공지, 교육의 경우 더욱 많은 회원들에게 도달하도록 한다.
- 점수 산정 역시 서버에서 자동화함으로써 점수로 인해 생기는 시시비비를 사전에 차단한다.
- 메인페이지에 동아리 설명을 추가하여 신입회원 가입기간 회장의 QnA 리소스 투여를 줄이고 미려한 디자인으로 신입회원의 동아리 가입 유인을 제공한다.

## 추가 기능
- 카페 검색기능 및 커모 데이터를 수집하는 페이지를 생성한다.
- 동아리 회원들이 좋아하는 카페 및 커피에 대한 데이터를 수집한다.

<hr>

# 프로젝트 설계

#### Alpha Website
- 정식 배포 전 기능들을 자유롭게 테스트할 수 있는 Alpha 페이지를 구성한다.
- 최대 10명 내외의 인원이 사용할 것이므로 `Heroku`를 통해 구성한다.
- Sentry plugin을 통해 서버 에러 상황을 실시간으로 획득한다.
- Alpha Website: <a href="https://caffein-alpha.herokuapp.com">Caffein-alpha</a>

#### CI/CD Pipeline
- 학기 중 수시로 페이지 변경사항이 있을 것으로 예상되므로 CI/CD 파이프라이닝을 구성한다.
- Amazon 공식 자습서에 제시된 바와 같이 동일하게 구성한다.

![pipeline](https://s3.amazonaws.com/chrisb/CICD-refarch.png)
출처: [아마존 공식 자습서](https://aws.amazon.com/blogs/compute/continuous-deployment-to-amazon-ecs-using-aws-codepipeline-aws-codebuild-amazon-ecr-and-aws-cloudformation)

#### Stress Test
- EC2 micro 인스턴스를 기준으로 부하테스트를 진행한다.
[부하 테스트 결과](https://docs.google.com/spreadsheets/d/1nNDHpzTMru78xJjexV1pvAAOgFVgdpyCjD_EK-Qc51w/edit?usp=sharing)

<hr>

# 프로젝트 결과
### 마이 페이지
![Login Main](/images/portfolio/caffein/login-main.gif)

### 카페 검색
![Cafe Search](/images/portfolio/caffein/cafe-search.gif)

### 사진첩 기능
![Photos](/images/portfolio/caffein/photobooth.gif)

### 커피 모임 생성
![Coffee Meeting](/images/portfolio/caffein/coffee-meeting.gif)

### 공식 모임 / 교육 생성
![Meeting Create](/images/portfolio/caffein/meeting-create.gif)

### 카페인 피드 보기
![Parter Meeting](/images/portfolio/caffein/partner-meeting.gif)

### 운영자 페이지
![Admin Page](/images/portfolio/caffein/caffein-admin.jpg)



