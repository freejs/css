### 배경(background)

백그라운드(background) : 원하는 특정 element에 배경 이미지나 배경 컬러를 지정하는 것.  

```javascript
background-size: contain;
background-size: cover;
```

background-size: contain을 해주면 배경이미지를 손실없이 다 채워넣는다.
background-size: cover을 해주면 배경이미지가 화면에 다 보이도록 해준다.


### 필터(filter)

필터는 어떤 그래픽 대상에게 여러가지 효과를 줄 수 있는 기능이다.  
ex) 컬러 이미지를 흑백으로 바꾼다던지, 뿌옇게 처리하던지 등등.  

```javascript
img{
  transition: all 1s;
}
```

모든 이미지에 대해서 1초동안 부드럽게 장면 전환이 된다.  

`codepen.io` 에서 filter를 검색하면 filter를 이용해 만든 것들을 볼 수 있다.  


### 변형(transform) 소개

엘리먼트의 크기, 회전, 비틀기 이러한 것들을 하는 것이 변형(transform)이다.  
transform은 엘리먼트가 block레벨 엘리먼트일 때만 동작한다.  
`codepen.io/vineethtr/full/XKKEgM/`  


### 움직임 주기-transition 기본

트렌지션은 CSS의 여러가지 속성들의 값이 변경이 되었을 때 그 전환을 부드럽게 하는 기능이다.  

```javascript
transition-property: font-size transform;
transition-duration: 0.1s;
transition:all 0.1s;
```  


### 움직임 주기-transition 심화

`https://matthewlein.com/ceaser/`

벤더 프리픽스??
