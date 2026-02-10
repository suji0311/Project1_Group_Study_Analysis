

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

## 1. 문제 정의

조별활동 중 이탈을 방지하기 위해
이탈에 영향을 미치는 핵심 요인을 분석하고
운영 전략을 제안한다.

---

## 2. 데이터 개요

- 총 표본: 1,314명
- 주요 변수:
  - group_leave (이탈 여부, 0/1)
  - score_q (초기 점수 분위)
  - on_offline (참여 방식)
  - leader_left (조장 이탈 여부)
  - age_sd (연령 다양성)

---

## 3. 주요 분석 방법

- EDA
- 카이제곱 검정
- 로지스틱 회귀 (OR + 95% CI)
- 의사결정나무

---

## 4. 주요 인사이트

### ① 조장 이탈은 구조 붕괴의 핵심 요인
- OR = 11.93
- 95% CI = [7.45, 19.11]

### ② 온라인 참여는 이탈 위험 증가
- OR = 1.69
- 95% CI = [1.11, 2.58]

### ③ 초기 점수는 독립 효과 없음

---

## 5. 운영 전략 제안

- 조장 리스크 조기 감지 시스템 도입
- 온라인 조 모니터링 강화
- 조장 이탈 발생 시 즉시 개입 프로토콜 구축

---

## 6. 결론

조장 이탈이 가장 강력한 구조적 위험 요인이며,
운영 전략은 개인 특성보다 구조 관리 중심으로 설계되어야 한다.

