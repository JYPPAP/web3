## 21.11.24
#### 오류 사항.
###### 일반
  1. 
  2. 
  3. imi 로고 위치 수정하기
  4. iniPay 이미지 위치 수정하기
  5. 사이드바 팝업 p 위로 올리기
  6. col2의 텍스트 말줄임 처리하기.
###### 860px
  1. basic의 header 제거
  2. list-item의 위치 조정
  3. 빠른거래의 위치 조정
  4. basic의 col1 텍스트 수직정렬 하기
  5. footer의 link에 margin-right 추가하기
  6. sns 로고 정렬하기
#### 수정 사항.
1. 속성값 정렬
2. 레이아웃의 값 이동 (레이아웃만 남기고 전부 이동.)
3. 
## 21.11.19
#### 해야할 일
1. 작은 화면일 때 "물품정보안내"글자를 지웠을 때 해당 정보를 어떻게 사용자에게 효과적으로 인식?시킬 수 있는지.
그냥 없애게 된다면 사용자는 ? 아이콘이 무슨 의미인지 모를텐데 그렇다면 ? 아이콘이 "물품정보안내"라는 사실을 사용자에게 어떻게 인식시킬 것인지 확인하기.
  - 해당 부분의 전체적인 너비와 글자크기를 조절해서 해결하는 방법으로 생각해보기.
  > 450px일 때 filter_item의 margin-right: 15를 0으로 수정.
  > 기존의 "물품정보안내"에 추가한 display:none 삭제
  
2. div 안에 넣었던 텍스트에 대해서 inline 태그로 감싼 뒤 처리할 방법에 대해서 생각해보기
  - 해당 텍스트들은 요소의 중앙에 위치해야 하며 여러줄 일 경우 line-height가 1의 상태로 생성되어야 한다.
3. 작은 화면일 경우 col4의 아이템에 적용되어있는 margin의 크기를 줄이기.
  - 현재 고정값이 상태인데 더 작은 고정값 혹은 작은 비율의 형태로 만드는 것에 대해서 생각해보기.
4. item을 두 줄로 만들 때 어떻게 할 것인지.
  - 1. 일단 item의 너비를 2배로 한다.
  - 2. col1, 3, 4는 float을 그대로 적용하고 col2에 적용되어있는 float을 빼본다.
    - 일단 col2를 아래쪽에 위치시킬 수 있는 방법으로 만들면 됨.
  - 3. item 의 자식요소들의 높이를 전부 60에서 40으로 줄인다.
  - 4. 내부에 있는 텍스트의 높이를 맞춰준다.
    - 할 수 있으면 수직정렬.
    - 여러줄로 해야할 경우 어떻게 해야할 것 인지 고민 필요
 - 5. 물품리스트의 header를 제거한다.
5. Premium의 아이템들의 outline이 비정상적으로 적용되는 것에 대해서 어떻게 처리할 것인지 생각해보기.
  - 일단 box-shadow를 다시 적용하는 것으로 생각해보기.
6. footer에 있는 link를 자연스럽게 줄어들 수 있도록 제작하기.
  - 현재 일정 크기에서 부자연스럽게 확 줄어드는 형태로 제작한 상황.

#### 해야할 일
1. 서버명(col1), 금액 크기(col2) 내부의 텍스트 길이가 길 때 어떻게 처리할 것인지에 대해서 생각하기.
  - 1. 말줄임 처리를 한다.
    - 최대한 온전히 보여줘야 할 정보이므로 말줄임 처리는 안좋을 것 같음.
  - 2. 텍스트의 크기를 줄인다
    - 어떻게?
    - CSS만으로 텍스트의 길이가 길 때 글자의 크기를 줄이긴 힘들 것 같다. 그렇다면 아예 화면의 크기가 줄어들었을 때를 가정해서 만들어야 하는걸까?
      - 이 방법은 뭔가 아닌 것 같음. 긴 줄의 텍스트를 CSS만으로 특정해서 크기를 줄이긴 힘들어 보임.
  - 3. 정중앙에 n줄로 만든다.
    - 인라인태그로 감싸고 몇 가지 추가해주면 될 것 같음.
    - 이게 그나마 가장 괜찮아보임.

