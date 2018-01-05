### flex 소개

flex는 주로 레이아웃을 잡을 때 쓰는 기능이다. 레이아웃은 컨텐츠를 만들 때 컨텐츠를 잘 정리정돈해서 구조화시킬 때 사용하는 것이 레이아웃이다. 레이아웃은 매우 중요한 주제.  

TABLE 레이아웃- 수정 어려움.  
POSITION 레이아웃  
FLOAT 레이아웃- 이해하기 어려움.  

...
드디어 궁극의 레이아웃 방법이 등장하는데 그것이 바로 FLEX.  

```javascript
<container>
  <item></item>
  <item></item>
</container>
```

기본적인 태그로는 컨테이너 역할 태그와 자식 역할하는 태그가 있다.  
그리고 컨테이너에서 쓰이는 속성과 아이템에서 쓰이는 속성들이 구분되어 있다.  
이것을 잘 구분해서 어떤 것은 컨테이너에게 주고 어떤 것은 아이템한테 주는지 코딩해야한다.  


### flex의 기본

```javascript
.container{
  background-color: powderblue;
  display: flex;
}
```

부모를 flex로 만들어주는 것 부터 시작이다. 기본.  

```javascript
.container{
  background-color: powderblue;
  display: flex;
  flex-direction: row; /*태그들이 반대쪽으로 가서 정렬된다.*/
}
```

`flex-direction` 으로 위치와 방향 설정 가능.  
row, cloumn, row-reverse, column-reverse.  


### flex-grow& shrink

flex 관련 중요한 속성 세가지. container가 아닌 item에게 해당되는 속성.  
`flex-basis` 는 flex방향에 해당되는 element의 크기를 지정하는 것이다.  
`flex-grow` 는 여백의 비중 결정하는 것. 기본값은 0.  
`flex-shrink` 는 flex-grow의 반대 기능. 0 일 때에는 공간을 갖고있는 부분만 줄어든다.(페이지를 줄일시) 1로 두면 페이지 크기를 줄이더라도 갖고있는 공간을 유지한다. 기본값은 1.  
shrink를 사용하기 위해서는 어떤 특정 element가 basis 값을 가지고 있을 때.   

어렵.  


### flex-holy grail layout

```
      Header
────┬────────┬────
Nav │  Main  │ AD
────┴────────┴────
      Footer
```

holy-grail : 성배  
화면의 크기에 따라서 main의 크기가 작아진다.  


### flex-기타 속성들

해보기  
https://opentutorials.org/module/2367/13526

**container에게 주어지는 속성들**

- `flex-direction` row(기본값)/ row-reverse/ column/ column-reverse  
- `flex-wrap` nowrap(기본값)/ wrap/ wrap-reverse  
컨테이너의 크기보다 아이템들의 합의 크기가 클 때, wrap을 하게 되면 아이템들은 줄바꿈이 되어 아래쪽으로 내려간다.  
- `align-items` flex-start/ flex-end/ center/ baseline/ stretch(기본값)  
flex의 direction은
컨테이너에 아이템들이 있고 그 컨테이너가 flex가 되는 순간에 아이템들은 컨테이너의 높이값과 같아진다. 아이템들이 stretch 상태이기 때문. 각각의 아이템들이 자신의 컨텐트 크기만큼이 되려면 flex-start 또는 flex-end를 해주면 된다.  
- `justify-content` flex-start/ flex-end/ space-between/ center/ space-around  
- `align-content` flex-start/ flex-end/ center/ space-between/ space-around/ stratch  

**item에게 주어지는 속성들**
- `align-self` auto/ flex-start/ flex-end/ center/ baseline/ stretch  
특정한 것만 예외적으로 다르게.  
- `flex-grow`  
- `flex-shrink`
- `flex` flex-grow, flex-shrink, flex-basis 를 축약한 것이다.  
- `order` 아이템들의 순서를 바꾸고 싶을 때.  


### 미디어쿼리 기본

미디어의 상태를 미디어에게 물어봐서 그 상태에 따라서 다른 디자인을 할 수 있게 한다.  
그런 상황에서 그 장치에 적합한 디자인/ 표현을 할 수 있도록 해주는 기술이 바로 **미디어 쿼리**  

반응형 디자인 : 화면의 크기에 능동적으로 반응해서 거기에 최적화된 모습을 보여준다.  


```javascript
  <style>
  /* 화면의 크기가 500px이하일 때 바디 태그의 background-color를 붉은색으로 한다.*/

  @media (max-width: 600px){
    body{
      background-color: green;
    }
  }
  @media (max-width: 500px){
    body{
      background-color: red;
    }
  }
  </style>
```  

*나머지 모든 캐스케이딩의 조건이 같다면 코드가 나중에 나오는 것이 우선순위가 높아진다.*


```javascript
<meta name="viewport" content="width=device-width, initial-scale=1.0">
```

*모바일에서도 화면이 알맞은 크기로 조절됨(?)*


### 미디어쿼리 응용

호오옹ㅇ이


### float 기본

float의 사전적 의미 붕 뜨다, 부유하다.  

글의 본문 안에서 image를 삽입 할 때, 자연스럽게 삽입하기 위한 것.  
layout을 잡을 때에도 이용하기도 한다.  

```javascript
  <p style="clear: both;">
```  

p태그의 float가 right일 때에만 clear시킨다.  


### float을 활용한 holy grail 레이아웃

호오오옹이2


### 다단 만들기

멀티 컬럼 : 신문과 같이 화면의 크기가 큰 매체에서 사용하는 전통적인 레이아웃 기법.  
컬럼을 조각조각 나눠서 좀 더 읽기 편하게 만드는 것을 멀티 컬럼 기법이라고 한다.  
