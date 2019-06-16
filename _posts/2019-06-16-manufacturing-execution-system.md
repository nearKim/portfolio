---
layout: post
categories: posts
title: 웹기반 사내 생산관리 시스템(MES, Manufacturing Execution System) 개발
subtitle: 국제 시장에서의 제품 생산성 재고를 위한 부품 통합 생산관리 시스템의 백엔드을 Django REST framework기반으로 제작한다
featured-image: /images/portfolio/mes/db-schema.jpg
tags: [business, web]
date-string: DECEMBER, 2017
---


# 요약
- 개발자: 김인근, 신동주
- 개발 기간: 2017.12 ~ 2018.02 (약 3개월)
- Github Repository: Private
- 웹사이트: Private
- 현황: 현재 사용중

# 프로젝트 목표
본 프로젝트는 (주)아카온과 협력업체들에 특화된 생산관리시스템(MES)를 구축함을 목표로 한다. 시스템은 다음 3가지 핵심 기능을 포함한다.

1. 재고관리: 위치, 개수, 현황 등
2. 배송관리: 송달이력, 배송 확인기능, 책임자 메일링 등
3. 회계관리: 국가별 차등세율에 따른 세금계산 등


# 기술 스택
- Django
- Django REST Framework

- gunicorn
- nginx

- Amazon EC2
- Amazon S3
- Amazon RDS
- Amazon ECS, ECR

- Docker
- Vagrant


<hr>

# 프로젝트 설명

## 개요
- (주)아카온은 인공지능 로봇 Musio를 제작하는 기업으로 로봇 제작에 필요한 부품을 외부 협력업체로부터 조달하여 사용한다.
- 협력업체는 대만, 일본 등지에 존재하며 이에 따라 부품 주문시 통관절차가 존재한다.
- 협력업체로부터 받은 부품을 다른 협력업체로 송달해야 하는 경우도 존재한다.
- 세금 등의 이유로 통관시 부품의 갯수가 대단히 중요한데, 누락이 존재하면 통관 자체가 되지 않을 수 있다.


## 기존 상황
- 모든 부품의 종류, 이력 등을 엑셀로 관리하였다.
- 협력업체는 X개를 전송하였다고 주장하는데, 도착한 부품에 누락분이 존재하는 경우가 대단히 빈번하였다.
- 이에 따라 통관이 되지 않거나, 통관중 임시 대기상태로 전환되어 생산에 차질이 생기는 경우가 많았다.
- 생산팀의 리소스가 과다하게 투여되었다.
- 새로운 부품의 추가에 따른 비용이 크게 증가하였다.

## 예상 효과
- 협력업체의 실수에 대한 근거를 보강하여 책임 소재를 명확히 한다.
- 도착한 물품수를 일일히 세지 않고 자동으로 현황을 파악한다.
- 통관에 따른 세율을 선제적으로 파악하여 회계에 도움을 준다.

<hr>

# 프로젝트 설계

### Database Schema
![Main Page](/images/portfolio/mes/db-schema.jpg)

