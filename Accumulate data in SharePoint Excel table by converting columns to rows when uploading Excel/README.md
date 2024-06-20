# Accumulate data in SharePoint Excel table by converting columns to rows when uploading Excel
SharePoint에 파일 업로드 시 특정 열에 나열된 데이터를 또 다른 파일에 행으로 추가하여 다수의 데이터를 자동으로 축적 및 정리

![image](https://github.com/baebae6ae/powerautomate-sample/assets/49053443/6273264f-72ff-4d2d-8177-897b5d2f10f0)


Excel 열에 나열된 데이터를 SharePoint에 업로드 시 하나의 행으로 변환하여 또 다른 Excel 파일에 저장합니다.
다수의 Excel에 각각 기록되어 있는 데이터를 업로드 한번으로 하나의 테이블로 정리하는데에 사용할 수 있습니다.


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
   데이터를 행으로 추가할 엑셀 파일, 테이블 지정(SharePoint에 미리 업로드되어 있어야 함.)
   각 행에 outputs('작성')?[0][‘열 이름'], outputs('작성')?[1][‘열 이름'], outputs('작성')?[2][‘열 이름']... 입력

결과
![image](https://github.com/baebae6ae/powerautomate-sample/assets/49053443/e7580422-ed21-46ad-97dc-532f52121135)
[업로드 파일]

![image](https://github.com/baebae6ae/powerautomate-sample/assets/49053443/d1c9423e-7f71-4571-9ee3-fa60b8e0732a)
[SharePoint 내 파일에 행 추가하여 정리]
