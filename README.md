# MadCamp-Week2

# 몰입캠프 Week2 Project : 말랑말랑
김태연, 방준형
## 프로젝트 개요
말랑말랑은 슬라임을 서버를 통해 사고팔고 레벨업하며 농장을 키워나갈 수 있는 힐링 게임이다. http 방식을 사용하여 서버와 통신하므로 양방향 통신은 불가하지만 게시판에 자신의 생각을 업로드하고, 다른 사람의 생각을 확인하며 여유롭게 게임을 즐길 수 있는 매력적인 2d 게임이다.

## 기능 설명
### 카카오 APK 로 로그인
>Kakao developers의 로그인 API를 활용하여 계정생성과 로그인이 가능하다. 참고한 페이지는 공식 페이지와 유용한 블로그페이지이다.
https://developers.kakao.com/docs/latest/ko/kakaologin/flutter
https://domdom.tistory.com/entry/flutter-%ED%94%8C%EB%9F%AC%ED%84%B0-%EC%B9%B4%EC%B9%B4%EC%98%A4-%EB%A1%9C%EA%B7%B8%EC%9D%B8-%EA%B5%AC%ED%98%84%ED%95%98%EA%B8%B0  

>애플리케이션을 실행시키면 로그인 페이지가 다음과 같이 출력되며 카카오 계정 혹은 카카오톡으로 로그인이 가능하다.  

>로그인 작업이 수행되면 서버에 node js를 통해 sql 쿼리문으로 해당 유저가 존재하는지 확인하고 존재하지 않을 시 유저를 추가하여 계정을 생성해 준다. 상단 탭의 drawer의 logout버튼으로 로그아웃이 가능하다.  

>로그인 시 프로필 및 닉네임에 대한 요청을 필수적으로 수락해야 게임을 할 수 있으니 필히 하도록 하자.

### 홈화면: 아이템 감상과 슬라임 터치, 여타페이지로의 이동

![](https://i.imgur.com/V0nbn5s.png)


>홈 화면에서는 가지고 있는 슬라임과 보유한 포인트, 다이아를 확인할 수 있다. 레벨에 따라 다른 배경에서 자유롭게 움직이는 슬라임을 감상할 수 있다.

>화면을 터치하면 일정량의 포인트(슬라임 수와 희귀도에 비례)를 얻을 수 있으며, 화면 곳곳에 랜덤으로 존재하는 다이아를 클릭하면 하루에 최대 10개까지 획득할 수 있다.

>화면 좌측 상단 서랍 바와 하단 4개 버튼을 이용해 다른 화면으로 넘어갈 수 있다.

### 왼쪽 서랍 바: change nickname, logout, level up
![](https://i.imgur.com/yUbMwMu.png)

>왼쪽 서랍 바를 열면 닉네임 변경, 레벨업, 로그아웃 버튼이 있다. 로그아웃 버튼을 누르면 게임에서 로그아웃할 수 있다.

>레벨업 버튼을 누르면 레벨업 화면으로 넘어간다. 일정량의 포인트를 지불하여 다음 레벨로 넘어갈 수 있으며, 레벨을 올리면 뽑기에서 좋은 슬라임이 나올 확률이 상승하고 슬라임 인벤토리 칸이 증가한다.

>닉네임 변경 칸에서 자유롭게 닉네임을 설정할 수 있다.


### 인벤토리: 슬라임 확인, 방출, 경매.
![](https://i.imgur.com/Y6K6seR.png)

>인벤토리에서는 가지고 있는 슬라임의 등급과 이름을 확인하고, 방출과 경매 버튼을 이용해 슬라임을 방출하거나 판매할 수 있다.

>슬라임 방출 버튼을 누르면 정말로 방생할지 선택할 수 있다.

>슬라임 판매 버튼을 누르면 슬라임 판매가를 설정하여 판매할 수 있다. 판매 리스트에 올라간 슬라임은 마켓에서 확인할 수 있다.


### 슬라임 마켓

<img src="https://i.imgur.com/0qGbsxx.jpg" width="200" height="400">
> 슬라임 아이템들은 인벤토리의 경매 탭을 이용해서 판매할 수 있다. 판매를 요청하면 서버에서 해당 아이템들의 가격 변경을 수행해 주고, 경매에 올라온(가격이 0이 아닌) 아이템들을 반환해 준다.


> 마켓에서는 "입양하기"를 선택해서 슬라임 아이템을 받아올 수 있다. 슬라임을 구매하면 소유주가 바뀌고 원 소유주에게 포인트가 전달된다.
> 

### 갓챠: 랜덤뽑기, 자랑하기, 게시판.

<img src="https://i.imgur.com/0yC6UwN.jpg" width="200" height="400"><img src="https://i.imgur.com/0JltYAF.jpg" width="200" height="400">
> 인벤토리에서 갓챠 버튼을 선택하면 다이아 재화를 이용해서 슬라임을 랜덤뽑기할 수 있다. 뽑기한 슬라임을 게시판에 게시하여 자랑할 수 있다.


> 추가된 아이템은 인벤토리에 저장된다.
### 이웃들: 구경하기, 검색. 다이아 찾기.


이웃 탭에서는 이웃들 페이지를 방문하여 구경할 수 있다. 이웃들 탭을 방문하여 다이아몬드를 수집하고, 이웃들의 농장을 구경할 수 있다. 레벨에 따라 서로 다른 스킨을 가지고 있으며, 이를 관찰할 수 있다.
<img src="https://i.imgur.com/x4QqGRE.jpg" width="200" height="400">

### 개선사항
소켓을 이용하여 양방향 통신을 사용한다면 유저들간의 소통을 지원할 수 있으며, 마켓에서 구매 활동이 일어나는 즉시 금액 반영이 가능하다. 소켓을 이용한 통신을 지원한다면 더 다양한 기능을 만들 수 있을 것이다.
