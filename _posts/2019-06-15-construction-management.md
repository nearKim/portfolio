---
layout: post
categories: posts
title: Schedule uncertainty analysis system development in EPC project
subtitle: 건설계획에서의 Monte carlo 시뮬레이션을 위한 건설데이터 선별 및 통계값 계산을 용이하게 하고, 시뮬레이션 결과를 시각화하여 보여주는 웹기반 시스템을 제작하여 Amazon EC2에 배포한다
featured-image: /images/portfolio/construction/construction-management-main.jpg
tags: [publication, patent]
date-string: FEBRUARY, 2019
---


# 개요
- 개발 기간: 2019.02 ~ 2019.05
- [Github Repository: Construction Management](https://github.com/nearKim/ConstructionManagement)
    - 개발 브랜치: master
    - 배포 브랜치: production

# 특허
박문서, 윤인석, 김인근 (2019.05.19). **건설 프로젝트 공정 스케쥴 데이터 관리 및 분석 시스템**. 대한민국, 제 C-2019-014217호.

# Working Paper
TODO


# 프로젝트 목표
본 프로젝트는 다음 3가지 모듈을 포함한 `통합 건설 데이터 관리 웹 어플리케이션`을 제작하고 Amazon EC2 인스턴스에 배포하여 연구자에게 서비스하는 것을 목표로 한다.
1. **Storage Module**: SRA에서의 Monte-Carlo simulation을 위해 as-built data를 로드하고, 데이터를 선별하여 DB에 저장.
2. **Allocation Module**: 저장된 DB의 데이터들을 현재 추정하고자 하는 Planned Schedule에 할당하여 JAVA 기반의 시뮬레이션 모듈이 이해할 수 있는 형식으로 변환.
3. **Analysis Module**: Simulation 모듈을 통해 생성된 최종 결과 4가지 Index에 따라 동적으로 시각화하여 사용자에게 제공.


# 프로젝트 설명
- 건설 산업에서 불확실성과 리스크 관리는 대단히 중요한 주제이다.
- 건설 프로젝트는 다수의 스케쥴(Schedule)로 이뤄져 있고 스케쥴의 공기(Duration) 리스크를 관리하는 여러가지 방법론이 소개되었다. 이를 통칭하여 **Schedule Risk Analysis(SRA)**라 한다.
- SRA를 실행함에 있어서 과거의 연구자들은 Monte-Carlo simulation(MCS)을 사용하였다. MCS에서는 Activity duration을 Probability distribution function(PDF)로 표현한 Random variable로 취급한다.
- 성공적인 SRA를 위해서는 정확한 PDF가 필요하다. 일반적으로 '전문가 경험(Expert experience)'과 '과거 데이터'(As-built data)가 PDF 추정에 큰 영향을 미친다고 알려져 있다.
- 많은 연구자들은 bias와 주관성 등의 이유로 as-built data 기반 추정이 expert experience기반 추정보다 정확하다고 주장한다. 또한 데이터만 충분하다면 데이터 분석 기법의 발달로 인해 보다 예측력이 뛰어난 결과를 도출할 수 있음이 증명되었다.
- 이에 따라 SRA를 실행함에 있어서 **Data Availivity**가 가장 중요한 역할을 한다는 점을 알 수 있다.
- 건설 업계에서 지금까지 수집한 건설 데이터는 '데이터 파편화', '프로젝트의 복잡도', '표준화의 부재'등의 이유로 매우 낮은 Data availivity를 보여준다.
- 따라서 더욱 효율적인 SRA 결과를 얻기 위해서 `효율적인 통합 건설 데이터 관리 솔루션`을 제작하는것이 필수적이다.

### Project Framework
![Research Framework](/images/portfolio/construction/framework.jpg)

<hr>

# 프로젝트 결과

### Storage Module
![Storage Module](/images/portfolio/construction/storage-module.jpg)

### Allocation Module
![Allocation Module](/images/portfolio/construction/allocation-module.jpg)

### Analysis Module
![Analysis Module](/images/portfolio/construction/visualization.jpg)

<hr>

# 기술 스택
- React
- Django
- Django REST Framework
- gunicorn
- nginx
- Amazon EC2

### Library
#### Python
- pandas
- numpy
- [django-webpack-loader](https://github.com/owais/django-webpack-loader)

#### React
- [react-vis](https://github.com/uber/react-vis)
- reactstrap
- react-bootstrap-table2



