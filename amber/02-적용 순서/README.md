### 상속

상속은  
element 를 디자인할 때 element에 속해 있는 하위 element 가 꾸며진 속성을 이어받게 되는 것.  

상속을 사용하는 이유는 생산성과 관련되어 있다.  

CSS속성들이 모두 상속되는 것은 아니다.  
**상속하는 속성과 상속하지 않는 속성을 찾아보면서 잘 구분해 써야한다.**  
어떤건 상속되고 어떤건 상속되지 않는 것이 있는데 그것을 외우기보다 찾아보면서 그때 그때 쓸 것.  


### 캐스케이딩 이란? (적용 우선순위)

CSS는 **Cascading Style Sheet** 의 약자이다.  
CSS는 1994년 정도에 등장.  

**웹브라우저** 는 html을 해석하는 기계.  
html에는 기본적인 디자인이 되어있다. h1, h2, h3... 으로 크기 구분. link는 밑줄이 있고 파란색이고.  

css에서 대두되는 것이 **우선순위**  


### 캐스케이딩 실습

```JavaScript
<html>
<head>
  <style>
li{color:red;}
#idsel{color:orange;}
.classsel{color:yellow;}
  </style>
</head>
<body>
  <ul>
    <li id="idsel" class="classsel" style="color:powderblue">CSS</li>
  </ul>
</body>
</html>

```

#### Cascading 규칙  
powderblue > orange > yellow > red  
**style attribute > id selector > class selector > tag selector**  

이 모든걸 이길 최강 우선순위는 `!important`  
