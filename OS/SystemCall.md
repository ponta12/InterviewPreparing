# System Call

fork(), exec(), wait()와 같은 것들은 Process 생성과 제어를 위한 System call임

- fork, exec는 새로운 Process 생성과 관련이 되어 있다.
- wait는 Process(Parent)가 만든 다른 Process(child)가 끝날 때까지 기다리는 명령어이다



**exec와 fork**

단순 fork는 동일한 프로세스의 내용을 여러 번 동작할 때 사용함

child에서는 parent와 다른 동작을 하고 싶을 때는 exec를 사용할 수 있음