2. 화면의 크기를 줄여서 컨텐츠의 크기가 2줄이 되어서 높이를 줄였을 때 처리형태에 대해서 생각하기
  - 일단 가장 중요한 것은 위치잡기.
  - col2에 적용된걸 빼고 inline-block로 만들던가 해서 아래로 내리는게 중요할 것 같음.
  - 위쪽은 float을 이용해서 정렬. 너비에 대해서는 col1, col4를 고정하고 col5는 제거. col3이 나머지 크기를 차지할 수 있도록 만들기. col3도 할 수 있다면 여러줄로 출력될 수 있도록 만드는게 좋으려나?
    -  col3의 내용이 길 때 어떻게 처리할 것인지 생각해보기.
  - col1, col4의 너비를 고정할 때 화면 줄어들면 줄어드는 크기 또한 고려해야 함.
  - item 2줄로 변경시 col4의 아이템들 정렬하기.

3. item에 hover시 위쪽 또는 위, 아래만 hover가 적용되는것을 어떻게 처리할 것인지 생각하기.
  - 아직도 이상함.
  - 예전 방식인 box-shadow?를 사용하는 방법으로 작성할 필요가 있어보임.
  - 이건 뭐가 문제인지 아직도 모르겠음. 
4. 2줄로 변경할 때 서버종류, 물품제목과 같은 header부분을 제거하기.
5. 화면크기 조정시 footer에 있는 링크를 자연스럽게 줄어들 수 있도록 변경하기

## 21.11.08
#### 완료
1. @import는 크로스브라우징이 안된다고 함.
 - caniuse.com 에서는 된다고 나와있었지만 실제로 회의실에서 켜 봤을 때 정상적으로 적용되지 않는것을 확인함.
 > html에 css link를 추가

2. 사이드바가 없어졌을 때 일부의 미묘한 크기일 때, list에 hover시 border-bottom만 보이는 현상이 있음.
 - 대략 1196 ~ 1080 사이일 때만 발생하는것 같음.
 - 그냥 오락가락 한다. 한 번 hover 했을 때는 다 나오다가 2군데, 3군데, 1군데, 4군데 마음대로 나온다.
 > outline 사용하니 정상적으로 출력되는것을 확인함.

#### 해야할 일

3. 화면너비가 작을 때 텍스트의 길이가 길 때를 생각하기.
 - 서버명의 경우에 현재 있는 길이보다 더 길다면 어떻게 할 것인지.
 - 서버명이나 col1, col3이 더 길어졌을 때 어떻게 처리를 할 것인지 고민하기
 - 길다고 고정적인 크기를 더 늘릴 수는 없는것이기 때문.
   - 텍스트가 길어지면 폰트의 크기를 줄이는 방법에 대해서 생각해보기.
     - 어떻게?
4. fLink에 있는 아이템들을 좀 더 매끄럽게 처리할 수 있도록 방법 생각하기
 - 현재는 그냥 margin을 줄이고 끝이지만 저 부분을 좀 더 깔끔하게 처리할 수 있는 방법에 대해서 생각하기.
  - 좀 더 자연스러운 방법에 대해서 생각하기.
5. 물품등록안내 글자가 없어지고 ? 아이콘만 남기는데, 저 부분에 대해서 좀 더 생각하기
 - 화면 크기가 작을 때 없어지면 처음보는 사람은 그 아이콘의 이유에 대해서 모를텐데 이유를 좀 더 명확하게 할 수 있도록 하기.
6. list
 - 두 줄로 변경했을 때, 전체적인 크기 줄이기
 - 아예 col2를 아래로 100%로 만들고, col3, col4를 위로 올리고, col5를 제거하는 방법
 - 높이는 줄이고, 텍스트의 위치도 다시 변경

7. list의 header에 대해서 존재유무, 필요성에 대해서 다시 생각하기
 - 현재 상태는 그냥 한 줄로 만들었지만 크기가 줄어들면 2줄로 바뀌는데 저건 계속 1줄이다.
 - 두 줄로 같이 만들면 너무 커진다. 아예 없애는 방법에 대해서 생각해보기


## 21.11.04-3
#### 해야할 일
1. IE에서 물품정보안내 우측에 ?에 마우스를 올렸을 때 뒤쪽의 아이콘이나 글자가 위로 올라감
  > IE에서 visibility:hidden, visibility: visible로 제어하니 생긴 문제로 display:none, display:block 처리하니 정상작동.

2. IE에서 li 태그에 list-style이 disk 상태로 존재함
  > li 태그도 reset.css에 추가.

3. footer에 sns 로고가 760일 때 겹쳐서 미디어쿼리를 780으로 수정.

## 21.11.04-2

1. 배너가 화면을 축소해도 전부 보일 수 있도록 만들기
  > 내부에 img 태그를 추가
  > 부모영역의너비를 100%로 지정 h는 auto(기본값)
  > img태그의 max-width: 100%로 지정.
  이렇게 하면 최대너비는 부모영역을 따라가고 축소하면 비율유지되는 상태로 잘 동작함.

