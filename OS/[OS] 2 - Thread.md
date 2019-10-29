### 스레드 (Thread)

------

> 스레드는 어떠한 프로그램 내에서, 특히 프로세스 내에서 실행되는 흐름의 단위를 말한다. 일반적으로 하나의 프로그램은 하나의 스레드를 갖고 있지만, 프로그램 환경에 따라 둘 이상의 스레드를 동시에 실행할 수 있다. 이러한 방식을 멀티 스레드라한다.





#### 프로세스와 스레드

> 프로세스와 스레드는 모두 실행의 단위를 의미하는 개념이다. 스레드는 하나의 프로세스 내에서 동작되는 여러 실행 흐름을 의미한다. 따라서 스레드는 프로세스 내의 주소 공간이나 자원을 공유하는 것이 가능하다. 
>
> 스레드 역시 프로세스처럼 스레드 ID, 프로그램 카운터, 레지스터 집합, 스택 등으로 구성되어 있다. 스레드는 같은 프로세스에 속한 다른 스레드와 코드, 데이터 섹션, 열린 파일이나 신호와 같은 운영체제 자원들을 공유한다. 이렇게 하나의 프로세스를 다수의 실행 단위로 구분하여 자원을 공유하고, 자원의 생성과 관리의 중복성을 최소화하여 수행 능력을 향상시키는 것을 멀티스레딩이라 한다. 멀티스레딩에서 각각의 스레드는 독립적인 작업을 수행해야 하기 때문에 각자의 스택과 PC 레지스터 값을 갖고 있다.
>
> 스레드는 하나의 독립된 실행 흐름이므로 독립된 스택과 PC 레지스터 값을 가져야만 한다. 스택은 함수의 호출시 전달되는 인자, 되돌아갈 주소값, 함수 내에서 선언하는 변수 등을 저장하기 위해 사용되는 메모리 공간이다. PC 레지스터 값은 스레드의 명령어가 어디까지 수행하였는지를 나타내는 값으로 스케줄러에 의해 프로세스가 선점당할 경우 저장되는 값이다.





#### 멀티 스레드 (Multi Thread)

##### 장점

> 프로세스를 이용하여 동시에 처리하던 일을 스레드로 구현할 경우 메모리 공간과 시스템 자원 소모가 줄어들게 된다. 스레드 간의 통신이 필요한 경우에도 별도의 자원을 이용하는 것이 아니라 전역 변수의 공간 또는 동적으로 할당된 공간인 힙 영역을 이용하여 데이터를 주고받을 수 있다. 이는 멀티 프로세스에서 프로세스가 서로 독립된 메모리를 차지하는 것과 다르다. 이러한 이유로 프로세스 간 통신 방법에 비해 스레드 간의 통신 방법이 훨씬 간단하다.
>
> 또 다른 장점으로 스레드의 문맥 전환(context switch)는 프로세스의 문맥 전환과 달리 캐시 메모리를 비울 필요가 없어 더 빠르게 진행된다. 따라서 시스템이 throughput이 향상되고, 자원소모가 줄어들게 되고, 프로그램의 응답시간이 단축된다. 이러한 장점으로 인해 여러 프로세스로 할 수 있는 작업들을 하나의 프로세스에서 스레드로 나누어 수행한다.

##### 단점

> 멀티 스레드의 단점은 각각의 스레드가 어떤 것이 먼저 실행될지 순서를 알 수 없다. 이로 인해 공유자원과 멀티 스레드에 대한 동시성 제어가 요구되는데, 이로 인해 프로그래밍이 복잡해진다는 단점이 있다.
>
> 이는 멀티 프로세싱과는 다르다. 멀티 프로세싱에서는 프로세스 간 공유하는 자원이 없기 때문에 동일한 자원에 동시에 접근하는 경우가 없다. 그러나 멀티 스레딩에서는 프로세스 내의 자원을 공유하므로, 둘 이상의 스레드가 동시에 자원에 접근할 수 없도록 제어하는 작업이 필요하다. 만약 동시에 접근할 경우, 다른 스레드에서 사용중인 변수나 자료구조에 접근하여 엉뚱한 값을 읽어오거나 수정할 수 있기 때문이다.  따라서 순차적으로 접근할 수 있도록 제어해야 하는데 이를 동기화 작업이라고 한다. 만약 동기화 작업을 수행하지 않는다면, 예상하지 못한 오류로 인해 전체 스레드가 종료되는 상황을 맞이할 수도 있다.
>
> 동기화 작업을 통해 작업 처리 순서와 공유 자원에 대한 접근을 제어한다. 그러나 이로 인해 병목현상이 발생하여 멀티스레드의 성능이 저하될 가능성이 있으므로 이를 유의해햐 한다.





#### 스레드의 종류

##### 사용자 레벨 스레드 (User Level Thread)

> 사용자 스레드는 커널 영역의 상위에서 지원되며 일반적으로 사용자 레벨의 라이브러리를 통해 구현되면, 라이브러리는 스레드의 생성 및 스케줄링 등에 관한 관리 기능을 제공한다. 동일한 메모리 영역에서 스레드가 생성 및 관리되므로 속도가 빠른 장점이 있는 반면, 여러 개의 사용자 스레드 중 하나의 스레드가 시스템 호출 등으로 중단되면 나머지 모든 스레드 역시 중단되는 단점이 있다. 이는 커널이 프로세스 내부의 스레드를 인식하지 못하며 해당 프로세스를 대기 상태로 전환시키기 때문이다.

##### 커널 레벨 스레드 (Kernel Level Thread)

> 커널 스레드는 운영체제가 지원하는 스레드 기능으로 구현되며, 커널이 스레드의 생성 및 스케줄링 등을 관리한다. 스레드가 시스템 호출 등으로 중단되더라도, 커널은 프로세스 내의 다른 스레드를 중단시키지 않고 계속 실행시킨다. 다중 처리(Multi CPU) 환경에서 커널은 여러 개의 스레드를 각각 다른 처리기에 할당할 수 있다. 커널 레벨 스레드는 사용자 스레드에 비해 생성 및 관리하는 것이 느리다는 단점이 있다.



#### 스레드 데이터

##### 스레드 기본 데이터

> 스레드도 프로세스와 마찬가지로 독립된 실행 흐름이다. 따라서 실행과 관련된 데이터가 필요하다. 일반적으로 스레드는 자신만의 고유한 스레드 ID, 프로그램 카운터, 레지스터 집합, 스택을 가진다. 그러나 코드, 데이터, 파일 등의 기타 자원은 프로세스 내의 다른 스레드와 공유한다.

##### 스레드 특정 데이터 (TSD, Thread Specific Data)

> 위의 기본 데이터 이외에도 하나의 스레드에만 연관된 데이터가 필요한 경우가 존재한다. 이런 데이터를 스레드 특정 데이터라한다. 멀티스레드 프로그래밍 환경에서 모든 스레드는 프로세스의 데이터를 공유하고 있지만, 특별한 경우에는 개별 스레드만의 자료 공간이 필요하다. 예를 들어 여러 트랜잭션을 스레드로 처리할 경우, 각각의 트랜잭션 ID를 기억하고 있어야 하는데, 이때 TSD가 필요하다. 