# Autodesk Interactive 메터리얼 HDRP용으로 업그레이드 하기
# How to Upgrade Autodesk Interactive Shader to HDRP

![image 2021-10-08 102119](https://user-images.githubusercontent.com/67905493/136483599-c36cf4c9-3775-4f62-88a7-951893065aaa.png)

HDRP를 적용하면서 메터리얼이 깨진 모습이다. 

![image](https://user-images.githubusercontent.com/67905493/136483652-9e3b0234-4439-4232-a436-3c40319adc50.png)

HDRP용 쉐이더로 지정되지 않은 모습이다.

![image](https://user-images.githubusercontent.com/67905493/136483747-d88d12ce-c392-4389-81a2-99b270a6e4d4.png)     

자동으로 HDRP용 메터리얼로 업그레이드를 해도, 아무런 일도 일어나지 않는다.


![image](https://user-images.githubusercontent.com/67905493/136483798-590fa60a-7a9c-467c-a560-82082039afe0.png)     

수동으로 메터리얼 쉐이더를 HDRP/Autodesk Interactive/AutodeskInteractive로 선택한다.


![image](https://user-images.githubusercontent.com/67905493/136483844-60b176fb-9b5c-4c43-a9a1-132bfacdc194.png)

그리고 메터리얼의 프로퍼티에서 UseColorMap, UseNormalMap 같은 Map 사용 여부에 전부 체크해준다.


![image](https://user-images.githubusercontent.com/67905493/136484177-7aa81d0b-b752-416a-8fc8-e2d5986d0145.png)

정상적으로 업그레이드 된 것을 볼 수 있다.
