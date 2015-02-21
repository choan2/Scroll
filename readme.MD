예제를 통해 scroll 이벤트를 공부합니다.

- - -
##마우스 휠 이벤트와 스크롤의 차이?
#### 마우스 휠 이벤트 (mousewheel)- [mousewheel/mousewheel00.html](http://)
1. 사용자가 마우스 휠을 돌릴때 이벤트를 발생시킨다.
2. 현재 파이어폭스 브라우저를 제외한 모든 브라우저가 mousewheel 이라는 이름으로 이벤트를 지원한다.
3. 파이어폭스는 DOMMouseScroll 이벤트가 대신한다.
4. DOM level 3에서는 wheel 이라는 이름으로 이벤트를 제안한다.
5. mousewheel 이벤트 핸들러의 이벤트 객체에는 wheelDelta 프로퍼티가 존재한다.
6. wheelDelta 프로퍼티는 마우스휠이 얼마나 회전했는지 나타낸다.
7. 윗쪽으로 한칸 돌리면 wheelDelta의 값은 120 delta, 아랫쪽으로 한칸 돌리면 -120 delta
8. 사파리와 크롬은 wheelDeltaX, wheelDeltaY(회전축이 두개일때 가로로 휠을 돌렸을때, 세로로 돌렸을때)를 지원한다. wheelDelta == wheelDeltaY 
9. 파이어폭스에서는 wheelDelta를 대신하여 detail 프로퍼티를 사용한다. detail에 -30을 곱해야 wheelDelta와 값이 같아진다.
10. Dom level 3의 wheel 이벤트 핸들러의 이벤트 객체는 deltaX, deltaY, deltaZ 프로퍼티를 갖는다. mouseWheel 이벤트의 값과 부호 방향을 맞추려면 프로퍼티 값에 -120을 곱해야 한다.
11. mouseWheel 이벤트를 사용하여 문서를 컨트롤 할 경우, 스크롤 양이나 방향을 컨트롤 할 수 있는 장점이 있으나, 현 시점에서 브라우저 별 분기처리가 필요하고, 향후 DOM level 3에서 이벤트 이름이 바뀔 가능성이 있다. 

