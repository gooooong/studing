
---
TVING 클론 코딩을 하다가 swiper에 대해 정보가 부족하구나 싶어서 작성하게 되었다.
내가 해보고 몰랐던 부분 위주로 작성해 본다.

---
---
# swiper ? 
슬라이드를 보다 편하게 사용할수 있게 도와주는 <span style="background-color:#555">**슬라이드 라이브러리**</span> 


&nbsp;


## 기본 설정
> [https://swiperjs.com/](https://swiperjs.com/get-started) 스와이퍼 사이트

> [swiper-css](/file/swiper/swiper-bundle.min.css) --> css 파일
> [swiper-js](/file/swiper/swiper-bundle.min.js) --> js 파일

```html
<!-- CDN 방식 -->
<!-- script 주소 가져오기 -->
<link rel="stylesheet" href="/js/swiper/swiper-bundle.min.css">
<script src="https://cdn.jsdelivr.net/npm/swiper@11/swiper-bundle.min.js"></script>    

<!-- 또는 -->
<!--파일 다운로드 후 해당 script-js file, script-css file 가져오기  -->
<link rel="stylesheet" href="js/swiper/swiper-bundle.min.css">
<script src="js/swiper/swiper-bundle.min.js"></script>
```
&nbsp;

---
> 기본 작성법

```html

 <div class="swiper mySwiper">                     <!-- swiper + 스크립트에서 사용할 class 설정 -->
    <div class="swiper-wrapper">                   <!-- wrapper 한번 감싸주기 -->
        <div class="swiper-slide">Slide 1</div>    <!-- 원하는 갯수만큼 슬라이드 만들기 -->
        <div class="swiper-slide">Slide 2</div>    <!-- 원하는 갯수만큼 슬라이드 만들기 -->
        <div class="swiper-slide">Slide 3</div>    <!-- 원하는 갯수만큼 슬라이드 만들기 -->
    </div>
            <!-- 사용하고자 할때 추가 -->
    <div class="swiper-pagination"></div>          <!-- 페이지 네비게이션 -->
    <div class="swiper-button-next"></div>         <!-- 다음 버튼 -->
    <div class="swiper-button-prev"></div>         <!-- 이전 버튼 -->
  </div>

<script>
var swiper = new Swiper(".mySwiper", {
});
</script>
```
&nbsp;

---
> script 설정법

```javascript

var swiper = new Swiper(".mySwiper", {
    // 화면에 보이고자하는 슬라이드 갯수
    slidesPerView: 3, // "auto" , 1, 2, 3, 4 ···

    // 슬라이드 간의 간격
    spaceBetween: 30,

    // 슬라이드 가운데 정렬
    centeredSlides: true, // 원할시 사용

    // 무한 반복
    loop: true, // 기본값 false 

    // 슬라이드 몇개씩 넘길껀가 설정
    slidesPerGroupSkip: 1,

    // 반응형 
    breakpoints: {
        769: { // 769px 이하 
            slidesPerView: 2, // 화면에 보여질 슬라이드 갯수
            slidesPerGroup: 2, // 한번에 넘어갈 슬라이드 갯수
        },
    },

    // 스크롤바 설정
    scrollbar: {
        el: ".swiper-scrollbar", // custom 하고 싶을 때 "swiper-scrollbar" class 사용
    },

    // 자동 재생 설정
    autoplay: {
        delay: 2500, // 시간설정, 1000 = 1초
        disableOnInteraction: false, // 버튼을 이용하여 컨트롤 한 이후에도 자동 재생 유지되도록
    },

    // 버튼설정
    navigation: {
        nextEl: ".swiper-button-next",  // custom 하고 싶을 때 "swiper-button-next" class 사용
        prevEl: ".swiper-button-prev",  // custom 하고 싶을 때 "swiper-button-prev" class 사용
    },

    // 페이지 네비게이션 설정
    pagination: {
        el: ".swiper-pagination",  // custom 하고 싶을 때 "swiper-pagination" class 사용
                                   // active 되었을 때 "seiper-pagination-active" class 
        clickable: true,  // 클릭 설정 (기본값 false)
    },

    // 마우스 휠 조작 설정
    mousewheel: true, // 원할시 사용

    // 키보드 조작 설정
    keyboard: true, // 원할시 사용
});
</script>
```
&nbsp;

---
>스크립트 옵션 정리 

|옵션|값|설명|비고|
|:---:|:---:|:---:|:---|
|direction&nbsp;&nbsp;|"horizontal"<br>"vertical"|슬라이드 방향 지정|<br>"horizontal" (기본값)<br>"vertical"<br>&nbsp;|
|autoplay|boolean 또는 object|자동 재생 설정|<br>true : 자동 슬라이드 설정<br>object : 슬라이드 옵션 추가<br>&nbsp;|
|loop|boolean|반복설정|<br>true : 무한 반복 슬라이드<br>false : 무한 반복하지 않음 (기본값)<br>&nbsp;|
|delay|number|자동 슬라이드 시,<br>한 슬라이드에 머무르는 시간 (ms)|<br>3000 (기본값)<br>1000 = 1초<br>&nbsp;|
|speed|number|슬라이드가 넘어가는 속도|<br>300 (기본값)<br>1000 = 1초<br>&nbsp;|
|slidesPerView|number 또는 "auto"|한 번에 보여질 슬라이드 갯수|<br>"auto" : 각 슬라이드 넓이에 맞게<br>자동 설정<br>&nbsp;|
|spaceBetween|number|슬라이드 사이의 간격|<br>0 (기본값)<br>&nbsp;|
|centeredSlides|boolean|활성화된 슬라이드가<br>가운데 보이게 지정|<br>true : 가운데로 설정<br>false (기본값)<br>&nbsp;|
|breakpoints|slidesPerView,<br>slidesPerGroup,<br>spaceBetween,<br>slidesPerColumn<br>만 사용가능|화면 넓이에 따라 레이아웃 변경<br>(반응형 슬라이드)|<br>breakpoints: {<br>&nbsp;&nbsp;&nbsp;&nbsp;760: {<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;slidesPerView: 3,<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;spaseBtween: 10,<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;slidesPerGroup: 3,<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;},<br>},<br>&nbsp;|
|mousewheel|boolen 또는 object|마우스휠로 슬라이드 이동|<br><br>&nbsp;|
|pagination|el:".swiper-pagination",<br>clickable: true|페이지 네비게이션 바|<br>custom class<br>"swiper-pagination"<br><br>custom 버튼 class<br>"swiper-pagination-bullet"<br><br>active 시<br>"swiper-pagination-bullet-active"<br>&nbsp;<br>&nbsp;|
|navigation|prevEl<br>".swiper-button-prev",<br>nextEl<br>".swiper-button-next"|페이지 네비게이션 버튼 설정|<br>custom<br>"swiper-button-prev"<br>"swiper-button-next" class <br>&nbsp;|
&nbsp;

&nbsp;


---

>  기본 css 설정 값

```css

/* swiper ----------------------- */
    .swiper {
        margin-left: auto;
        margin-right: auto;
        position: relative;
        overflow: hidden;
        list-style: none;
        padding: 0;
        z-index: 1;
        display: block;
    }
    .swiper-wrapper {
        position: relative;
        width: 100%;
        height: 100%;
        z-index: 1;
        display: flex;
        transition-property: transform;
        transition-timing-function: var(--swiper-wrapper-transition-timing-function, initial);
        box-sizing: content-box;
    }
    .swiper-slide {
        flex-shrink: 0;
        width: 100%;
        height: 100%;
        position: relative;
        transition-property: transform;
        display: block;
    }

/* swiper-button ---------------- */
    .swiper-button-next, 
  	.swiper-button-prev {
        position: absolute;
        top: var(--swiper-navigation-top-offset, 50%);
        width: calc(var(--swiper-navigation-size) / 44* 27);
        height: var(--swiper-navigation-size);
        margin-top: calc(0px -(var(--swiper-navigation-size) / 2));
        z-index: 10;
        cursor: pointer;
        display: flex;
        align-items: center;
        justify-content: center;
        color: var(--swiper-navigation-color, var(--swiper-theme-color));
    }

/* swiper-pagination ------------ */
    .swiper-pagination {
        position: absolute;
        text-align: center;
        transition: .3s opacity;
        transform: translate3d(0, 0, 0);
        z-index: 10;
    }
    .swiper-horizontal >.swiper-pagination-bullets, 
    .swiper-pagination-bullets.swiper-pagination-horizontal, 
    .swiper-pagination-custom, .swiper-pagination-fraction {
        bottom: var(--swiper-pagination-bottom, 8px);
        top: var(--swiper-pagination-top, auto);
        left: 0;
        width: 100%;
    }
    .swiper-pagination-bullet {
        cursor: pointer;
        margin: 0 var(--swiper-pagination-bullet-horizontal-gap, 4px);
        width: var(--swiper-pagination-bullet-width, var(--swiper-pagination-bullet-size, 8px));
        height: var(--swiper-pagination-bullet-height, var(--swiper-pagination-bullet-size, 8px));
        display: inline-block;
        border-radius: var(--swiper-pagination-bullet-border-radius, 50%);
        background: var(--swiper-pagination-bullet-inactive-color, #000);
        opacity: var(--swiper-pagination-bullet-inactive-opacity, .2);
    }
    .swiper-pagination-bullet-active {
        opacity: var(--swiper-pagination-bullet-opacity, 1);
        background: var(--swiper-pagination-color, var(--swiper-theme-color));
    }
  

```
&nbsp;

&nbsp;

---
## ex 01

> 아래 사진과 같은 swiper에서는 6번째 슬라이드가 잘린다 <br>
> 애매하게 걸쳐진 슬라이드를 설정 해보자

![](https://velog.velcdn.com/images/gooooo__o/post/9fa783f5-db6b-432e-9bbb-dda293994698/image.png)
&nbsp;

이해를 돕기위해 모형으로 만들어 보았다

![](https://velog.velcdn.com/images/goooo__o/post/3bf9fbf2-e983-42a5-bb12-017708d78eb4/image.png)

&nbsp;
> html

```html

  <div class="wrap">
        <div class="swiper myswiper">
            <div class="swiper-wrapper">
                <div class="swiper-slide">1</div>
                <div class="swiper-slide">2</div>
                <div class="swiper-slide">3</div>
                <div class="swiper-slide">4</div>
                <div class="swiper-slide">5</div>
                <div class="swiper-slide">6</div>
                <div class="swiper-slide">7</div>
                <div class="swiper-slide">8</div>
                <div class="swiper-slide">9</div>
                <div class="swiper-slide">10</div>
                <div class="swiper-slide">11</div>
                <div class="swiper-slide">12</div>
                <div class="swiper-slide">13</div>
            </div>       
            <div class="swiper-button-next"></div>        
            <div class="swiper-button-prev"></div> 
        </div>
    </div>
````
&nbsp;

> css

```css

  /* --- 페이지 설정 ------------------- */
    .wrap {
        width: 1700px;
        background: #ccc;
        padding: 100px;
        margin: 500px auto;
    }

  /* --- swiper 설정 ------------------ */
    .myswiper {
        overflow: visible; /* 기본값 "hidden" >> "visible" 변경 (보이게 설정) */ 
    }    
    .myswiper .swiper-slide {
        width: 246px;
        height: 354px;
        background-color: white;
        border-radius: 5px;  
    }

  /* --- swiper 버튼 설정 ------------- */
    .swiper-button-next,
    .swiper-button-prev {
        position: absolute; /* 슬라이드 밖에 위치하길 원해서 absolute적용 */
        top: 20px;
        width: 100px;
        height: 100%;
        color: transparent; /* 기본 버튼 화살표 색상 없애줌 */
    }
    .swiper-button-next {
        right: -100px;
        background: url(/images/arrow_next.png); /* 새로운 버튼 이미지 적용 */
    }
    .swiper-button-prev {
        left: -100px;
        background: url(/images/arrow_prev.png); /* 새로운 버튼 이미지 적용 */
    }
    
```
&nbsp;
>javasctipt

```javascript

	const SWIPER = new Swiper('.myswiper', {
    	spaceBetween: 33,       // 각 슬라이드 사이의 간격
        slidesPerView: 'auto',  // 화면에 보여질 슬라이드 갯수
        slidesPerGroup: 5,      // 한번에 넘어갈 슬라이드 갯수
           
        navigation: {           // 페이지 넘기는 버튼
            nextEl: ".swiper-button-next",
	        prevEl: ".swiper-button-prev", 
        },  
    });

```


&nbsp;


### 결과물

<img src="/images/swiper_test_slideperview_01.png" alt="">

>
> * slidesPerView 다른 숫자로 바꿀시 원래 크기가 틀어진다
> -- 화면에 보여지는 갯수를 억지로 맞춰버리는 듯 하다
> <br>
> * 슬라이드 그룹 6개로 하면 6 번째 슬라이드 안보이고 넘어간다
> -- 당연한 소린가?

&nbsp;

&nbsp;

### slidesPerView 설정

> **SlidesPerView: auto**
>  - 내가 설정한 width, spassBtween 모두 그대로 설정된다
> ![](https://velog.velcdn.com/images/goooo__o/post/2388c7e0-aff2-47c9-bebf-2d6e93cfebec/image.png)


> **SlidesPerView: 1**
> - 화면에 1개의 slide만을 보여줌
![](https://velog.velcdn.com/images/goooo__o/post/db0463c6-8bc1-4968-bc07-b69c43bc65cd/image.png)

> **SlidesPerView: 2**
> - 화면에 2개의 slide만을 보여줌
![](https://velog.velcdn.com/images/goooo__o/post/0c98823c-7676-4521-ab34-3de21913a1b8/image.png)

> **SlidesPerView: 3**
> - 화면에 3개의 slide만을 보여줌
![](https://velog.velcdn.com/images/goooo__o/post/88e89823-8d14-41d4-bee0-7fb21008cbf6/image.png)

> **SlidesPerView: 4**
> - 화면에 4개의 slide만을 보여줌
![](https://velog.velcdn.com/images/goooo__o/post/7a342075-b93f-4c56-9d8c-40f44e6dfd88/image.png)

> **SlidesPerView: 5**
> - 화면에 5개의 slide만을 보여줌
![](https://velog.velcdn.com/images/goooo__o/post/aa5d5bfb-03bb-4460-82f9-a277d87f17d7/image.png)

> **SlidesPerView: 6**
> - 화면에 6개의 slide만을 보여줌
![](https://velog.velcdn.com/images/goooo__o/post/6f2c5fac-1f22-40a1-8734-12a228538e5a/image.png)

> **SlidesPerView: 7**
> - 화면에 7개의 slide만을 보여줌
![](https://velog.velcdn.com/images/goooo__o/post/96490722-ae12-4083-af96-e7454f496d6a/image.png)



&nbsp;

&nbsp;

&nbsp;



### 같은 상황에서 Pagination을 설정해보자

> html

```html
    <!-- html .swiper-wrpper 아래에 추가 -->
    
    <div class="swiper-pagination flex-ac"></div>
```
```html
    <div class="wrap">
        <div class="swiper myswiper">
            <div class="swiper-wrapper">
                <div class="swiper-slide">1</div>
                <div class="swiper-slide">2</div>
                <div class="swiper-slide">3</div>
                <div class="swiper-slide">4</div>
                <div class="swiper-slide">5</div>
                <div class="swiper-slide">6</div>
                <div class="swiper-slide">7</div>
                <div class="swiper-slide">8</div>
                <div class="swiper-slide">9</div>
                <div class="swiper-slide">10</div>
                <div class="swiper-slide">11</div>
                <div class="swiper-slide">12</div>
                <div class="swiper-slide">13</div>
            </div>       
            <div class="swiper-button-next"></div>        
            <div class="swiper-button-prev"></div> 
               
            <!-------------------------------------->
            <div class="swiper-pagination"></div>    <!-- 추가 -->
            <!-------------------------------------->
         
          중요!!  "swiper-pagination-bullet"은 알아서 생성
          			때문에 추가하지 않아두 된다
          
     

        </div>
    </div>
```

&nbsp;

>script

```javascript
    // const swiper 안에  pagination을 추가한다
    
    pagination: {
        el: ".swiper-pagination",
        clickable: true,
    },    
```

```javascript
// javascript

 <script>
        const SWIPER = new Swiper('.myswiper', {
            spaceBetween: 33,     
            slidesPerView: 'auto',
            slidesPerGroup: 5,     
           
            navigation: {           
                nextEl: ".swiper-button-next",
                prevEl: ".swiper-button-prev", 
            },  
          
          /* ----------------------------- */
           pagination: {					     /* 추가 */
                el: ".swiper-pagination",
                clickable: true,
            },
          /* ----------------------------- */
          
       });
```
> css :custom

```html
  <style>
        .swiper .swiper-pagination {
            bottom: -80px;
        }
        .swiper .swiper-pagination .swiper-pagination-bullet {
            width: 20px;
            height: 20px;
            margin: 10px;
            background-color: white;
        }
        .swiper .swiper-pagination .swiper-pagination-bullet-active {
            opacity: 1;
        }
  </style>
```
&nbsp;

#### 결과물
> * 가운데 아래 부분에 pagination 아주 잘 들어감
> * bullet 갯수는 알아서 생성됨
![](https://velog.velcdn.com/images/goooo__o/post/54a85f3a-1fe8-4d15-8e1a-707ea4070b60/image.png)

&nbsp;

&nbsp;

&nbsp;


#### 만약 "pagination-bullet"을 추가 했을 경우

```html
      <div class="swiper-pagination">
          <div class="swiper-pagination-bullet"></div>
      </div>
```















&nbsp;

---
### 반응형 Breakpoints

```javascript
var swiper = new Swiper(".mySwiper", {
    slidesPerView: 3, // 기본 초기값 설정, 제일 작은 화면
    spaseBtween: 5, 
    
    // 760px 이상
    breakpoints: {
        760: { // 760px min-width
            slidesPerView: 3,
            spaseBtween: 10, 
            slidesPerGroup: 3, 
        },
    },

    // 1024px 이상
    breakpoints: {
        1024: { // 1024px min-width 
            slidesPerView: 5, 
            spaseBtween: 15, 
            slidesPerGroup: 5,
        },
    },
});
```
&nbsp;

---
### 예제
![](https://velog.velcdn.com/images/goooo__o/post/e7e11c59-5ebe-4061-b08a-0547f36d2308/image.svg)


> 위와 같은 슬라이드를 만들어 보자
> 	- 화면 : 1100px
> 	- 화면에 슬라이드 1페이지씩 보이기
> 	- 슬라이드 1페이지씩 넘기기
> 	- 각 슬라이드 사이 간격 : 20px
> 	- 슬라이드 높이 : 600px
> 	- padding : 100px 
> 	- ovserflow : 보이기 
> 	- 이전, 다음 버튼 화면 끝으로 붙이기
> 	- 이전, 다음 버튼 사이즈 높이 : 100%, 넓이 : 79px
