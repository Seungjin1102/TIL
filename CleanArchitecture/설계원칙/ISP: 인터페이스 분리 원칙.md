# ISP: 인터페이스 분리 원칙



### 객체는 자신이 호출하지 않는 메서드에 의존하지 않아야한다.

##### 구현할 객체에게 무의미한 메서드의 구현을 방지한다.

##### 상속할 객체의 규모가 너무 커지면 작은 인터페이스로 나눈다.



### Ex

![그림 10.1 인터페이스 분리 원칙](https://uchanlee.dev/static/d04224ae81a5b9b85f371bba0709b1c1/3ddad/image-10.1.png)

이 예제는 ISP에 위반되는 예이다.

* User1은 OPS의 모든 메서드를 사용한다(문제없음)
* User2는 op2만 사용한다(op2만 사용하지만 다른 op의 소스코드가 변경되면 User2도 컴파일 후 다시 배포해야 한다.)

#### 해결

![그림 10.2 분리된 오퍼레이션](https://uchanlee.dev/static/d943bf2bf4a9daa8e6a22a613bfccd2c/0a47e/image-10.2.png)

각각의 op를 인터페이스로 만들어 분리한다. 이렇게 되면 변경된 부부만 소스코드에서 수정하고 배포할 수 있다.



### 결론

* 언어 타입에 따라 소스코드 의존성 여부가 다르다.
* 필요 이상으로 많은 걸 포함하는 모듈에 의존하는 것은 좋지않다.

