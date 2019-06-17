# currency_converter
환율 계산 프로젝트(송금 국가는 미국으로 고정, 수취 국가는 한국, 일본, 필리핀으로 고정)

## 사용 기술
- java 8, spring boot 2.1.5, thymeleaf

## 요구 사항
- Spring framework를 이용하여 환율 계산 웹 기능을 구현
- 송금 국가는 미국(USD)로 고정
- 수취 국가들(한국, 일본, 필리핀) 중 하나를 선택하면 환율이 바뀌어 나타나는 기능
- 송금액(USD)를 입력하고 submit하면 선택한 수취 국가에 따른 환율이 계산되어 보여주는 기능
- 환율과 수취금액은 소수점 2째자리까지, 3자리 이상 되면 콤마를 찍어서 보여준다. EX) 1234 -> 1,234.00
- 환율 정보는 https://currencylayer.com/의 무료 서비스를 이용해 실시간으로 가져오면 된다. 
- 가져오는 시점은 서버 실행 시점 혹은 API 호출 시점 둘 중 하나이다.
- 환율을 미리 계산해서 html/js에 넣어두고 수취국가를 변경할 때마다 가져와서 보여주거나, 매번 수취국가를 선택, 변경 시 마다 api를 불러서 보여줘도 된다.
- submit을 하면 선택된 수취국가와 그 환율, 그리고 송금액을 가지고 수취금액을 계산해서 하단에 보여주면 된다. 
- 테스트 코드 작성

## 구현 기능 목록
1. 수취국가에 따른 환율 정보를 보여주는 기능
	- 외부 API 사용(https://currencylayer.com/)
	- 환율은 소수점 2째자리 까지, 3자리 이상 되면 콤마를 찍어 보여준다
	- 수취금액을 입력하지 않거나, 0보다 작은 금액이거나 10,000 USD보다 큰 금액이거나 올바른 숫자가 아니라면 
	"송금액이 바르지 않습니다"라는 에러 메세지를 보여준다. 메세지는 팝업 혹은 빨간 글씨로 나타낸다.

2. 가져온 환율에 따라 송금액을 계산해서 보여주는 기능

## 시연 화면
![Screenshot](./docs/sample1.png)
![Screenshot](./docs/sample2.png)
	

   
