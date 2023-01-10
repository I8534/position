# position

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


Z-Index

	position 속성이 없는 태그들은 나오는 순서대로 쌓임
	position 속성이 있는 태그들은 없는 태그들보다 위에 나오는 순서대로 쌓임.
	position 속성에 z-index까지 있다면 z-index가 큰 태그가 위에 쌓임.
	z-index가 아무리 크더라도 부모 태그의 z-index가 더 우선임
            z-index는 형제끼리의 비교에 사용


