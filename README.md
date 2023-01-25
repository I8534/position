# position

*** 이 부분이 굉장히 중요 ***

명심!! 포지션 앱솔루트는 상위요소 즉 부모요소 중에 릴레이티브 먹는 것을 기준으로 한다.

position을 먹일려면 박스요소에다 해야 한다.

position relative가 static보다 위에 있다. absolute는 relative보다 위에 있다. html 태그 상 fixed가 위에 입력된 경우fixed는 absolute보다 위에 있다. 
z index를 입력하지 않은 경우를 전제로.

너무 당연하다 abosulte는 붕 떠있기 때문이고, 

이 fixed는 top left right bottom의 값이 없으면 뷰포트 기준으로 그냥 원래 있어야 할 곳에 있다. 그래서 안 보일 수가 있다.

html상 형제 요소로 아래에 위치하거나 뷰포트 밖에 있어서 스크롤을 내려야 볼 수 있다면 그 상황에서 픽스드만 입력하면 안 보인다. 즉 화면 밖에 위치하기 때문에 안 보인다.

fixed의 기준은 뷰포트이기 때문이다. 당연히 fixed에 위치값을 입력하면 맨 위에 있게 된다.

그리고 부모의 zindex가 더 중요하다. 가령 자식 요소의 zindex는 5이고 그 부모 요소는 1이라고 하자 그 부모요소와 형제인 요소가 fixed이고 zindex가 일이면 충돌한다.

자식 요소가 5인 것은 안 중요하다.
sticky relative는 우선 순위 없다.

사실 모든 요소는 우선순위가 없다. abosolute는 붕 떠있는 것이고 나머지 요소들은 특정 상황이 없으면 그냥 원래 스태틱 상태인 것이랑 같다. fixed는 뷰포트 밖으로 안 나가게 조심.

https://creamilk88.tistory.com/197

ㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡ

0. position css

css 상에서 position을 입력할 때 방법이다.

우선 positino:static은 그냥 html 상에서 입력했을 때 모습 그대로 보여준다

즉 따로 입력할 필요는 없다.

즉 top left right bottom을 입력해도 움직이지 않는다.

그러나 transform：translate(x, y) 값을 통해서 움직일 수 있다.  

** 밑에서 배우는 position 값을 입력할 때는 top left right bottom 값이 반드시 하나라도 있어야 한다.

1. position: fixed는 왜 사이트 갔을 때 계속 옆에서 쫒아는 놈이 있지 않나 그거이다.

position: fixed
top: 30px
right 30px이면 
위에서 밑으로 30px 내려오고
오른쪽 창 기준으로 왼쪽으로 30px 밀어버린다.

** fixed를 하면 디스플레이 플렉스에 저스티파이 스페이스 비트윈 해서 너비를 넓혔다고 하더라도
원래대로 돌아온다. 픽스드의 속성이다.
** 정 넓히고 싶다면 밑에 width:100vw를 쓰는 수 밖에 없다.

position fixed를 입력하면 갑자기 잘 있던 가로 너비가 확 줄어드는 경우가 생기는데 왜 그러는건지.
원래 픽스드 속성이다. 딱 자기가 갖고 있는 요소의 너비만큼만 고정이 된다. 그래서 너비값을 정확히 지정을 해줘야 한다.

position: fixed;
right: 30px

만 입력하면 오른쪽 옆에 붙는데 아무 위치에나 붙는다. 그래서 높이값을 설정해줘야 한다.

position: fixed;
top: 0;
right: 0;

이렇게 값을 입력하면 맨위 오른쪽으로 붙는다.

*** 포지션 픽스드로 잡을 때 부모 안에서 픽스드만을 입력하면(대신 위 아래 좌 우 입력 안 하는 경우) 그냥 구석탱이 위에서 자리를 잡고 있다. ***
근데 아무데도 속해있지 않고 픽스드만을 입력하면(대신 위 아래 좌 우 입력 안 하는 경우) 화면 밖으로 사라진다.

2. position: relative는 본인이 있던 위치에서 움직이는 것이다.