2. 물품검색버튼의 크기 조절하기
  > 검색창이던지 버튼이던지 크기가 안맞음.
  > 초기화값 box-sizing:border-box를 box-sizing:content-box로 변경

3. 게임머니, 아이템, 기타, 물품제목의 글자가 너무 큼.
  > font-size:13px으로 수정 완료.

4. 프리미엄 등록안내 왼쪽여백 추가하고, after로 생성한 >>>를 글자 옆으로 붙여야 함.
  > letter-spacing: -1px로 여백 생성, :after에 margin-left를 margin-right로 변경

5. 물품리스트의 필터를 더 아래로 옮기기
  > display: inline-block, vertical-align: bottom으로 아래로 내려가긴 했음.

6. 물품정보안내부분도 바닥에 붙이기
  > right로 묶인 부분에 margin-top: 10px 추가.

7. 물품리스트에 hover시 2번째부터 흰색의 위쪽 여백제거.
  > .item에 전체적으로 margin-bottom: 5px가 적용되어 있었고,
  .premium에만 필요하기 때문에 옮김.

8. 배너3 아래에 높이 늘리기. 현재 조금 좁음.
  > footer에 mt50을 줘버림.
  > 현재 margin중복으로 30만 적용된 상태였기 때문에 그냥 50을 줘버림.
  > 나중에 필요하다면 수정을 해보는 것도 좋을 것 같음.

9. footer에 link 위치 수정하기
  > 이용약관부터 옆으로 조금씩 밀린 상태
  > display: inline-block이 문제였음.
  > 이유는 모르겠지만 이거때문에 옆으로 내용이 밀린거였음.

10. 1080이상일 때 sns 아이콘 오른쪽 벽에 붙이기
  > link를 float:left로 수정하니 해결 완료.

11. iniPay 이미지 추가하기
  > 이미지 추가 및 위치조정 완료

12. pointer 추가할 것들.
  1. 배너
  2. 게임머니, 아이템, 기타
  3. 검색버튼(버튼만)
  4. col1의 글자
  5. col2의 글자
  6. 물품리스트의 필터 4개와 before로 잡아놓은 공간
  7. ?와 refresh 아이콘
  8. 사이드바의 아이콘(아이콘만)
  9. footer의 sns 버튼
  10. iniPay 이미지

13. 완료 후 IE로 체크하기.
14. 미디어쿼리에서 제거할 부분. col2를 어떻게 처리할것인지 다시 생각하기.
  - 현재 dn_text를 지우는 부분이 과연 적절한 것인지
  - 텍스트의 크기를 줄이거나 높이를 키우는 방법으로 접근해보는것은 어떤지에 대해서 고민하기.
  - 미디어쿼리에서 빠른거래 아이콘의 처리에 대해서 생각하기.
  - 600정도에 빠른거래 제거.
  - 1000에 iniPay 이미지 관련 설정이 필요할 것 같음.
    - float으로 변경?
  - sns가 아래로 내려오면 iniPay와 겹침
  - fInfo에 배경이 추가되어야 함.
  - police 이미지가 내려왔을 때 border-top이 적용되어있는지 확인 필요
  - link를 벽에 붙이지 말고 중앙정렬에 여러줄로 처리할 수 있는 방법에 대해서 생각해보기
  - info 부분을 dib에서 db로 변경해서 한 줄로 쭉 버리는것에 대해서 생각해보기.
  - link가 2줄이 될 때 hr의 위치도 아래쪽으로 이동할 수 있도록 변경하기.
  - 판매리스트를 아예 2줄로 만드는 것에 대해서 고민해보기.
    - 높이를 변경하고 서버 | 물품 제목 20: 80의 비율
  판매금액 | 물품정보(크기 그대로) | 등록시간 30:50:20의 비율
    - 기존 상태에서 아예 수정을 진행하여 보여줄 수 있는것을 길게 보여주는 방법을 통해서 만들어보기.
    아예 1080일 때 로 지정해서 예전것 싹 버리고 새로 생성.
15. footer에 있는 hr 태그 수정하기
  - 현재 너무 두꺼움. 얇은 선으로 변경이 필요함.
  > hr태그가 아니라 link에 border-bottom으로 이상한게 들어있어서 제거 후 정상 처리함.


## 21.11.04
* 전체적인 내용을 완료한 상태
#### 해야할 일
1. 빠져있거나 바꾸면 좋을 것 같은 부분들 찾아서 수정하기
2. list들과 footer의 미디어쿼리 최적화하기