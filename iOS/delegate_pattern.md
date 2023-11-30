# Delegate Pattern을 활용하는 경우를 예를 들어 설명하시오.

- Delegate Pattern이란 특정 행위에 대한 자신의 책임을 다른 객체에 위임하는 디자인 패턴입니다.
- Delegate Pattern은 기존의 프레임워크에 존재하는 객체의 동작을 커스텀하여 사용하고 싶을 때, VIewController간의 데이터를 전달할 때, 이벤트를 처리할 때 사용합니다.
<br/>

1. tableView / collectionView의 delegate
    
    ```swift
    class ViewController: UIViewController {
        @IBOutlet weak var tableView: UITableView!
        
        override func viewDidLoad() {
            super.viewDidLoad()
            
            tableView.delegate = self
            tableView.dataSource = self
        }
    }
    
    extension ViewController: UITableViewDelegate, UITableViewDataSource {
        func tableView(_ tableView: UITableView, numberOfRowsInSection section: Int) -> Int {
            return 1
        }
        
        func tableView(_ tableView: UITableView, cellForRowAt indexPath: IndexPath) -> UITableViewCell {
            let cell = tableView.dequeueReusableCell(withIdentifier: "cell", for: indexPath)
            return cell
        }
    }
    ```
<br/>

2. ViewController와 View의 분리
    
    ```swift
        // Delegate 프로토콜 정의
    protocol CustomViewDelegate: AnyObject {
        func didTapButton()
    }

    class CustomView: UIView {
        
        weak var delegate: CustomViewDelegate? // Delegate 프로토콜을 준수하는 Delegate 객체를 프로퍼티로 가짐.
        
        @IBAction func buttonTapped(_ sender: UIButton) {
            delegate?.didTapButton() // Delegate에게 이벤트 위임
        }
    }

    class ViewController: UIViewController {
        override func viewDidLoad() {
            super.viewDidLoad()
            
            let customView = CustomView()
            customView.delegate = self // ViewController가 Delegate 역할을 수행
        }
    }

    extension ViewController: CustomViewDelegate { // Delegate 프로토콜을 채택
        func didTapButton() { // Delegate 객체가 수행할 메서드 구현
            print("Button Tapped")
        }
    }
    ```

