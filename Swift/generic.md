# Generic이 무엇이고 어떻게 동작하는지 설명해주세요.

- Generic 은 Type 에 유연하게 대응하기 위한 요소로,
함수, 클래스, 또는 구조체가 특정 타입에 종속되지 않고 여러 종류의 타입을 수용할 수 있도록 해줍니다.
- 이를 위해 Type Parameter <T> 를 이용하여 다양한 타입을 수용할 수 있습니다.

```swift
// 제네릭을 사용하지 않은 함수
func swapTwoInts(_ a: Int, _ b: Int) {
    let temporaryA = a
    a = b
    b = temporaryA
}

// 제네릭을 사용한 함수
func swapTwoValues<T>(_ a: T, _ b: T) {
    let temporaryA = a
    a = b
    b = temporaryA
}

var someInt = 3
var anotherInt = 107
swapTwoValues(someInt, anotherInt)
//result: someInt = 107, anotherInt = 3

var someString = "hello"
var anotherString = "world"
swapTwoValues(someString, anotherString)
//result: someString = "world", anotherString = "hello"
```

- 제네릭은 동일한 로직을 다양한 데이터 타입에 대해 재사용할 수 있어 코드 중복을 최소화하고 유지 보수를 용이하게 합니다.
- 또한, 컴파일 시점에서 타입 안정성을 보장하기 위해 특정 클래스 상속이나 프로토콜 준수와 같은 제한 조건을 설정하여 잘못된 데이터 타입으로 인한 오류를 방지합니다.