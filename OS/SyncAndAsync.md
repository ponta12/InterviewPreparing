# 동기와 비동기 차이

#### 비유를 통한 쉬운 설명

해야할 일(task)가 빨래, 설거지, 청소 세 가지가 있다고 가정한다. 이 일들을 동기적으로 처리한다면 빨래를 하고 설거지를 하고 청소를 한다. 비동기적으로 일을 처리한다면 빨래하는 업체에게 빨래를 시킨다. 설거지 대행 업체에 설거지를 시킨다. 청소 대행 업체에 청소를 시킨다. 셋 중 어떤 것이 먼저 완료될지는 알 수 없다. 일을 모두 마친 업체는 나에게 알려주기로 했으니 나는 다른 작업을 할 수 있다. 이 때는 백그라운드 스레드에서 해당 작업을 처리하는 경우의 비동기를 의미한다.



#### Sync vs Async

일반적으로 동기와 비동기의 차이는 **메소드를 실행시킴과 `동시에` 반환 값이 기대되는 경우를 동기라고 표현**하고 그렇지 않은 경우에 대해서 비동기라고 표현된다. **동시에라는 말은 실행되었을 때 값이 반환되기 전까지는 `blocking`되어 있다는 것을 의미**한다. 비동기의 경우, **`blocking`되지 않고 이벤트 큐에 넣거나 백그라운드 스레드에게 해당 task를 위임하고 바로 다음 코드를 실행하기 때문에 기대되는 값이 바로 반환되지 않는다.**

