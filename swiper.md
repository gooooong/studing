---
<style type="text/css">
    @font-face {
        font-family: 'Pretendard-Regular';
        src: url('https://cdn.jsdelivr.net/gh/Project-Noonnu/noonfonts_2107@1.1/Pretendard-Regular.woff') format('woff');
        font-weight: 400;
        font-style: normal;
    }
    body {
        font-family: 'Pretendard-Regular';
    }
</style>
---



swiper 정리
=============

&nbsp;


#### 기본 설정
> [swiper](https://swiperjs.com/get-started) 시작하기 사이트

> [swiper-css](/file/swiper/swiper-bundle.min.css) --> css 파일 다운로드 <br>
> [swiper-js](/file/swiper/swiper-bundle.min.js) --> js 파일 다운로드

```html
 <!-- script 주소 가져오기 -->
<script src="https://cdn.jsdelivr.net/npm/swiper@11/swiper-bundle.min.js"></script>    

<!-- 또는 -->
<!--파일 다운로드 후 해당 script-js file, script-css file 가져오기  -->
<link rel="stylesheet" href="js/swiper/swiper-bundle.min.css">
<script src="js/swiper/swiper-bundle.min.js"></script>
```
&nbsp;

---
#### 기본 문법
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
#### 스크립트 설정
```html
<script>
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
### slide per view 설정

> 아래 사진과 같은 swiper에서는 6번째 슬라이드가 잘린다  <br>
> 슬라이드 설정 시
> slides per View : "auto" <br>
> slides per Group : 5
>
> * 화면에 보이는 슬라이드 갯수를 조절해버리면 원래 크기가 틀어진다
> * 슬라이드 그룹 6개로 하면 6 번째 슬라이드 안보이고 넘어간다

<img src="/images/tving-captuer.png" width="100%" title="tving 화면캡쳐"></img><br/>

&nbsp;

---
### 반응형 Breakpoints

```javascript
var swiper = new Swiper(".mySwiper", {


 breakpoints: {
        769: { // 769px 이하 
            slidesPerView: "auto", 
            slidesPerGroup: 5, 
        },
    },
});
```
