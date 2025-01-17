---
layout: single
title: 논리적 모델과 물리적 모델
---

# 논리적 모델(Logical Model)
- 논리적 모델은 데이터베이스의 구조와 관계를 추상화하여 표현한 개념적인 모델이다.
- 개체(Entity)와 속성(Attribute), 관계(Relateionship) 등을 사용하여 데이터의 구조를 표현한다.
- 논리적 모델은 개발자나 사용자가 데이터를 이해하고 조작하는데 도움을 주는 역할을 한다.
- 대표적인 논리적 모델로는 관계형 데이터베이스에서 사용되는 ER(Entity-Relationship) 모델이 있다.
- 실제 구성했던 모델 구조
![논리모델](https://github.com/DJSon2/about-me/assets/124123956/3131636d-62cf-40c2-bc1c-f7e01e0807f8)

# 물리적 모델(Physical Model)
- 물리적 모델은 논리적 모델을 실제 데이터베이스 시스템에 구현하기 위한 모델이다.
- 데이터베이스 시스템의 특정 기술이나 플랫폼에 맞추어 데이터의 저장, 접근, 성능 등을 고려하여 설계한다.
- 물리적 모델은 테이블(Table), 인덱스(Index), 제약조건(Constraint) 등과 같은 요소들을 사용하여 데이터베이스를 구성한다.
- 물리적 모델은 데이터베이스 시스템의 성능을 최적화하고, 데이터의 저장과 검색을 효율적으로 처리할 수 있도록 한다.
- 대표적인 물리적 모델로는 관계형 데이터베이스에서 사용되는 B-tree 인덱스, 파티셔닝, 클러스터링 등이 있다.
- 실제 구성했던 모델 구조
![물리모델 (2)](https://github.com/DJSon2/about-me/assets/124123956/ff582c3e-fa81-45b4-bb2e-ef18e9fe2fe1)


# 논리적 모델과 물리적 모델의 역할
- 논리적 모델은 데이터의 구조와 관계를 표현하며, 개념적인 이해를 도와준다.
- 물리적 모델은 논리적 모델을 실제 데이터베이스 시스템에 구현하여 데이터의 저장과 접근을 관리하고 최적화한다.
- 이러한 모델링 단계를 통해 데이터베이스는 구조화되고 효율적으로 관리될 수 있다.