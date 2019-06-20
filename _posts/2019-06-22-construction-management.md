---
layout: post
categories: posts
title: Schedule Risk Analysis system development
subtitle: 건설 프로젝트 계획단계에서 공정 리스크 분석에 필요한 과거 실적 데이터를 저장 및 관리하고, 이를 활용하여 새로운 계획 공정표에 대한 리스크 분석을 수행하여 각 작업 별 결과를 시각화하여 보여주는 웹 기반 시스템
featured-image: /images/portfolio/construction/construction-management-main.jpg
tags: [publication, patent, web]
date-string: FEBRUARY, 2019
---


# 요약
- 개발자: 김인근
- 연구자: 윤인석
- 개발 기간: 2019.02 ~ 2019.05 (약 4개월)
- [Github Repository: Construction Management](https://github.com/nearKim/ConstructionManagement)
    - 개발 브랜치: master
    - 배포 브랜치: production
- API 명세: TODO

# 지식재산권
박문서, 윤인석, 김인근(발명자). 2019.05.19. **건설 프로젝트 공정 스케쥴 데이터 관리 및 분석 시스템**. 대한민국, 제 C-2019-014217호.

# Working Paper
**System Architecture for Enhancing Data Availability in Schedule Risk Analysis Based on Historical Project Data**
Target Journal: Automation in Construction (Impact Factor : 4.032)

# 프로젝트 목표
본 프로젝트는 [ISARC](https://isarc2019.org/)에서 발표된 "Schedule Uncertainty Analysis System Framework to Manage and Allocate Historical Data for Industrial Construction Project"<sup>[1](#footnote)</sup>이 제시하는 바를 웹 서비스로 구현하는 것을 목표로 한다.

이에 따라 다음 3가지 모듈을 포함한 `실적 데이터 기반의 공정 리스크 분석 웹 어플리케이션`을 제작하고 Amazon EC2 인스턴스에 배포하여 논문의 연구자에게 서비스한다.

1. **Storage Module**: 건설 프로젝트의 실적 공정 데이터 관리를 위해 as-built data를 로드하고, 작업 데이터를 선별하는 task를 지원하고 그 결과를 DB에 저장.
2. **Allocation Module**: 분석하고자 하는 계획 공정표의 작업들과 저장된 DB의 실적 데이터들을 연계하고 연계된 정보를 시뮬레이션 분석의 입력 값으로 변환.
3. **Analysis Module**: 사용자가 연계한 정보를 바탕으로 리스크 분석(몬테카를로 시뮬레이션)을 수행하고 결과의 종합 정보와 작업 별로 4가지 종류의 risk index를 시각화하여 사용자에게 제공.


<a name="footnote">1</a>: Yoon et al. "Schedule Uncertainty Analysis System Framework to Manage and Allocate Historical Data for Industrial Construction Project". ISARC. Proceedings of the International Symposium on Automation and Robotics in Construction. Vol. 35. IAARC Publications, 2019.

# 역할 및 기여
본 프로젝트의 모든 개발을 수행하였다.

# 기술 스택
- React

- Django
- Django REST Framework

- gunicorn
- nginx
- Amazon EC2

- Sentry

### Library
#### Python
- pandas
- numpy
- [django-webpack-loader](https://github.com/owais/django-webpack-loader)

#### React
- [react-vis](https://github.com/uber/react-vis)
- reactstrap
- react-bootstrap-table2


<hr>

# 프로젝트 설명

## 배경
- 건설 프로젝트는 타 산업 대비 상대적으로 긴 프로젝트 기간과 규모로 인하여 공정에 대한 리스크 분석에 대한 중요성이 강조되어 왔음.
- 리스크 분석을 위한 대표적인 방법 중 하나는 Monte-Carlo Simulation(몬테카를로 시뮬레이션)이며, 이를 활용한 리스크 분석을 Schedule Risk Analysis(SRA)라 함.
- SRA 수행을 위한 입력 값은 리스크 분석의 대상이 되는 공정표의 작업들의 “확률분포”임.
- 확률 분포를 도출하는 방법은 전문가의 경험(Expert experience)을 바탕으로 한 방법과 과거 데이터(As-built data)를 활용하는 방법이 있음.
- 전문가의 경험을 통한 도출은 편향, 주관성이 존재하기 때문에 많은 연구자들은 과거 데이터 기반의 SRA가 더 신뢰도 있는 방법이라고 주장하고 있음.

## 문제 상황
- 신뢰성 있는 SRA를 위해서는 신뢰성 있는 실적 데이터가 기반되어야 함을 알 수 있음.
- 이는 실적 공정 데이터에 대한 Availability가 건설 프로젝트의 공정 리스크 분석에 있어서 중요한 역할을 함을 의미함.
- 하지만 건설 산업에서는 ‘타 산업 대비 높은 수준의 프로젝트 복잡도’, ‘프로젝트 특성의 높은 이질성으로 인한 표준화의 어려움’ 등으로 인해 Data availability가 상대적으로 낮음.
- 이로 인해 유의미한 SRA 수행이 어려우며, 건설 프로젝트 관리에 있어 리스크 분석의 중요성에도 불구하고 실무에서는 리스크를 identify하는데 그치고 있음.

## 기존 SW 현황
- 관련 업계의 분석용 소프트웨어로는 Oracle사의 [Primavera](https://www.oracle.com/industries/construction-engineering/primavera-products/)와 Microsoft사의 [MS project](https://products.office.com/en/project/project-and-portfolio-management-software)가 있음.
- 위 SW들은 리스크 분석기능을 지원하기는 하나, 전문가 경험 기반 분석에 더욱 용이함.
- 실적 데이터 기반 분석을 위해서는 이러한 데이터를 관리할 수 있는 모듈이 필요하나 이러한 기능을 갖춘 소프트웨어는 거의 존재하지 않음.

## 예상 효과
- 본 웹 어플리케이션을 통해 과거 공정 데이터를 관리할 수 있는 모듈을 제공하여 공정 리스크 분석을 위한 data availability를 획기적으로 개선함 .
- 이러한 모듈을 기반으로 실적 데이터 기반의 리스크 분석 수행이 가능하도록 하여 실무에서의 리스크 분석의 용이성과 신뢰성을 향상시킴.



### Project Architecture
#### Research Framework
![Research Framework](/images/portfolio/construction/framework.jpg)

#### Database Architecture
![Database Architecture](/images/portfolio/construction/db-schema.jpg)

<hr>

# 프로젝트 결과

### Storage Module
![Storage Module](/images/portfolio/construction/storage-module.jpg)

### Allocation Module
![Allocation Module](/images/portfolio/construction/allocation-module.jpg)

### Analysis Module
![Analysis Module](/images/portfolio/construction/visualization.jpg)


