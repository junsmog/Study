# [SWIFT] UITextView Center Vertical (텍스트뷰 세로 가운데 정렬)#

`Xcode`로 코딩하다보면 `UITextView`에 대한 가로 정렬은 있으나 세로 정렬이 없다는 것을 발견하게 됩니다. 
`UITextView`에서 세로 정렬하는 방법을 소개하려고 합니다.

**원리**

```
1.UITextView 모든 글이 들어갔을 때 크기 * zoomScale
2.UITextView Bounds 크기 - 1번 결과값 (UITextView 모든 글이 들어갔을 때 크기 * zoomScale)
3.2번 결과 값 / 2 의 값과 1 중 최고 값을 가져옵니다. 
4.3번의 결과 값을 UITextView의 ContentOffSet y 값으로 설정 합니다.
```

1번 ~ 4번을 수식으로 표현하면 다음과 같습니다.

```
contentOffset.y = -(max(1, (UITextView 모든 글이 들어갔을 때 크기 * zoomScale) / 2)))
```

요약하자면, 
UITextView의 Bounds 높이 크기보다 UITextView에 입력된 글자의 높이 크기가 작았을 경우 가운데 정렬을 해주는 로직 입니다.

# **소스코드**

```swift
// UITextView Extention
func centerVertically() {
        let fittingSize = CGSize(width: bounds.width, height: CGFloat.greatestFiniteMagnitude)
        let size = sizeThatFits(fittingSize)
        let topOffset = (bounds.size.height - size.height * zoomScale) / 2
        let positiveTopOffset = max(1, topOffset)
        contentOffset.y = -positiveTopOffset
 }

// 사용 방법
UITextView.centerVertically
```

# **정리**

위 소스의 단점이 하나있습니다.  글자크기를 모든 디바이스가 동일하게 설정해야하는 문제가 있습니다. 
**StoryBoard 에서 Variation을 했을 경우 가운데 정렬 소스가 적용되지 않습니다.** 
또한 **디바이스에 따른 글자크기 변경에서도 적용되지 않는 이슈가 있습니다.** 만약 디바이스마다 글자크기를 다르게 할 경우 별도로 UITextView를 구현해야할 것으로 생각됩니다.

위의 글자크기 고정 이슈 대응만 확실히 해결한다면 빈번하게 사용될 것으로 예상됩니다.