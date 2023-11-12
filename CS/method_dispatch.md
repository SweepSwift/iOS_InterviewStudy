## Method Dispatch

method가 실행될 때, 프로그램이 어떤 method를 실행할지 선택하는 메커니즘을 말한다.

Method Dispatch는 어느 시점에 어떤 method를 사용할지를 결정하느냐에 따라서 Static Dispatch와 Dynamic Dispatch로 나뉜다.

### Dynamic Dispatch

- **런타임에 어떤 method가 사용될지 결정되는 것**을 말하며, **참조타입에서 사용**된다.

- 클래스의 경우에는 상속이 가능하기 때문에, 컴파일 타임에서 참조될 요소의 위치가 명확하게 결정되지 않기 때문에 런타임에서 실제 참조될 요소가 결정된다. 따라서 프로그램 실행 중 해당 요소를 찾는 과정이 필요하기 때문에 성능적으로 떨어지며, **오버헤드**가 발생할 수 있다.

- 다만, 어떤 서브클래스가 들어와도 실제에 맞는 요소를 참조하기 때문에 **다형성 활용에 유리**하다는 장점이 있다.

### Static Dispatch

- Static Dispatch는 **컴파일 타임에 어떤 method를 사용할지 결정**하며, **값타입과 참조타입(class, struct 모두)에서 모두 사용**될 수 있다. `protocol`과 `extension` 모두 Static Dispatch에서 동작하며, 참조타입인 class에 `final` keyword를 사용한다면 Static Dispatch로 동작한다.

- Static Dispatch로 동작한다는 것은 기본적으로 컴파일 타임에 어떤 method를 호출할지 결정할 수 있다는 뜻으로, 실행하려는 method가 뚜렷하기 때문에 기본적으로 모든 값에 적용된다.