position: relative;
relative가 움직이는 기준은 원래 위치를 기준으로 이동하는 것이다.
top: 50px;
left: 50px;

*position:absolute는 relative 기준으로 움직이는데

만약 릴레이티브 먹은 애를 움직일 필요가 없는 상황이면 

그냥 css에 position relative만 입력하면 된다.

3.

.wrapper {
position: relative;
}

.position div {
background-color: greenyellow;

position: absolute;
만약 부모 박스(wrapper)에 박스 기준이 없으면 바디를 기준으로 뷰포트 최하단(보이는 화면 최하단)에 위치하게 된다. */
왜냐면 position: absolute는 기준을 자신이 아닌 상위 요소에서 찾는데 상위요소 태그 중에 relative 기준으로 움직임
즉 wrapper라는 박스 기준으로 포지션을 잡는 것이다. 즉 wrapper 박스 안에서 바닥에서 20만큼 뜨고 오른쪽에서 20만큼 멀어지는 것이다.
만약 기준이 없다면 최상위에 있는 body가 배치 기준이 됨. */
}




참고) z-index: ;는 그림이 겹칠 수도 있다. 근데 위에 올리고 싶은 그림이 있으면 제트 인덱스 값을 입력함으로서 위 아래를 정할 수 있다

마이너스 플러스 값 입력도 가능하다.

 /* 공중에 떠있는 속성들 중에 누가 맨 앞에오고 누가 뒤에 올 것인지 정해주는 속성이다. 숫자가 높을 수록 앞으로 감.
  이 제트 인덱스는 포지션이 있을 때만 적용이 가능하다. */


부모 엘리먼트 내부에 속박되지 않고, 독립된 배치 문맥(positioning context)을 가지게 됩니다. 
마치 포토샵 같은 그래픽 툴에서 새로운 레이어를 추가하는 효과에 비슷하다고 생각하시면 됩니다.
따라서, 엘리먼트를 기본적으로 브라우저 화면(viewport) 상에서 어디든지 원하는 위치에 자유롭게 배치시킬 수 있으며, 심지어 부모 엘리먼트 위에 겹쳐서 배치할 수도 있습니다.
단, 상위 엘리먼트 중에 position 속성이 relative인 엘리먼트가 있다면, 그 중 가장 가까운 엘리먼트의 내부에서만 엘리먼트를 자유롭게 배치할 수 있습니다. 
즉, 전체 화면이 아닌 해당 상위 엘리먼트를 기준으로 offset 속성(top, left, bottom, right)이 적용됩니다.

여기서 중요한 것은 position absolute는 붕 뜬 상태라는 것이다. 박스를 만들어보고 엡솔루트를 적용해보면 홈페이지 상으로는 박스안에 포함이 안 된 것으로 나온다. 그러나

html 태그 상으론 포함이 되어있다. 즉 글씨 색깔 같은 것은 다 적용이 되는데 위치가 붕 뜬 것이다. 그래서

display flex를 적용시켜보면 absolute 밑으로 요소가 들어간다. 가령 세개의 네모를 만들었을 때, 가운데 사각형한테 포지션 앱솔루트를 넣으면 걔는 이제 디스플레이 플렉스가 적용이 안 된다.

즉 혼자 완전히 다른 세계에 있다는 것이다.



<div class="search">
<input type="search" placeholder="스토어 검색">
<i class="fa-solid fa-magnifying-glass"></i>
</div>

search에 position:relative 주고 i 에 포지션 앱솔루트를 줬다고 해보자

이러면 html 마크업 상으로는 search라는 박스 안에 포함되어있는데

막상 사이트 가서 검사해보면 search안에 포함이 안 되어 있다. 붕 떠있따고 생각하면 된다.


4.  position: sticky;
  top: 50px;

메뉴 중에 어느 정도 따라 내려오는 것이 있다. 바로 그것이다.

정해진 박스 안까지만 따라 오는 것이다.

즉 부모의 박스 높이 값이 정해져있어야 그 높이만큼 내려가는 것이다.

<div class="wrapper">
   <header>

