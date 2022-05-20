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
> ...
> ![image](https://user-images.githubusercontent.com/91044039/169458775-eaff4250-3ae2-454f-af86-b17774119c70.png)
> 상관계수 0.3 미만인 변수 삭제
> - 다중 선형회귀 모형 결과
> ![image](https://user-images.githubusercontent.com/91044039/169458927-84d9af1c-0142-4f9d-a311-5f557b541c8e.png)
