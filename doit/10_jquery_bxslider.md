# jQuery 플러그인
## bxSlider 플러그인 활용하기
### bxSlider 플러그인 설치하기
1. [bxSlider](https://bxslider.com)
2. install 버튼
3. Download jquery.bxslider.zip 다운받기

### bxSlider 플러그인 기본형
``` javascript
참조변수 = $("요소 선택").bxSlider({
    옵션 설정,
});
```

### [bxSlider 플러그인 사용방법](https://bxslider.com/examples/image-slideshow-captions/)
** html **
``` html
<div class="bxslider">
  <div><img src="/assets/images/coffee1.jpg" title="Funky roots"></div>
  <div><img src="/assets/images/coffee2.jpg" title="The long and winding road"></div>
  <div><img src="/assets/images/coffee3.jpg" title="Happy trees"></div>
</div>
```


** js **
``` javascript
$(function(){
  $('.bxslider').bxSlider({
    mode: 'fade',
    captions: true,
    slideWidth: 600
  });
});
```