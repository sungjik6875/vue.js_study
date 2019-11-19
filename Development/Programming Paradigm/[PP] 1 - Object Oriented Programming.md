##### 출처

```
https://velog.io/@cyranocoding/%EA%B0%9D%EC%B2%B4-%EC%A7%80%ED%96%A5-%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%B0%8DOOP-Object-Oriented-Programming-%EA%B0%9C%EB%85%90-%EB%B0%8F-%ED%99%9C%EC%9A%A9-%EC%A0%95%EB%A6%AC-igjyooyc6c

https://gmlwjd9405.github.io/2018/07/05/oop-features.html
```





### 객체 지향 프로그래밍 (OOP)

------

> 객체 지향 프로그래밍은 컴퓨터 프로그램을 '객체(Object)'들의 모임으로 파악하고자 하는 프로그래밍의 패러다임 중 하나이다. 각 객체들은 서로 메시지를 주고 받을 수 있으며 데이터를 처리할 수 있다.





#### 객체 지향 프로그래밍의 장점

* 프로그램을 유연하고 변경이 용이하게 만든다.
* 프로그램의 개발과 보수를 간편하게 만든다.
* 직관적인 코드 분석을 가능하게 한다.

> 위의 장점들을 관통하는 객체 지향 프로그래밍의 중요한 특성은 강한 응집력(Strong Cohesion)과 약한 결합력(Weak Coupling)을 지향한다는 점이다.
>
> 응집력과 결합력의 의미는 다음과 같다.



##### 응집력

> 프로그램의 요소가 해당 기능을 수행하기 위해 얼마만큼의 연관된 책임과 아이디어가 뭉쳐있는지를 나타내는 정도. 프로그램의 요소가 특정 목적을 위해 밀접하게 연관된 기능들이 모여서 구현되어 있고, 지나치게 많은 일을 하지 않으면 그것을 응집력이 높다고 한다.



##### 결합력

> 프로그램 코드의 한 요소가 다른 것과 얼마나 강력하게 연결되어 있는지, 얼마나 의존적인지를 나타내는 정도. 결합력이 낮다는 것은 요소가 다른 요소들과 관계를 크게 맺고 있지 않은 상태를 의미한다. 반면 결합력이 높은것은 의존도가 높다고 표현하기도 한다.
>
> OOP의 경우 클래스 하나에 문제 해결을 위해 데이터를 모아 놓은 객체를 활용한 프로그래밍을 지향하므로 응집력을 강화하며, 클래스 간에 독립적으로 디자인함으로써 결합력을 약하게 할 수 있다.





#### 객체 지향 프로그래밍의 기본 구성 요소

> 예시 상황은 다음과 같다.

```
필드에 몬스터들을 배치하고 싶다.
몬스터의 종류는 드래곤, 좀비, 해골이 있다.
각 몬스터들은 시간이 흐르고 레벨업을 할 수 있다.
위의 상황에서 객체들을 어떻게 디자인해야 할까?
```



* ##### 클래스

> 같은 종류의 집단에 속하는 속성과 행위를 정의한 것. 다른 클래스와 독립적으로 디자인해야 한다. 위의 예제에서 몬스터의 특성과 행위들을 정의한 객체가 클래스가 된다. 

* ##### 객체

> 클래스의 인스턴스. 상위 클래스의 속성을 갖고 있으면서 개별적인 특성과 행위(메소드) 또한 가지고 있다. 위의 예제에서는 드래곤, 좀비, 해골 등이 각각의 객체가 된다.

* ##### 메서드

> 클래스로부터 생성된 객체를 사용하는 방법. 객체의 속성을 조작하는 데 사용된다. 위의 예제에서 각각의 몬스터들이 레벨업을 하는 행위가 메소드라고 볼 수 있다.





#### 객체 지향 프로그래밍의 특징

> 객체 지향 프로그래밍의 특징은 다음과 같다.

* 추상화
* 캡슐화
* 일반화 관계
* 다형성



##### 추상화 (Abstraction)

> 어떤 영역에서 필요로 하는 속성이나 행동을 추출하는 작업. 사물들의 공통된 특징, 추상적 특징을 파악해 인식의 대상으로 삼는 행위를 말한다. 이러한 특징을 하나의 개념(집합)으로 다루는 수단을 말한다. 예시는 다음과 같다.

