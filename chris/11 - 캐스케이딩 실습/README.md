# 캐스케이딩 실습

```html
<html>
  <head>
    <meta charset="utf-8">
    <style>
      li {
        color: red;
      }
      #idsel {
        color: blue;
      }
      .classset {
        color: green;
      }
    </style>
  </head>
  <body>
    <ul>
      <li>HTML</li>
      <li id="idsel" class="classsel" style="color: powderblue">CSS</li>
      <li>JavaScript</li>
    </ul>
  </body>
</html>
```


중첩이 발생했을때, 

> 우선순위 inline(style attribute) > id > class > tag
