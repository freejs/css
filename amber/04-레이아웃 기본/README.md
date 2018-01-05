### 인라인 VS 블럭레벨  

html의 여러 태그들은 그 태그의 성격에 따라서 화면 전체를 쓰는 태그와 자기 자신의 크기만큼만 쓰는 태그로 나눠진다. inline 방식과 block level 방식.  
어떤 것이 블록이고 어떤 것이 인라인인지 알아보자.  

```javascript
<html>
  <head>
    <style>
      h1, a{border: 1px solid orange;}
    </style>
  </head>
  <body>
    <h1>Hello world</h1>
    안녕하세요. westbro입니다. <a href="https://opentutorials.org">생활코딩</a>입니다.
  </body>
</html>

```

h1태그는 자동으로 줄바꿈이 된다.  
h1은 전체 크기를 쓴다. = **블럭 레벨 엘리먼트**  

a태그는 자동으로 줄바꿈이 되지 않는다.  
a태그는 딱 자기 크기만큼만 쓴다. = **인라인 태그**  

```javascript
h1{display: inline;}
a{display: block;}
```

*인라인을 블럭으로 블럭을 인라인으로 얼마든지 바꿀 수 있다.*  


### 박스모델

박스모델은 각각의 태그들이 웹페이지에 표현될 때 부피감을 결정한다. 여백, 위치, 크기 등등.  
왜 박스라는 표현을 썼을까?  
각각의 태그들은 태그 바깥 쪽 박스와 같은 모양으로 둘러쌓여 있다.  

**인라인 태그들에게는 width 와 height값이 무시된다.**  

### box-sizing

어떤 element의 크기(width, height)를 지정할 때, element 가 padding이나 border나 이런 값들을 가지고 있는 경우 내가 지정한 사이즈가 예상한 것과 다른 경우가 생긴다.  
왜 그런 경우가 생길까?  

**element의 크기는 margin도 제외하고 border도 제외한 부분만을 지정한다.**

그래서 이러한 것을 해결하기 위해 등장한 것이 `box-sizing`이라는 속성이다.  
content의 크기만큼 width와 height가 지정이 되는데,  border-box로 바꾸면 margin과 border가 포함된 크기를 맞춘다.

```javascript
*{ /*모든 element를 지칭한다.*/
  box-sizing: border-box;
}
```  

### 마진겹침(margin-collapsing) 1

마진이 어떤 경우에 사라져버리는 현상이 있다. **마진겹침 현상**  
**사례1** 위 태그와 아래 태그의 마진이 겹쳤을 때,  
*위 태그와 아래 태그의 마진 값 중에 더 큰 값이 두 개의 태그 사이의 간격이 된다.*  

**만약 마진겹침 현상이 없었다면?**  
리스트를 만들 시, 리스트간 간격이 두 배가 된다. 그럼 보기 안좋음.  


### 마진겹침(margin-collapsing) 2

**사례2**  
부모 element 아래 자식 element가 있는데, 부모 element과 자식 element 모두 마진이 있는 경우 겹칠 수 있는 현상.  
*부모 element의 시각적 효과가 없는 투명한 효과일 때, 부모 태그와 자식 태그 중 더 큰 값이 마진이 된다.*  

### 마진겹침(margin-collapsing) 3

*어떤 태그의 시각적 효과가 없다면 그 태그의 마진 값은 위쪽 마진값과 아래쪽 마진값 중 더 큰 값이 마진 값이 된다.*  


### 포지션(position)- relative VS static

각각의 html의 태그들이 화면상 어디에 위치할 것인가를 결정한다.  

상대 위치와 정적 위치.  

```javascript
<!DOCTYPE html>
<html>
  <head>
    <style>
        html{border:1px solid gray;}
        div{
            border:5px solid tomato;
            margin:10px;
        }
        #me{
            position: relative;
            left:100px;
            top:100px;
        }
    </style>
  </head>
  <body>
    <div id="other">other</div>
    <div id="parent">
       parent
       <div id="me">me</div>
    </div>
  </body>
</html>
```

포지션 타입이 relative일 때 오프셋을 사용할 수 있다. 상대적 위치.  
(오프셋: top, bottom, left, right 속성)    
static일 때는 오프셋 상관없이 정직인 위치에만 위치.  

### 포지션(position)- absolute

절대적 위치.  

포지션 기준을 html로 한다. 부모element가 아닌 화면 전체에서의 위치 기준.  

relative : 부모 element 기준  
absolute : 부모 중 position type이 지정된 부모 element 기준. 그리고 부모도 자식을 없는 셈치게 된다. 크기도 블럭레벨에서 인라인으로 바뀜.  

absolute를 처음 지정하게되면 absolute의 left과 top은 바로 0px, 0px이 아니고 부모 element를 기준으로 한 위치가 기본 값으로 지정된다. 그 상태에서 left값과 top값을 주게 되면 그제서야 html을 기준으로 위치가 바뀌게 된다.  

즉, 기본 값은 자기가 원래 있기로 한 위치.  

또한 어떠한 element를 absolute로 지정하게 되면 그 element는 더 이상 부모 소속이 아니다. 부모와의 link가 끊기게 된다. 그래서 블럭레벨 엘리먼트에서 인라인 태그로 바뀌게 된다.  

이때, 부모의 position 이 relative면 부모의 기준으로 오프셋을 매기게 된다.  
**정확히 말하자면, element의 postitino이 absolute면 html을 기준으로 하기 보다는 position 이 static이 아닌 부모를 기준으로 한다. 없을 경우 타고 타고 올라가서 html기준이 되는 것.**  


### 포지션(position)- fixed

고정된 위치.  

페이지 스크롤과는 무관하게 자기 위치에 고정되어 계속 display된다. 특정 element를 스크롤로부터 독립시키고 화면에 완전 고정시키고 싶을 때 fixed를 쓴다.  
fixed도 인라인 속성을 갖는다. 자기 크기만큼만. fixed 또한 부모와 인연 끊음. 부모 element는 자식 element의 크기를 포함하지 않는다.   