```
몬스터는 체력(healthPoint)과 레벨(level), 서식지(habitat) 속성을 가지고 있으며,
레벨을 1단계 올릴 수 있는 메소드(levelUp)을 가지고 있다.
```

> 추상화를 할 때 유의할 점은 속성 위주가 아닌 동작 위주로 정의하는 작업을 하는 것이다. 객체의 동작에 연관이 되지 않는 속성들은 결국 불필요하므로 동작을 정의하고, 동작에 필요한 속성을 정리하는 것이 좋다.



##### 캡슐화 (Encapsulation)

> OOP의 지향 원칙 중 하나인 높은 응집도와 낮은 결합도를 유지할 수 있도록 설계해야 요구사항을 변경할 때 유연하게 대처할 수 있다. 캡슐화는 낮은 결합도를 유지할 수 있도록 하는 객체 지향 프로그래밍의 설계 원리이다.
>
> 캡슐화는 정보 은닉을 통해 높은 응집도와 낮은 결합도를 갖도록 한다.

> ##### 정보 은닉
>
> 필요가 없는 정보는 외부에서 접근하지 못하도록 제한하는 것으로 private 등의 접근 제어자를 사용함으로써 정보를 은닉한다. 정보 은닉이 필요한 이유는 하나의 클래스의 변경이 발생하면 변경된 클래스의 비밀에 의존하는 다른 클래스들도 변경해야 할 가능성이 커지기 때문이다.



##### 일반화 관계 (Generalization)

> 일반화는 여러 개체들이 가진 공통된 특성을 부각시켜 하나의 개념이나 법칙으로 성립시키는 과정이다. OOP의 관점에서는 상속 관계라고도 한다. 따라서 속성이나 기능의 재사용만 강조해서 사용하는 경우가 많다.

> ##### 자식 클래스의 캡슐화
>
> 일반화 관계는 하나의 클래스 안에 있는 속성 및 연산들의 캡슐화에 한정되지 않는다. 외부 세계에서 자식 클래스 자체를 캡슐화하는 것으로 확장된다. 서브 클래스의 캡슐화는 외부 클라이언트가 개별적인 클래스들과 무관하게 프로그래밍을 할 수 있도록 한다.

> ##### 일반화 관계와 위임
>
> 두 클래스 사이에 'is a kind of' 관계가 성립되지 않을 때 상속을 사용하면 불필요한 속성이나 연산도 물려받는다는 문제가 있다. 예를 들어 스택을 구현할 때 ArrayList를 그대로 상속해서 사용한다고 가정하자. ArrayList의 어떤 기능들은(isEmpty, size, add, remove) 별도의 구현이 없어도 사용할 수 있다는 편리함이 있을 것이다. 그러나 스택과 관련없는 많은 연산이나 속성도 같이 상속받는다. 이는 스택의 무결성 조건인 LIFO(Last In First Out)에 위배되는 것들이다.
>
> 위의 문제점을 보완하기 위한 수단으로 위임(delegation)이 있다. 위임은 어떤 클래스의 일부 기능만 재사용하고 싶은 경우에 사용한다. 자신이 직접 기능을 실행하지 않고 다른 클래스의 객체가 기능을 실행하도록 위임한다. 일반화 관계가 클래스 사이의 관계라면, 위임은 객체 간의 관계라고 할 수 있다.



##### 다형성 (Polymorphism)

> 다형성은 서로 다른 클래스의 객체가 같은 메시지를 받았을 때 각자의 방식으로 동작하는 능력이다. 다형성은 보통 상속과 연계되어 동작하게 된다. 다형성과 일반화 관계는 코드를 간결하게 하면서도, 변화에도 유연하게 대처할 수 있게 한다.
>
> 다형성을 사용함으로써 참조되는 클래스 객체의 종류와 무관하게 프로그래밍이 가능하다. 부모 클래스는 자식 클래스에게 물려준 속성에 한해서 참조하는 것이 가능하다.



##### 피터 코드의 상속 규칙 (Peter Coad)

...