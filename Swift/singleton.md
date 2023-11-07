# SingleTon 패턴이 무엇인지와 언제 활용할 수 있는지 설명하세요
----------------------------------------------------
* SingleTon 패턴이란
  * 특정 클래스에 대해 하나의 인스턴스만이 생성되어 사용되는 디자인 패턴을 의미합니다.
  * 싱글톤 패턴은 동일한 역할을 수행하는 객체가 다중 생성되지 않도록 하여 메모리를 효율적으로 사용할 수 있도록 해줍니다.
  * 멀티 스레드 환경에서 싱글톤 패턴을 활용하게 될 경우에는 문제가 발생할 수 있어 사용에 유의해야 합니다.
    * 하나의 객체만 생성되어야 하는데 객체가 다중으로 생성되어 thread-safe를 보장하기 어려워지는 문제가 발생할 수 있습니다.
      이러한 문제는 동시 접근 가능한 스레드의 수를 제한하거나 lock을 구현하여 보완할 수 있습니다.
    * thread-safe하지 않다는 것은 여러 스레드가 동시에 인스턴스를 호출하여 인스턴스가 동시에 생성되는 것을 뜻합니다.
      Swift의 경우에는 static 키워드를 통해 타입 프로퍼티로 생성되는데, 이때 GCD의 dispatch_once가 적용되어 thread-safe 합니다.

* SingleTon 패턴의 활용 예시
  * UIKit
    ```
    let screen = UIScreen.main    // 화면
    let userDefaults = UserDefaults.standard    // UserDefault
    let application = UIApplication.shared   // 앱
    let fileManager = FileManager.default    // 파일
    let notification = NotificationCenter.default   // 노티피케이션(특정 상황, 시점을 알려줌)
    let logger = Logger.shared   // 로그 메세지
    ```
  * 사운드 효과를 재생하는 오디오 채널, HTTP 요청을 수행하는 네트워크 관리자 등 앱 전체에서 공유되는 리소스 및 서비스에 대해 관리할 때 사용할 수 있습니다.
