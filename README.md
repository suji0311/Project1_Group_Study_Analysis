Note: The dataset uploaded here is a partially sampled and anonymized version.


# BDA 11th Cohort Group Activity Dropout Analysis

## 1. Problem Statement

This project analyzes dropout behavior in group study activities 
to identify key risk factors and propose data-driven operational strategies 
to reduce group dissolution.

The primary objective is to distinguish between individual-level risk 
and structural risk within group operations.

---

## 2. Dataset Overview

- Total observations: 1,314 participants
- Target variable:
  - `group_leave` (0 = stay, 1 = leave)

### Key Features:
- `score_q` : Initial performance quartile
- `on_offline` : Participation type (Online / Offline)
- `leader_left` : Whether the group leader dropped out
- `age_sd` : Age diversity within group
- `group_size` : Group size

---

## 3. Analytical Methods

The following analytical approaches were applied:

- Exploratory Data Analysis (EDA)
- Chi-square tests (Hypothesis Testing)
- Logistic Regression (Odds Ratio + 95% Confidence Interval)
- Decision Tree Analysis

---

## 4. Key Findings

### ① Leader Dropout as a Structural Risk Trigger

- Odds Ratio = **11.93**
- 95% CI = [7.45, 19.11]
- p < 0.001

Groups where the leader dropped out showed 
approximately 12 times higher risk of group dissolution.

Leader dropout is identified as the strongest structural risk factor.

---

### ② Online Participation Increases Dropout Risk

- Odds Ratio = **1.69**
- 95% CI = [1.11, 2.58]
- p = 0.015

Online groups exhibit significantly higher dropout risk 
compared to offline groups.

---

### ③ Initial Performance is Not an Independent Risk Factor

After controlling for structural variables,
initial score quartile showed no significant independent effect.

This suggests structural instability outweighs individual performance differences.

---

## 5. Operational Strategy Recommendations

Based on the findings:

- Implement early detection monitoring for leader instability.
- Establish intervention protocols immediately after leader dropout.
- Strengthen monitoring for online-based groups.
- Design structural risk management rather than individual-based penalties.

---

## 6. Conclusion

Structural factors — particularly leader dropout — 
are significantly more influential than individual performance levels.

Effective group management strategies should prioritize 
structural stability over individual screening.

---

## Future Improvements

- Random Forest / XGBoost for predictive modeling
- Survival analysis for dropout timing modeling
- Early warning risk scoring system


# Group_Study_Analysis
# BDA 11기 조별활동 이탈 분석

# 1. 주제 선정 및 분석 배경
## 1.1 문제 제기
조별활동은 협업 기반 학습 구조임.
개인 학습 대비 지속성 및 완주율 향상 기대됨.
그러나 실제 운영 과정에서 일부 조의 활동 중단, 조원 이탈, 조 해산 현상 반복적으로 발생함.
특히 특정 조에서 이탈이 집중적으로 나타나는 구조 확인됨.
단순 개인 성향 문제가 아니라 구조적 요인 존재 가능성 제기됨.
본 분석은 조별활동 이탈의 핵심 요인 규명 및
이탈 방지 운영 전략 제시 목적임.

## 1.2 분석 목표
다음 세 가지 질문에 답하고자 함.
조별활동 이탈은 개인 요인 중심 문제인가, 구조적 문제인가?
조장 이탈은 조 전체 안정성에 어떤 영향을 미치는가?
온라인 기반 조는 오프라인 대비 구조적 취약성을 가지는가?

## 1.3 분석 방법
다음 절차 수행함.
기초 통계 분석
분위수 분석
카이제곱 가설 검정
로지스틱 회귀 분석 (OR 및 95% CI)
의사결정나무 분석
구조 리스크와 개인 리스크 구분하여 해석함.


# 2. 분석 결과 상세 내용
## 2.1 기초 이탈률
전체 평균 이탈률 약 13% 수준임.
그러나 변수별 분기 시 큰 차이 발생함.

<img width="404" height="426" alt="image" src="https://github.com/user-attachments/assets/761e2b0d-5f78-49bd-b881-21025b3b2053" />


