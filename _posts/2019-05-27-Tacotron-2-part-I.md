# 제목 Tacotron-2 - 제1부 구성 소개

## I. Google의 음성합성 기술
2017년 12월에 Google가 "NATURAL TTS SYNTHESIS BY CONDITIONINGWAVENET ON MEL SPECTROGRAM PREDICTIONS"라는 논문을 발표했습니다. 이논문에은 인간 목소리를 자연스럽게 합성해 주는 딥러닝 모델을 제안했습니다. 전 음성합성 기술과 달리, tacotron-2은 복잡한 언어 및 어쿠스틱 특징을 사용하지않고 바로 음성과 대응 텍스트으로 학습된 모델통해 합성 텍스트로 음성을 자연스럽게 만들어냅니다. 
바이두라는 중국 화사도 비씃한 Deep voice 3 모델을 제안했는데 지금까지는 Tacotron-2 아직도 성능 가장 좋은 모델인 것 같습니다. 
	
## II.Tacotron-2 아키텍처
본 모델의 아키텍처가 아래 같은 주로 2부분 있습니다.
	
### 1. Tacotron 모둘
이 모둘은 sequence-to-sequence 딥러닝 망입니다. 


학습 과정에는 처리 된 음성과 텍스트를 분석하여 melspectrogram을 예측 모델을 구성되니다. 질행 과정에는 텍스트를 입력하면 melspectrogram을 예측 되고 이 melspectrogram을 wavenet vocoder 모둘의 입력 데이터가 됩니다. 

![Tacotron architecture](https://camo.githubusercontent.com/7bdc61ffb468c3daf1af3b5cef2ccc16c3473cd9/68747470733a2f2f707265766965772e6962622e636f2f625538734c532f5461636f74726f6e5f325f4172636869746563747572652e706e67)



	
### 2. Wavenet vocoder 모둘
이 모둘은 2016년에 발표했던 wavenet 모델을 수정해서 구성된 모둘입니다. dilated convolutional network 사용하여 melspectrogram을 시간별 음성 데이터로 전환해 주는 모델인데 성능이 검증되었습니다. 

![wavenet dilational network](https://storage.googleapis.com/deepmind-live-cms-alt/documents/BlogPost-Fig2-Anim-160908-r01.gif)

## 다음 내용:
데이터 전 처리 및 한글 텍스트에 적용
 
