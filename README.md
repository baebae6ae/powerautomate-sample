# powerautomate-sample
특정 열에 나열된 데이터를 가로 행에 추가하여 다수의 데이터를 정리 및 관리


![image](https://github.com/baebae6ae/powerautomate-sample/assets/49053443/f079116f-a231-4159-bea4-5dd97c853dac)

1. 파일 업로드(SharePoint)
2. 업로드한 파일에 대해 데이터 구간을 테이블로 지정
3. 테이블에 있는 행 나열
   테이블: 사용자 지정 값-테이블 만들기 동적 값 name 또는 outputs('테이블_만들기;)?['body/name']

![image](https://github.com/baebae6ae/powerautomate-sample/assets/49053443/d40902b2-ea66-4f70-97af-38fb8f424b40)

4. 변수 초기화
   유형: 배열, 값: 테이블에 있는 행 나열의 동적 값 value
5. 작성
   입력: 변수 초기화의 output
6. 테이블에 행 추가
   데이터를 행으로 추가할 엑셀 파일, 테이블 지정
   각 행에 outputs('작성')?[0][‘열 이름'], outputs('작성')?[1][‘열 이름'], outputs('작성')?[2][‘열 이름']... 입

결과
