# frame과 bounds의 차이에 대해 설명하세요

### 공통
- 뷰의 위치와 사이즈를 반환하는 CGSize 타입의 변수

### Frame
- 상위뷰를 기준으로 상위 뷰에 속한 서브뷰의 좌표를 결정하는 방법
- 상위뷰의 좌표에 대해 상대적인 특징을 가지기 때문의 상위뷰의 변화에 따라 크기 및 위치가 달라짐
- frame은 뷰의 위치 및 크기를 지정할 때 사용

### Bounds
- 상위뷰와 상관 없이 자신을 기준으로 좌표를 보여주는 방법으로 원점은 0, 0으로 표현됨
- 자기 내부의 Layer를 그릴 때 사용되어 bounds가 변경될 경우 해당 뷰가 보여지는 시점이 달라짐
- 주로 스크롤뷰에서 많이 사용