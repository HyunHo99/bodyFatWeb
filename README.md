# CHECK YOUR BODY FAT
https://bodyfat.ml
헬린이의, 헬린이에 의한, 헬린이를 위한 웹.
자신의 눈바디를 누군가에게 물어보고 싶지만, 차마 부끄러워 누군가에게 물어보지도 못하고 마음 졸이는 이들을 위해 개발되었습니다.

> 개발자: 양현호, 이호준, 최정재

## 데이터 수집 과정

+ google, instagram 크롤링을 통해 얻어진 3000개 가량의 데이터 중, 복근 사진이 나와있는 사진만 걸러내었습니다. 
+ 거르는 과정은 1차적으로는 OpenCv를 통해 양 어께부터 골반까지를 인식해 잘 인식되는 사진만을 남기고, 복근 사진만 크롭했습니다.
+ 크롭된 사진 중 유효한 이미지만 추출하기 위해, 유효 이미지 50개와 비유효 이미지 50개를 google teachable machine을 이용해 딥러닝 모델을 얻고, 이 딥러닝 모델로 다른 이미지들을 걸러내었습니다.

## 딥러닝 훈련 과정

+ convolutional layer와 dense layer만으로 구성하려 했으나, 오차가 4.x mae 이상이 되어 다른 방법을 찾았습니다. 
+ google사의 mobileNetV2를 이용한 전이학습을 통해 이미지의 feature을 보다 정확하게 추출하려 했습니다.
+ feature 추출과정을 제외한 Dense layer는 다음과 같이 구성했습니다.
+ ![캡처](https://user-images.githubusercontent.com/86706463/126333791-a5107c72-a312-4604-b9a5-3a15b7141d0d.JPG)
+ 학습 결과는 다음과 같습니다.
+ ![캡처3](https://user-images.githubusercontent.com/86706463/126333797-f487d527-9c9c-42bc-8416-a43a53e0aa0d.JPG)
## 웹페이지 구성 과정

+ 첫 페이지에서는 멋있는 이미지와 애니메이션을 불러옵니다.
+ 두 번째 페이지에서는 페이지 사용법을 알려줍니다.
+ 세 번째 페이지에서 이미지를 업로드하고 어께에서 골반까지를 자르면 당신의 눈바디를 알려줍니다!
