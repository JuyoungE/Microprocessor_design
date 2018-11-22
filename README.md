# Microprocessor_design

I annotated each code of file.

***

## FSM design for 8 bit SAC

### 1.OBJECTIVE




Atmega128을 이용하여 8 bit SAC를 설계하고 시뮬레이션을 통해 동작을 확인한다. 

SAC란 successive approximation circuit의 약자로 아날로그 신호를 디지털 신호로 변환시키는 회로를 뜻한다. 위 그림에서 빨간 표시한 부분을 의미한다.















### 2. DETAIL PROJECT DESCRIPTION


 우선 회로의 전원(start)은 PE5에 연결된 push 버튼을 이용하였다. 즉 push 버튼을 누르면 아날로그 신호를 받아들여 회로 동작이 시작된다. 동작시킬 회로는 위에서 언급한 SAC회로로 입력받은 아날로그 신호 값을 디지털 신호 값으로 변환한다. 아날로그 신호 값을 디지털 신호 값으로 변환하는 원리는 아래와 같다.

 디지털 값이 8bit이므로 7bit부터 0bit까지 차례로 아날로그 값과 크기를 비교한다. 좀 더 자세하게 말하자면 우선 디지털 중앙값인 ‘1000 0000’(7bit)을 '예상 디지털 변환 값(이하 A)'으로 두고 아날로그 값과 크기를 비교한다. 만약 아날로그 값이 더 크면 A를 전 비트 크기만큼 증가시키고(예를 들어 위의 경우 7bit 비교하였으므로 6bit인 ‘0100 0000’만큼 증가), 아날로그 값이 더 작으면 A를 전 비트 크기만큼 감소시킨다(예를 들어 위의 경우 7bit 비교하였으므로 6bit인 ‘0100 0000’만큼 감소). 
 이렇게 얻게 된 A값을 다시 아날로그 값과 비교하여 전 비트만큼 더하거나 빼는 위의 과정을 반복한다. 모든 비트와 비교가 끝이 나면 A엔 우리가 얻고 싶은 아날로그의 디지털 변환 값이 저장된다.

 마지막으로 이렇게 A에 저장된 디지털 변환 값을 PA0번부터 PA7번에 연결된 LED를 이용해 육안으로 쉽게 확인할 수 있도록 하였다.


















### 3.HARDWARE DESIGN, INCLUDE BLOCK DIAGRAM OF DESIGN, I/O, ETC.

- 회로의 전원(start)은 PE5에 연결된 push 버튼을 이용한다.
- 최종 디지털로 변환된 신호 값은 PA에 연결된 LED에 표시한다.




### 4. SOFTWARE DESIGN, INCLUDE FLOW CHART, FUNCTIONS USED IN CODE


s3 & s4
































4
0
1













### 5. SIMULATION & EXPERIMENT RESULTS








