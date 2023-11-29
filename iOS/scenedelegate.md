# Q: iOS 13 이후 등장한 sceneDelegate에 대해 앱의 생명주기와 관련해서 설명해보세요.

# A:

iOS 13 이전에는 `UIApplicationDelegate`가 모든 앱의 생명주기를 관리했습니다. 하지만 iOS 13 이후부터는 `UISceneDelegate`가 등장하면서 앱의 생명주기를 관리하는 역할을 `UIApplicationDelegate`와 `UISceneDelegate`가 나눠서 관리하게 되었습니다.

`UISceneDeleagate`가 등장하게 된 이유는, iOS 13부터는 iPad에서 멀티 윈도우를 지원하기 위해서입니다. 더이상 하나의 앱에 하나의 화면이라는 개념이 성립되지 않기 때문에, 앱의 생명주기를 관리하는 `UIApplicationDelegate`와 앱의 상태를 관리하는 `UISceneDelegate`가 나눠서 관리하게 되었습니다.

하나의 앱은 하나 이상의 `SceneDelegate`를 가질 수 있게 구성되어 있습니다. 이를 통해 각 Scene은 독립적으로 UI의 상태를 관리하고, 사용자에게 멀티플 윈도우를 제공할 수 있게 되었습니다.

### 정리

* iOS 13 이전
  * AppDelegate: 앱의 생명주기 관리, UI 상태 관리


* iOS 13 이후
  * AppDelegate: 앱의 생명주기 관리, Session Lifecycle 관리
  * SceneDelegate: UI 상태 관리
  
  * SceneDelegate에서 Scene이 생성되고 종료되는 트리거를 AppDelegate에 알려줌으로써, AppDelegate가 앱의 생성과 종료 시점을 통제 가능.