즉 스크롤 내리는만큼 따라 내려오는 메뉴를 보고 싶다면 header에

position: sticky;
top: 0px;

을 입력해야 한다. 총 높이는 wrapper가 갖고 있기 때문이다.

위의 fixed와의 차이점은 fixed는 자기 고정 위치에서 스크롤해도 움직이지 않고 어떤 경우에도 움직이지 않지만, 
sticky는 스크롤 할 때 일반 문서의 흐름에 따라 움직인다.

When to use fixed : 언제 fixed를 써야할까
So with that in mind, we want to use fixed
when it must always be on the same place on the page at all times. It simply doesn’t move.

When to use sticky : 언제 sticky를 써야할까
You’ll want to use sticky
when you specifically have something that you want to scroll into view and then stop once it reaches a certain point.


포지션 스티키를 입력할 때 부모의 높이가 움직이는 한계가 된다고 했다. 

학원에서 배우는 기준으로 말하자면 사이트 높이 전체를 하고 싶으면 wrapper 클래스의 높이를 따로 지정할 필요 없이

wrapper 스티키가 들어있는 태그를 가능한 래퍼의 자식으로 두면 된다.

왜냐 어차피 박스 래퍼의 높이는 결국 구성요소들이 알아서 결정하니깐 알아서 되는 거다.


포지션을 입력할 땐 높이값이든 왼쪽 오른쪽 값이든 뭐든지 반드시 입력해줘야 한다.



ㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡ

Z-Index

	position 속성이 없는 태그들은 나오는 순서대로 쌓임
	position 속성이 있는 태그들은 없는 태그들보다 위에 나오는 순서대로 쌓임.
	position 속성에 z-index까지 있다면 z-index가 큰 태그가 위에 쌓임.
	z-index가 아무리 크더라도 부모 태그의 z-index가 더 우선임
            z-index는 형제끼리의 비교에 사용

ㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡ

.gnb-wrapper {
  position: relative;
  width: 95%;
  height: 50px;
  margin: 0 auto;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.logo {
  height: 40px;
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
}

display:flex는 기존의 블록요소를 너비부분을 갖고 있는 자손의 너비만큼으로 바꾸는 것이다. 인라인요소만큼 바꾸는 것이다.


.logo {
  height: 40px;
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
}

근데 이 것은 특정값을 완전 가운데로 이동을 시키는 것이다. 즉 ABC인 것을 BAC로 바꿀려고 하는 것이다. 

이게 가능한 것은 absolute를 받는 요소는 붕 떠있어서 display flex의 영향을 안 받는다.

  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  
이것은 인위적으로 한가운데로 옮겨버린 것이다.

ㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡ

.drawer-menu.is-open .fa-chevron-down {
  transform: translateY(-50%) rotate(180deg);
}
/* 화살표가  돌아가면 살짝 아래로 내려가니 그 내려간 높이를 잡아주는 것이다.*/

돌아가면 총 높이가 두배가 된다. 거기서 다시 반만큼 올려주라는 것이다.
/* .drawer-menu에 포함되어야 하니깐 같이 쓴 거다. */



거리를 %로 표시할때 : 이동시키는 태그의 크기의 해당 % 만큼 이동한다. 

아래의 내용은 100% 이므로 오른쪽으로 200px (태그의 width는 200px 이다) 이동했다. 

position: absolute;
top: 50%;
left: 50%;
transform: translate(-50%, -50%);

완벽하게 가운데에 두는 css 식이 이것인 이유가 바로 이거이다. 

점이라면

position: absolute;
top: 50%;
left: 50%;

만 해도 딱 가운데에 온다 근데 가로 200px, 세로 200px라면 자체 갖고 있는 크기 때문에 완전히 가운데로 가지 못한다.

그래서 transform: translate(-50%, -50%);을 입력하게 되면 

갖고 있는 가로 200의 절반, 세로 200의 절반인 100px만큼 이동하게 되면서 딱 가운데로 가게 된다.

ㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡ

.mac-story-box {
  position: sticky;
  bottom: 0;
  
}

바닥에 붙는 메뉴 만들 때

ㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡ





