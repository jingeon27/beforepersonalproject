# 개인프로젝트 전 레포지토리

- 개인프로젝트를 위한 빌드업
- express를 심도 있게 차근차근 공부하기 위한 repository

## node.js 기초 정리

--------------------------

## 이벤트 기반

- 이벤트 기반은 이벤트가 발생할 때 미리 지정해둔 작업을 수행하는 방식을 의미함. ex(클릭, 네트워크 요청 등)
- 이벤트 기반 시스템에서는 특정 이벤트가 발생할 때 무엇을 할지 미리 등록해두어야함.
- 노드도 js와 마찬가지로 이벤트 기반 방식으로 동작해 이벤트가 발생하면 이벤트 리스너에 등록해둔 콜백함수를 호출하고 다 처리하면 다음 이벤트까지 대기함

### 이벤트 루프

- 이벤트 발생 시 호출할 콜백 함수들을 관리하고, 호출된 콜백함수의 실행 수서를 결정하는 역할을 담당, 노드가 종료될 때까지 이벤트 처리를 위한 작업을 반복해 루프라고 부름

### 백그라운드

- 타이머나 이벤트 리스너들이 대기하는 곳 js가 아닌 다른언어로 작성된 프로그램이라고 봐도 됨. 여러 작업 동시 실행 ㄱㄴ

### 태스크 큐

- 이벤트 발생 후, 백그라운드에서는 태스크 큐로 타이머나 이벤트 리스터의 콜백하수를 보냄, 정해진 순서대로 콜백들이 줄을 서 잇어서 콜백 큐라고도 부름 콜백들은 보통 완료된 순서대로 줄을 서 잇지만 특정 경우에 따라 순서가 바뀌기도 함.

## 논 블로킹 I/O

- 논 블로킹이란 이전 작업이 완료될 때까지 대기하지 않고 다음 작업을 수행함을 뜻함
- 블로킹이란 이전 작업이 끝나야만 다음 작업을 수행하는 것을 의미함
- 논 블로킹으로 작성해도 전체 소요 시간이 짧아지지 않음

### 논블로킹 장점

- 간단한 작업이 대기하는 상황을 막을 수 있음.

### setTimeout(콜백, 0)

- 0으로 설정하면 바로 실행되는 게 아니라 브라우저에선 4ms 노드에서는 1ms의 지연 시간이 있음.

## 노드의 장단점

### 장점

- 싱글 스레드이기 때문에 멀티 스레드 방식에 비해 적은 컴퓨터 자원 사용(cpu 1개 씀 ㅇㅇ)
- 논 블로킹 방식으로 멀티 프로세싱을 하기 때문에 I/O가 많은 서버로 적합함
- 웹 서버가 내장되어 있음
- JSON 형식과 쉽게 호환됨

### 단점

- 기본적으로 CPU 코어를 하나만 사용
- CPU 작업이 많은 서버로는 부적합함
- 하나뿐인 스레드가 멈추지 않도록 관리가 필요함
- 서버 규모가 커졌을 시 관리 어려움
- 어중간한 성능
