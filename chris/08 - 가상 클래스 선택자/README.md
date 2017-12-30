# 가상 클래스 선택자

Pseudo class selector

클래스 선택자처럼 동작하지만 클래스선택자는 아니고

여러가지 엘리먼트의 상태에 따라서 엘리먼트를 선택하는 선택자

```html
<html>
  <head>
    <meta charset="utf-8">
    <style>
      a:link {
        color: black;
      }
      a:visited {
        color: red;
      }
      a:active {
        color: green;
      }
      a:hover {
        color: yellow;
      }
      a:focus {
        color: white;
      }
    </style>
  </head>
  <body>
    <a href="https://opentutorials.org">방문함</a>
    <a href="https://a.a">방문안함</a>
  </body>
</html>
```

기본적으로 먼저 선언한게 우선순위가 높음.

focus는 가장뒤에 놓는것이 좋음.