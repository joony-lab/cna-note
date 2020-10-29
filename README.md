# cna-note

1. 동기식 호출
order > 결제는 동기식 호출 구현
![image](https://user-images.githubusercontent.com/69283682/97558818-fadc9300-1a1f-11eb-8585-2bb964977187.png)

동기식 설정에 따라 payment 서비스 중단시 500 에러 발생
![image](https://user-images.githubusercontent.com/69283682/97559049-48f19680-1a20-11eb-8ce6-b4e2d6fe91c2.png)

payment 서비스 정상 작동시 정상 결과 출력
![image](https://user-images.githubusercontent.com/69283682/97559248-87875100-1a20-11eb-9e92-f7bd19be6969.png)

2. 비동기 호출
order > delivery비동기식 구현

kafka에서 Delivery 상태 업데이트
![image](https://user-images.githubusercontent.com/69283682/97560098-9c181900-1a21-11eb-8eca-1d71886c5f13.png)

delivery 서비스 down

구매주문 정상 실행
![image](https://user-images.githubusercontent.com/69283682/97561062-ecdc4180-1a22-11eb-809e-3300e63c0ef2.png)

서비스 다운되어 있어서 delivery 서비스 조회 시 에러 발생
![image](https://user-images.githubusercontent.com/69283682/97561168-11381e00-1a23-11eb-956e-5962ed45d9ac.png)

delivery 서비스 시작

delivery 서비스 조회 시 정상 확인
![image](https://user-images.githubusercontent.com/69283682/97561273-40e72600-1a23-11eb-8770-1e6e58cdc94a.png)

3. CQRS
dashboard 통해 복수개의 서비스 현황을 조회

dashboard에서 paid, delivery 정보 view 구현
![image](https://user-images.githubusercontent.com/69283682/97561906-31b4a800-1a24-11eb-9bc3-178666142348.png)

dashboard 조회 결과
![image](https://user-images.githubusercontent.com/69283682/97562008-57da4800-1a24-11eb-91d7-ab0a8a80abd0.png)

4. Gateway

8088로 dash 조회
![image](https://user-images.githubusercontent.com/69283682/97562218-9e2fa700-1a24-11eb-8306-36f435499814.png)

8088로 payment 조회
![image](https://user-images.githubusercontent.com/69283682/97562314-c4554700-1a24-11eb-82d7-675d2da0bda7.png)

5. CI
각 서비스를 Pipeline 등록
![image](https://user-images.githubusercontent.com/69283682/97562511-14340e00-1a25-11eb-9f8a-f053d8b5020d.png)

6. CD
각 서비스 CD (Release) 등록
![image](https://user-images.githubusercontent.com/69283682/97562673-5c533080-1a25-11eb-89d8-3ffede6c309c.png)

kubectl 설정
![image](https://user-images.githubusercontent.com/69283682/97562752-7db41c80-1a25-11eb-849b-f154bb53043e.png)

7. configMap
configmap 설치 (yaml)
![image](https://user-images.githubusercontent.com/69283682/97563002-d1266a80-1a25-11eb-8117-80c9c1390211.png)

- application.yml
![image](https://user-images.githubusercontent.com/69283682/97563435-6295dc80-1a26-11eb-836f-8cf5a2e86b67.png)

- deployment.yml
![image](https://user-images.githubusercontent.com/69283682/97563694-c15b5600-1a26-11eb-9810-539fe289d2fa.png)
