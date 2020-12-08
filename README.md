
## 1. 시연 영상
https://youtu.be/qjfb4_BUEa8
## 2. 프로젝트에 대한 소개
 2020 캡스톤디자인프로젝트B 스타트3조 프로젝트
 
 본 프로젝트 SpeakUP은 통역 학습자가 통역음성을 전사하는 과정을 돕는 과제수행 환경을 제공한다.
### 문제 정의
1) 전사자료를 만들 때 시간이 많이 소요되고, 기존 STT는 추임새, 침묵구간을 표시해주지 못한다.

2) 통역 개시 지연 시간을 직관적으로 파악하기가 불가능하다.

3) 객관적 평가 지표를 확인하기 어렵다. 
 
### 제안 내용
1) 침묵구간의 위치 및 길이, 필러를 텍스트에 표시해주는 새로운 전사 시스템 개발

2) 통역 개시 지연시간 파악 및 가시화 기능 개발

3) 전사파일 채점과 자가평가를 위한 통계분석 제공
    
    
### 구현 방법

#### 1) 전처리 : 노이즈 제거
#### 2) 태깅
  ![캡처](https://github.com/EwhaSpeakUP/SpeakUP/blob/master/images/캡처.JPG)  
   1) 파형 분석을 통해 침묵 구간과 비침묵 구간 분리
   
   2) filler word detector를 통해 필러와 비필러로 분리
   
   3) filler word classifier를 통해 필러의 종류 구별
#### 3) 후처리 (텍스트화)
  - 공백(1 _ _ _ )이면 공백 길이를 '...n초...'로 출력
  
  - 필러(01 _ _ )면 해당 필러로 텍스트화 및 통계 처리
  
  - 그 외 단어(00 _ _  )이면 google STT API로 텍스트화
### 기대효과 및 의의
1) 학습자가 전사파일을 제공하기 위해 반복해서 번역 음성파일을 들을 필요 없이 바로 전사파일을 만들어준다.

2) 교수자와 학습자가 전사자료를 만드는데 소요되는 시간 및 노력이 현저히 줄어든다.

3) 교수자에게 학습자의 실질적인 통역 평가를 위한 충분한 시간을 제공한다. 

4) 통역평가의 중요한 요소인 통역 개시 지연시간을 시스템에서 측정해주어, 교수자가 원활한 평가를 할 수 있도록 돕는다.

5) 학습자의 통역평가를 위한 통계분석 자료를 제공해 교수자의 객관적 판단 및 학습자의 자가평가를 돕는다.
 
## 3. Reference
### 딥러닝 모델
https://github.com/tensorflow/docs/blob/master/site/en/r1/tutorials/sequences/audio_recognition.md
https://github.com/eunbeejang/SilentBabyMonitor
https://github.com/harmanpreet93/audio_classification/blob/master/audio_classification_conv2d_mfcc.ipynb
### 서버
https://github.com/extrabacon/python-shell
https://github.com/jung2929/melon_mock_server_layeong
https://github.com/lcobucci/jwt
https://www.opentutorials.org/course/2717
### 안드로이드
https://github.com/square/retrofit
https://github.com/square/okhttp
https://github.com/square/retrofit/tree/master/retrofit-converters/gson
https://github.com/PhilJay/MPAndroidChart
 
## 4. 각 기술에 대한 팀원들의 기술 블로그 내용
- 딥러닝모델&전사알고리즘: https://youdaeng-com.tistory.com/5
- 서버 : https://blog.naver.com/72kyj37/222146734461 / https://blog.naver.com/heyji1230/222146936643
- 안드로이드 :  https://jionchu.tistory.com/entry/SpeakUP-%EC%95%88%EB%93%9C%EB%A1%9C%EC%9D%B4%EB%93%9C-%EC%95%B1-%EA%B0%9C%EB%B0%9C%EA%B8%B0
 
## 5. License 표시

MIT License

Copyright (c) 2020 EwhaSpeakUP

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
