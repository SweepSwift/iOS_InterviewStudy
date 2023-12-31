
###  함수형 프로그래밍 


함수형 프로그래밍이란 객체 지향 프로그래밍과 다르게 어떻게 할 것인 지 보다 무엇을 할 것인 지에 초점을 맞춘 프로그래밍 패러다임입니다.
함수형 프로그래밍은 기능을 순수 함수 단위로 문제를 나누어 해결하는 방법으로 가독성을 높여줍니다.
상태값을 가지지 않고 순수하게 함수만으로 동작하기에 사이드 이펙트를 줄일수 있고 어느 상황에서도 일정한 결과를 만들수 있습니다.

- 순수 함수: 같은 입력에 대해 항상 같은 출력을 반환하며 side-effect가 없는 함수입니다. 이는 함수가 외부 상태를 변경하지 않아야 함을 의미합니다.
- 참조 투명성: 함수의 반환값이 외부 상태에 의존하지 않는 것을 의미합니다. 이는 함수의 결과가 항상 같다는 것을 의미합니다.

      func add(_ a: Int, _ b: Int) -> Int {
        return a + b }

      func add(_ a: Int, _ b: Int) -> Int {
        return a + b }


- 일급 함수: 함수를 변수에 할당하거나 함수의 인자로 전달할 수 있는 함수입니다.
    
      let addFunction = add // 함수를 변수에 할당
      addFunction(1, 2) // 3 // 변수에 할당된 함수를 호출

- 사이드 이펙트 (side Effect) : 프로그램이이예상치 않은 외부 상태 변경을 일으키는 것

- 일급 객체 : 변수에 할당 가능, 함수의 인자로 전달 가능, 함수의 반환값으로 사용 가능, 자료 구조의 구성 요소로 사용 가능
