## RxSwift에서 네트워크 통신 시 Single을 사용하는 이유를 서술하시오.

### A.

Single은 RxSwift의 traits의 하나로,  `next`를 통해 이벤트를 처리하는 중에 데이터를 내보내는 side effect가 발생할 수 있는 Observable과 달리, 여러 번 호출이 발생하지 않고 한 가지 요소만 방출한다.
따라서, 파일 저장이나 다운로드, 디스크에서 데이터 로딩과 같이 여러 번의 호출이 필요하지 않은 비동기적 연산, 즉 네트워크 통신 시 주로 사용된다. <br>
Single의 특징을 살펴보면, `.success()`와 `.failure()` 두 가지 이벤트만 방출한다. 이때, `.success()`는 `onNext`와 `onComplete`를 합친 것과 같이 동작한다. 다만, 둘을 합친 것과 비슷하게 동작한다고 해서 single의 event를 `onNext`나 `onComplete`로 전달하게 된다면 오류가 발생한다.
또한, 에러 핸들링에 명시적이며, 코드가 간결해진다.
