## KIST
### [생육 환경 최적화 경진대회](https://dacon.io/competitions/official/235897/overview/description)

![image](https://user-images.githubusercontent.com/91044039/169456529-13facc71-63ab-4cea-9c78-51ba36899617.png)

## Analytics
### [통계분석을 활용한 생육정도 추정 정량 지표](https://dacon.io/competitions/official/235897/codeshare/4955?page=1&dtype=recent)

### 목표
> 적상추 데이터 활용 생육정도를 알 수 있는 정량 지표 발굴
> - 각 데이터를 측정한 날짜를 통해 0~100%로 수치화한것을 target으로 정하여 생육 정도를 알 수 있는 정량지표를 발굴
> 
> target : 0%
> 
> ![download](https://user-images.githubusercontent.com/91044039/169457498-0979b87b-6a6d-4965-a709-b49433903d2c.png)
> 
> target : 30%
> 
> ![download](https://user-images.githubusercontent.com/91044039/169457586-34631113-8008-48fd-845d-7833fb9b2584.png)
> 
> target : 60%
> 
> ![download](https://user-images.githubusercontent.com/91044039/169457604-e06adc91-22f4-4b1f-8da7-fd2d99868929.png)
>
> target : 90%
>
>![download](https://user-images.githubusercontent.com/91044039/169457770-5be531b5-fd89-4f0a-8ce9-dce2fb56528c.png)

### 데이터
> ![image](https://user-images.githubusercontent.com/91044039/169458070-adac835d-387b-4aac-a9bc-66479009890b.png)
> - 환경 데이터를 사용하여 생육 정도를 나타내는 target을 예측

### 상관분석
> ![image](https://user-images.githubusercontent.com/91044039/169458736-bf0faa97-3bbb-420b-8350-013a9768cb45.png)
> 
> ...
> 
> ![image](https://user-images.githubusercontent.com/91044039/169458775-eaff4250-3ae2-454f-af86-b17774119c70.png)
> 
> 상관계수 0.3 미만인 변수 삭제
> 
> - 다중 선형회귀 모형 결과
> 
> ![image](https://user-images.githubusercontent.com/91044039/169458927-84d9af1c-0142-4f9d-a311-5f557b541c8e.png)

### Stepwise Feature Selection
> ![image](https://user-images.githubusercontent.com/91044039/169459207-9573ae34-f352-4730-9fa3-6858a3ae2b1c.png)
> 
> ![image](https://user-images.githubusercontent.com/91044039/169459233-c7760c15-a7bd-4a8e-8559-f5b8a9d3e4a3.png)
> - Stepwise를 통해 선별된 변수
> 
> ![image](https://user-images.githubusercontent.com/91044039/169459288-314b35d9-9ecb-4ec7-aa1d-9bc8355174d6.png)

### VIF(다중공선성)
> ![image](https://user-images.githubusercontent.com/91044039/169463278-fd4f6c23-e211-43ea-b6bf-120bd2be3555.png)
> 
> - 서로 강한 상관 관계를 갖는 변수 존재
> 
> ![image](https://user-images.githubusercontent.com/91044039/169463410-bfd3cbff-4259-4ece-9b8f-233b37e39928.png)
> 
> - 다중공선성을 방지하기 위해 VIF를 계산하여 다중공선성이 존재하는 변수 제거
> 
> ![image](https://user-images.githubusercontent.com/91044039/169465245-44e7cc2d-d53e-4e4e-8472-6caa76997d49.png)
> 
> - VIF가 10을 초과하는 변수를 Stepwise 방식으로 제거
> 
> ![image](https://user-images.githubusercontent.com/91044039/169463566-bc653e7a-5094-4c8b-bd1e-b329da14884c.png)
> 
> ![image](https://user-images.githubusercontent.com/91044039/169465358-fd9affc5-0685-43ce-8648-e70dd2df1ebe.png)
> 
> - 최종 선별된 변수

### 모델
> ![image](https://user-images.githubusercontent.com/91044039/169463817-afbfb70a-531b-44fd-bf05-f6e81c39002a.png)
> 
> - 최종 선별된 변수로 모델링

### 모델 검증
> ![image](https://user-images.githubusercontent.com/91044039/169464031-584672ad-dbea-4f37-93f2-a79e0cfef89e.png)

### 결론
> ![image](https://user-images.githubusercontent.com/91044039/169464073-5d2363d7-a00f-48c0-bcb9-95b3bd705306.png)
> - 통계적 방법으로 도출된 위 식을 활용하여 식물의 생육 정도를 추정할 수 있는 정량 지표  


## Algorithm

- 목적

청경채 사진과 환경 데이터를 활용한 잎면적 예측 알고리즘 개발

- 데이터
    1. 이미지 데이터

![image](https://user-images.githubusercontent.com/91044039/169959327-445313ae-05a3-4f6d-a2e2-840e076f35da.png)

![image](https://user-images.githubusercontent.com/91044039/169959350-9e14e8dc-bae0-4595-a512-8b9273a53799.png)

1. 환경 데이터
- 촬영 된 시각으로부터 1일간 1분 간격으로 측정된 환경정보 데이터
    
![image](https://user-images.githubusercontent.com/91044039/169959375-e8c080b2-b90b-4220-b966-18e2a01e0a50.png)
    
2. label
- 해당 이미지 파일명
- 해당 이미지가 촬영된 시점으로부터 1일 후의 잎 면적(중량)
- 전처리
train의 모든 csv파일의 열별 최소 최대치를 찾아서 dict로 저장
해당 dict를 사용하여 MinMaxScaling

데이터 경로를 데이터프레임 형태로 구성 target은 weight
    
![image](https://user-images.githubusercontent.com/91044039/169959406-e77f98e5-402c-49aa-aa83-a6994623cb76.png)
    

       이미지, 메타데이터, 타겟을 반환하는 커스텀 데이터셋 정의

        이미지 데이터 변환
         - 사이즈변환, 노멀라이징, 텐서 변환

- 이미지 변환 적용한 데이터 셋
    
![image](https://user-images.githubusercontent.com/91044039/169959419-0d9949d3-1f4c-4e45-b53b-14bc514d00ab.png)
    
- 모델링
5 fold로 모델을 fine-tuning 한 후 voting ensemble
    - Model
        - CNN과 RNN을 결합한 모델
        (CNN: Convnext / RNN: LSTM)
    - Optimizer
        - Adam
    - Scheduler
        - LambdaLR
    - Criterion
        - L1Loss (MAE)
- 결과
    
![image](https://user-images.githubusercontent.com/91044039/169959437-3f0903f2-165e-4e91-8de5-f807a5bdddae.png)
