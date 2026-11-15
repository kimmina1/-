flowchart LR
  %% 주요 노출 및 결과
  Stress["스트레스 인지 여부 (노출)"]
  Sleep["하루 평균 수면시간 (결과)"]

  %% 인구사회·경제적 요인 (교란변수 후보)
  Age["연령"]
  Sex["성별"]
  Mar["결혼 여부"]
  Inc["소득 4분위수"]
  Edu["교육수준"]
  Econ["경제활동 상태 (EC1_1)"]
  WorkHr["주당 평균 근로시간 (EC_wht_23)"]
  WorkTp["근로형태 (EC_wht_5)"]

  %% 건강행태 및 정신건강 요인
  Htn["고혈압 의사진단 (DI1_dg)"]
  Smoke["현재 흡연 (sm_presnt)"]
  Drink["1년간 음주빈도 (BD1_11)"]
  Pa["유산소 신체활동 (pa_aerobic)"]
  Phq["우울 PHQ-9 점수"]
  Gad["불안 GAD-7 점수"]

  %% 인구사회·경제적 배경 -> 노출/결과/근로·건강행태
  Age --> Stress
  Age --> Sleep
  Age --> Mar
  Age --> Edu
  Age --> Econ
  Age --> Htn
  Age --> Smoke
  Age --> Drink
  Age --> Pa

  Sex --> Stress
  Sex --> Sleep
  Sex --> Econ
  Sex --> WorkTp
  Sex --> Smoke
  Sex --> Drink

  Mar --> Stress
  Mar --> Sleep
  Mar --> Inc

  Edu --> Inc
  Edu --> Econ
  Edu --> WorkTp
  Edu --> Stress
  Edu --> Sleep

  Inc --> Stress
  Inc --> Sleep
  Inc --> Htn
  Inc --> Pa

  Econ --> WorkHr
  Econ --> WorkTp
  Econ --> Stress
  Econ --> Sleep

  WorkHr --> Stress
  WorkHr --> Sleep
  WorkTp --> Stress
  WorkTp --> Sleep

  %% 노출 -> 수면 및 잠재적 매개/정신건강·행태 경로
  Stress --> Sleep
  Stress --> Phq
  Stress --> Gad
  Stress --> Smoke
  Stress --> Drink
  Stress --> Pa

  Phq --> Sleep
  Gad --> Sleep
  Smoke --> Sleep
  Drink --> Sleep
  Pa --> Sleep
  Htn --> Sleep