#### 스크롤 (scroll)
1. 뷰포트와 문서의 크기의 차이로 인해 스크롤바가 발생한다.
3. scrollLeft, scrollTop 프로퍼티가 있다.
4. 위의 두 프로퍼티는 요소의 스크롤바의 위치를 반환한다.
5. document.documentElement에서 scrollLeft, scrollTop 프로퍼티를 이용하려면 문서의 "body" 요소에서 불러와야 한다.
4. 문서의 위치를 이동해야 할때 window객체의 scrollTo() 혹은 scroll() 메서드를 이용하여 스크롤바를 컨트롤 할 수 있다.
5. window 객체에는 scrollBy(), scrollTo(), scroll(), scrollWidth(), scrollHeight(), scrollIntoVIew()등의 메서드가 있다.
6. scrollBy() : scroll() 혹은 scrollTo()와 비슷하지만, 전달인자를 현재 스크롤바 오프셋에 더하여 이동시킨다.
7. scroll(),scrollTo() : 전달인자의 오프셋으로 스크롤바를 이동시킨다.
8. scrollWidth(), scrollHeight() : 요소에 내용 영역과 패딩, overflow:hidden 되어 가려진 내용을 합친 크기 [scrollWidth()](https://developer.mozilla.org/en-US/docs/Web/API/Element.scrollWidth), [scrollHeight()](https://developer.mozilla.org/en-US/docs/Web/API/Element.scrollHeight)
9. scrollIntoView() : 호출한 요소가 뷰포트 안에 노출되도록 보장한다. 전달인자는 true, false 이며, 기본값은 true 이다. 뷰포트 상단에 요소의 상단 가장자리를 가능한 붙인다. false는 하단 가장자리를 붙인다. 앵커 링크를 이용하는 경우와 동작이 비슷하다. 

```
//scrollBy() 예제
//200밀리초마다 10픽셀씩 아래로 스크롤 된다.
javascript:void setInterval(function () {scrollBy(0,10)},200);

//scrollIntoView() 예제
$('#test')[0].scrollIntoView(true

//IE10
$('#test').each(function () {
	this.scrollIntoView(true)
})

```

- - -

## scroll 관련 jquery 메소드
####  .scroll()
1. scroll 이벤트는 스크롤이 움직일 때 발생합니다. 이것은 window 객체에서 제공됩니다. [scroll_00/scroll01.html](http://choan616.dothome.co.kr/study/scroll/scroll_00/scroll01.html)
2. 스크롤이 가능한 프레임이나 overflow CSS 속성이 있는 요소의 scroll (또는 auto 속성) 에서도 발생합니다.[scroll_00/scroll02.html](http://choan616.dothome.co.kr/study/scroll/scroll_00/scroll02.html)

####  .scrollLeft()
1. scrollLeft(): 수평(가로) 스크롤의 위치는 픽셀 수치입니다. 스크롤바가 아주 왼쪽에 있거나 더이상 스크롤이 되지 않으며 그 수치는 0이 됩니다.[scroll_00/scroll03.html](http://choan616.dothome.co.kr/study/scroll/scroll_00/scroll03.html)
2. scrollLeft(가로스크롤값)- 조건에 일치하는 요소들의 수평 스크롤의 위치를 value값으로 세팅합니다.[scroll_00/scroll04.html](http://choan616.dothome.co.kr/study/scroll/scroll_00/scroll04.html)

#### .scrollTop()
1. 조건에 일치하는 요소들 중 첫번째 요소의 스크롤바의 수직 위치(y좌표)를 얻을 수 있습니다.[scroll_00/scroll05.html](http://choan616.dothome.co.kr/study/scroll/scroll_00/scroll05.html)
2. scrollTop( value )- 조건에 일치하는 요소들의 수직 스크롤의 위치를 value값으로 세팅합니다.[scroll_00/scroll06.html](http://choan616.dothome.co.kr/study/scroll/scroll_00/scroll06.html)

- - -

##세로 패럴락스 예제
예제는 배경 이미지인 별과 가운데에 있는 지구, 그리고 "parallax"라고 씌어진 이미지들로 구성되어 있습니다.

2. 스크롤 시 각각 다른 속도로 **세로 이동**을 하도록 코딩해봅시다.[scroll_01/scroll_01.html](http://choan616.dothome.co.kr/study/scroll/scroll_01/scroll_01.html)

##가로 패럴락스 예제
예제는 컨텐츠 영역, 뒤에 배경으로 먼 산, 가까운 산. 이렇게 세 부분으로 나뉘어 있습니다. 

1. 요소들을 **가로 이동**하도록 코딩해봅시다.[scroll_02/scroll_02.html](http://choan616.dothome.co.kr/study/scroll/scroll_02/scroll_02.html)
2. HTML5의 data 속성을 이용하여 애니메이션 되도록 코딩해봅시다.[scroll_02/scroll_03.html](http://choan616.dothome.co.kr/study/scroll/scroll_02/scroll_03.html)

##무한 스크롤 예제
페이지를 가장 아래로 스크롤 하면 내용이 **계속 로딩**이 되도록 무한 스크롤을 코딩해봅시다.[scroll_03/infinite_scroll.html](http://choan616.dothome.co.kr/study/scroll/scroll_03/infinite_scroll.html)

##이미지 변경 예제
스크롤에 따라 연속적인 이미지를 **플립북 애니메이션**처럼 재생이 되도록 코딩해봅시다.[scroll_04/flip_animation.html](http://choan616.dothome.co.kr/study/scroll/scroll_04/flip_animation.html)

##플로팅 메뉴 예제
스크롤하면 따라오는 간단한 플로팅 스타일 메뉴를 코딩해봅시다.
