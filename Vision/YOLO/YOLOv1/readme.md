![image](https://github.com/bovo1/model_implemention/assets/110110403/90e68558-c825-4c69-bd1c-d9655a57c23e)


YOLOv1은 Input으로 448X448 크기의 이미지를 받습니다.  
여러 레이러를 거쳐서 detection을 하는데 한 가지의 모델만 사용하기에 1-stage detector 라고 합니다. 

이러한 Object Detection은 크게 두 가지 구조로 나눌 수 있습니다.  
1. Backbone
2. Head
Backbone은 입력받은 이미지의 특성을 추출하는 역할,
Head는 특성이 추출된 feature map을 받아 detect를 합니다.

Backbone은 위에서 말했듯 feature을 추출하는 것이 목적이기에 feature 추출에 최적화된 모델인 Classification을 목적으로 만들어진 모델을 사용합니다.  
Classification 모델을 사용하는 이유는 특성된 추출을 가지고 어떤 객체인지 알아내는 것에 특화되었기 때문입니다.  
YOLOv1이 만들어질 달시에 가장 성능이 좋은 classfication 모델은 VGG16 이었습니다.  
그래서 보통 VGG16을 backbone으로 사용한 모델들이 많은데 YOLOv1은 자신만의 backbone인 Darknet을 만들었습니다.  

DarkNet의 특징은 448X448 Input을 받아 VGG의 Input 이미지 크기인 224X224 보다 크다는 것과 처리 속도가 빠르다는 점입니다.  
