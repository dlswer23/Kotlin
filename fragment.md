# fragment

 재원이가 프레그먼트 모른다고 뭐라고 해서 하는 공부이다.



#####  +fragment가 무엇일까

프레그먼트는 기본적으로 태블릿과 같은 큰 화면에서 역동적이고 유연한 UI디자인을 지원하는 것이 목적이였는데 태블릿의 화면은 휴대폰 화면보다 훨씬 크기 때문에 UI의 구성요소 조합과 표현할 공간이 더 많다.

![](https://miro.medium.com/max/700/0*2SEFa_mSVpapS_1W.png)

 

##### +왜 액티비티가 아닌 프레그먼트를 사용하는가

`일단 액티비티는 무겁다.` 물론 액티비티를 초기화하는데 막 몇초씩 걸리지는 않지만 프레그 먼트에 상대적으로 무겁다.  프레그먼트는 단독적으로 존재 할 수 없다. 액티비티 내에 호스팅이 되어야 한다. 액티비티내에서 프레그먼트는 상대적으로 가볍게 추가/ 재거가 가능하다. 

그리고 우리가 일반적으로 화면을 전환할때는 인텐트를 사용한다. 액티비티는 다른 프로세스에서 실행하는 것을 염두하고 설계 되었기 때문에 메모리 영역을 공유하지 않는다. 그렇기 때문에 리눅스 커널 레벨에서 프로세스 간 통신(IPC)을 하게 되는데, 이 부분에서 많은 제약사항이 생기며 메모리를 직접 공유하는 것보다 퍼포먼스가 많이 떨어지게 된다. 

프레그먼트를 사용하는 경우 프레그먼트 간 데이터 공유는 액티비티내에서 자유롭게 이루어진다. 물론 코드베이스에서 데이터를 전달하는 과정이 복잡해 보일 수 있지만, ViewModel 또는 DI 프레임워크 사용으로 이 부분을 좀 더 매끄럽게 만들 수도 있다.