## 2.2 참여 방식별 차이
<img width="689" height="468" alt="image" src="https://github.com/user-attachments/assets/4a43ef6c-1d4e-4a98-bbcf-f3b8414c9e36" />




온라인 조 이탈률이 오프라인 대비 높게 나타남.
로지스틱 회귀 결과:
온라인 OR = 1.69
95% CI: 1.11–2.58
p < 0.05
즉, 온라인 환경에서 이탈 위험 약 1.7배 증가함.

## 2.3 조장 이탈 영향
<img width="447" height="289" alt="image" src="https://github.com/user-attachments/assets/ac918d24-76f1-44af-83db-42abd19957cc" />


가장 큰 차이 관측됨.
조장 유지 조 이탈률 약 8%
조장 이탈 발생 조 이탈률 약 55%
로지스틱 회귀 결과:
<img width="467" height="289" alt="image" src="https://github.com/user-attachments/assets/6ead3854-4ce8-469f-a223-5161efd54fae" />



OR = 11.93
95% CI: 7.45–19.11
p < 0.001
조장 이탈 발생 시 이탈 위험 약 12배 증가함.
구조적 붕괴 신호로 해석 가능함.

## 2.4 초기 점수 영향

<img width="697" height="467" alt="image" src="https://github.com/user-attachments/assets/6f80cb36-197e-4a5e-a3fd-362773c86196" />

초기 점수 분위수 단변량 분석에서는 차이 존재함.
그러나 구조 변수 통제 이후 통계적으로 유의하지 않음.
개인 역량보다 구조 안정성이 더 큰 영향 요인으로 판단됨.

## 2.5 의사결정나무 분석 결과

<img width="950" height="482" alt="image" src="https://github.com/user-attachments/assets/dbcc7d9e-4d35-4d2f-b9ab-7d5a5045bd10" />



최상위 분기 변수는 leader_left로 확인됨.
조장 이탈 여부가 가장 강력한 분기 기준임.
조장 이탈 발생 시 즉시 이탈 클래스 비율 급증함.
구조 리스크 중심 모델 형성됨.


# 3. 결과 해석 및 아이디어 제시
## 3.1 핵심 해석
조별활동 이탈은 개인 문제 중심 구조가 아님.
구조 설계 문제에 가까움.
특히 조장 중심 책임 구조가 단일 실패 지점(single point of failure)로 작용함.
조장 이탈이 곧 조 붕괴로 이어지는 구조 확인됨.

## 3.2 문제의 구조적 본질
현재 구조 특징:
조장 업무 과도 집중
조장 이탈 시 대체 체계 부재
온라인 조 별도 관리 체계 미흡
리스크 분산 설계가 이루어지지 않은 상태임.

## 3.3 운영 전략 제안
## ① 역할 분산 구조 도입
조장 단독 책임 구조 완화 필요함.
일정 관리 담당
자료 정리 담당
공지 담당
조장 외 최소 2인 이상 역할 분산 의무화 필요함.

## ② 부조장 제도 공식화
조장-부조장 2인 체계 기본 구조로 설정 필요함.
조장 이탈 발생 시 부조장 자동 승계 체계 도입함으로써 운영 연속성 확보 가능함.
특히 온라인 조는 필수 적용 대상임.

## ③ 조장 리스크 조기 감지 시스템
활동 점수 및 참여율 기반 조기 경고 체계 도입 필요함.
2주 연속 활동 저조 시 운영진 알림
조장 활동 점수 하위 분위 조 집중 모니터링
사전 개입이 해산 방지에 가장 효과적임.

## ④ 온라인 조 관리 강화
온라인 조는 결속력 약함.
초기 오리엔테이션 강화
월 1회 공식 점검
운영진 중간 개입 제도 도입
구조적 보완 필요함.

## 3.4 전략 방향 요약
이탈 문제는 개인 선별 강화로 해결 불가함.
구조 설계 개선 중심 전략 필요함.
리더십 리스크 분산
대체 가능 구조 구축
온라인 환경 보완
구조 안정성 확보가 핵심임.




