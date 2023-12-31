# @escaping closure에 대해 설명하세요.

## A
- 함수의 파라미터로 전달받은 클로저를 **함수의 생명주기가 끝난 후에 실행**하거나 **함수 밖에서 변수나 상수에 저장**하기 위해 사용하는 타입 속성입니다. 즉, 값이 호출 수명보다 오래 지속될 수 있어 <U>**메모리 누수에 주의**</U>해야 합니다.

- `@escaping closure`는 `옵셔널`과 함께 사용할 수 없는데요, `옵셔널`로 선언 시 함수의 매개변수 타입을 인식할 때 **클로저가 아닌 옵셔널 타입으로 인식**하기 때문입니다. 그러나 `옵셔널` 타입과 `@escaping` 키워드가 공존할 수 없을 뿐이지, `옵셔널` 타입으로 선언 시 자동으로 `@escaping closure`로 동작합니다.

---

### non-escaping closure 와 차이점
- Swift에서 `non-escaping closure`는 일반적으로 함수 내부에서 실행되어 자신을 인자로 받는 함수의 생명주기보다 일찍 종료되거나 생명주기를 따라갑니다. 해당 함수가 종료된 후에 클로저가 실행될 수 없으며 변수나 상수에 대입할 수 없고, 중첩 함수 내에서 매개변수로 받은 함수를 리턴할 수도 없습니다.
그러나 `@escaping closure`는 함수의 실행 흐름에 관계없이 호출 시점에 실행되며, 변수나 상수에 대입할 수 있는 건 물론이고 해당 함수를 리턴하는 것도 가능합니다.

- `@escaping` 타입 속성을 가지는 함수 타입 파라미터는, 프로퍼티나 메서드에 대해 `self` 키워드를 명시해야 합니다. `self`가 클래스의 인스턴스를 참조하는 경우, **강한 순환 참조 사이클**이 생기기 쉬워 `Reference Count`에 대한 고려가 필요하며 `[weak self]` 키워드를 사용하여 순환 참조를 방지할 수 있습니다.
그러나 `non-escaping closure`에서는 함수의 생명주기(스코프) 내에서 모든 작업이 이뤄지므로 `[weak self]`키워드를 사용하지 않아도 됩니다.

---
### 사용 예시
  - 비동기 작업
  - Callback Function 콜백 함수(다른 함수에 인자로 들어간 클로저)
  - Delegate Pattern 딜리게이트 패턴
