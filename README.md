##  진행한 실험

### 1. 에폭(Epoch) 수 증가
- **변경 사항**: `5` -> `20`
- **비고**: 더 늘려보고 싶었지만, 학습에 너무 오랜 시간이 소요되어 20으로 제한했다.
- **결과**:
<img width="163" height="57" alt="image" src="https://github.com/user-attachments/assets/9d1eb7bc-0501-4f09-bfb2-b0c6db56063f" />
원래 계획은 50으로도 늘려서 해보고 싶었지만 너무 오랜 시간이 걸려서 진행하지 못했다.

### 2. 학습률(Learning Rate) 증가
- **변경 사항**: `0.0001` -> `0.001`
- **사유**: 기존 학습 속도가 너무 느려 학습률을 높였다.
- **결과**:
<img width="161" height="57" alt="image" src="https://github.com/user-attachments/assets/b92c6528-eb71-45cc-96f9-8ca7f09c2252" />
이 결과로 떨어진것을 알 수 있고, 학습속도도 드라마틱하게 빨라지지 않아서 

### 3. `ReduceLROnPlateau` 콜백 추가
- **내용**: 검증 손실(validation loss)이 개선되지 않을 때 학습률을 동적으로 감소시키는 `reduce_lr` 콜백을 추가했습니다.
- **결과**:
<img width="161" height="57" alt="image" src="https://github.com/user-attachments/assets/6e938aa9-4339-4a70-b374-b731490dac07" />
콜백을 썼을 때 에폭 16에서 조기종료 되었고, 학습률도 적절히 찾았는지 미미하지만 첫 실험에 비해 지표가 좋게 나왔음을 알 수 있다.

종합적으로, 내가 해본 실험에선 에폭수 20, 콜백을 추가하여 학습했을 때 가장 성능지표 측면으로 나았다는 것을 알 수 있다.

---

##  회고

학습 시간이 예상보다 훨씬 길어져 계획했던 다양한 실험을 모두 진행하지 못한 점이 아쉽습니다. 특히 다른 모델 아키텍처를 테스트해보지 못한 것이 가장 아쉬움으로 남습니다.

결과적으로 미미하지만 성능 향상을 확인했으며, 더 효율적인 데이터 전처리 방법을 적용하여 모델을 다시 학습시켜보고 싶다는 생각이 들었습니다.

---

##  스트림릿 구현 화면
<img width="677" height="647" alt="image" src="https://github.com/user-attachments/assets/b389b69f-7c3e-4804-8d26-1690827865e1" />
