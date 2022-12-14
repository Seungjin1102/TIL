# LSP: 리스코프 치환 원칙



### 상위 타입의 객체를 하위 타입의 객체로 치환해도 상위 타입을 사용하는 프로그램은 정상적으로 동작해야한다.

### 특정 메소드가 상위 타입을 인자로 사용한다고 할 때, 그 타입의 하위 타입도 문제 없이 정상적으로 동작해야한다는 말.



### Ex

![그림 9.1 License와 파생 클래스는 LSP를 준수한다.](https://uchanlee.dev/static/2602e08dd5e4b86d136e5860b7726449/0a47e/image-9.1.png)

이 예제는 LSP를 준수하는 예이다.

* Billing 의 행위가 License 하위 타입을 의존하지 않는다.
* 하위 타입은 모드 License 타입을 치환할 수 있다.



![그림 9.2 악명 높은 정사각형/직사각형 문제](https://uchanlee.dev/static/0bb1fe33b3e2479c58cba7ae2433dd0e/42a8d/image-9.2.png)

이 예제는 LSP를 위반하는 예이다.

* Rectangle 의 가로와 세로는 독립적으로 변경할 수 있지만, Square 는 가로와 세로가 같이 변경된다.
* User에서는 Rectangle 이 Square 인지 검사하는 조건을 추가하는 루틴이 필요 -> User의 행위가 사용하는 타입에 의존하게 된다(서로의 타입 치환 불가능)

### 결론

* LSP는 아키텍처 수준까지 확장할 수 있고 반드시 확장해야 한다.
* 치환 가능성을 조금이라도 위배하면 시스템 아키텍처가 오염되어 루틴을 추가할 수 도 있다(Square 예제)
* 상속을 잘 정의하여 치환 가능성이 위배되지 않도록 설계한다.
