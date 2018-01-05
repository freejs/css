### 선택자와 선언

```JavaScript
h1{color: red; font-size: 12px;}
```

- color → `Property` `속성`  
- red → `Value` `속성값`  
- : → `Value-Property Separator` `구분자`  
- ; → `Declaration Separator` `구분자`  

- h1 → `선택자`  
- color: red; font-size: 12px; → `선언`  


### ID 선택자 (선택자의 종류)

```JavaScript
<html>
  <head>
    <style>
    li{
      color:red;
      text-decoration:underline;
    }
    #select{
      font-size: 50px;
    }
    </style>
  </head>
  <body>
    <ul>
      <li>HTML</li>
      <li id="select">CSS</li>
    </ul>

  </body>
</html>
```

id로 꾸며줄 때에는 앞에 #을 붙여줘서 지칭한다.  


### 부모 자식 선택자

```JavaScript
#lecture>li{
  border: 1px solid red;
  color: orange;
}
```

lecture 라는 ID의 직계 li만 선택  


### 선택자 공부 팁

선택자는 CSS에서 주어같은 역할.  

**CSS Cheat Sheet** 찾아보면서 하면 좋음.  


### 가상 클래스 선택자 (pseudo class selector)

가상 클래스 선택자를 통해 링크 꾸며주기.

```JavaScript
a:active{
  color:green;
}
```

마우스로 누르고 있으면 초록색이 된다.

```JavaScript
a:hover{
  color:yellow;
}
```

마우스를 올려놓으면 노란색이 된다.

- `:link` – 방문한 적이 없는 링크
- `:visited` – 방문한 적이 있는 링크
- `:hover` – 마우스를 롤오버 했을 때
- `:active` – 마우스를 클릭했을 때
-  `:focus` - 선택이 되었을 때(?), 순서상 가장 마지막에 효과를 주는 것이 좋다.
