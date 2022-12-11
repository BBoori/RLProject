# RLProject

# 코드 저장 파일 
- a66032_rl_project.py
- A66032_RL_project.ipynb << colab 에서 수행

# Acrobot-vi
- https://www.gymlibrary.dev/environments/classic_control/acrobot/
- 목표는 막대에 토크(회전력)를 적용하여 아래파트를 스윙하여 목표 높이에 도달하는 것

## State, action, reward 설계 
1. Action Space : discrete, deterministic

![image](https://user-images.githubusercontent.com/117243020/206926943-99ac84d4-054a-452a-b0ad-dc2773559def.png)

2. Observations : 6개 (theta1은 첫번째 관절 , theta2는 두번째 관절)

- 두개의 회전 관절 각도와 각 속도에 대한 정보를 제공 /
- 관측값에서 0번과 1번은 1번 링크 각도의 삼각함수 값, 2번과 3번은 2번 링크 각도의 삼각함수 값.
- 4번과 5번은 각 링크의 각속도를 나타낸다.

![image](https://user-images.githubusercontent.com/117243020/206927007-0d8a3964-9cc8-4b83-b843-b9014b8d5dd5.png)

3. Reward
- 가능한 한 적은 단계로 지정된 목표 높이에 도달하도록 하는 것이며 
- 목표에 도달하지 못한 모든 단계는 -1의 보상을 받는다. 
- 목표 높이를 달성하면 보상이 0으로 종료된다. 보상 임계값은 -100이다

5. Starting State
- 기본 상태( theta1, theta2및 두 각속도)의 각 매개변수는 -0.1과 0.1 사이에서 균일하게 초기화된다.
- 이것은 두 링크가 약간의 초기 확률로 아래쪽을 가리키고 있음을 의미한다.

6. Episode End
- 다음 중 하나가 발생하면 에피소드가 종료된다.
  1. 종료: 자유단은 다음과 같이 구성되는 대상 높이에 도달할때
   -cos(theta1) - cos(theta2 + theta1) > 1.0
  2. 잘림: 에피소드 길이가 500보다 클때



## 강화학습 알고리즘 및 hyperparameter 등 설명 : PPT 파일 참조


## 실험 셋업
>  테스트 환경
1. DQN 모델 , 에피소드 3000번 반복 
2. Double DQN 모델 , 에피소드 3000번 반복 
3. DQN 모델 , 에피소드 6000번 반복 
4. Double DQN 모델 , 에피소드 6000번 반복 

## 실험 결과 : PPT 파일 참조




