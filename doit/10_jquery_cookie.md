# jQuery 플러그인
## jQuery-cookie 플러그인 활용하기
### jQuery-cookie 플러그인 용도
* 쿠키(cookie)란
    * 사이트를 방문자의 브라우저 정보를 저장하는 공간
    * 사이트당 최대 20개 생성, 최대 4KB까지 저장
* 쿠키(cookie)를 생성하고 쿠키 만료를 설정할 수 있다.
* 활용
    * '오늘 하루 동안 이 창 열지 않기' 기능
    * '최근에 본 상품' 기능

### jQuery-cookie 플러그인 설치하기
1. [cdnjs](https://cdnjs.com)
2. jquery-cookie 검색
3. 1.4.1 버전 copy url
4. 주소 입력란에 붙여넣기
5. `ctrl`+`s` 로 저장

### 메서드 사용법
[gitHub에서 확인](https://github.com/carhartl/jquery-cookie?utm_source=cdnjs&utm_medium=cdnjs_link&utm_campaign=cdnjs_library)

### '3일동안 이 창 열지 않기' 예제
**html**
``` html
<div id="notice_wrap">
    <p>내용 내용</p>
    <p class="closeWrap">
        <input type="checkbox" name="expiresChk" id="expiresChk">
        <label for="expireChk">3일 동안 이 창 열지 않기</label>
        <button class="closeBtn">닫기</button>
    </p>
</div>
```

**js**
``` javascript
// 쿠키("popup")의 값이 "none"이면, id값이 "notice_wrap"인 요소를 숨긴다.
if($.cookie("popup") == "none") {
    $("#notice_wrap").hide();
}

// close 값이 "closeBtn"인 요소를 클릭하면,
// 체크 박스의 체크 유무에 따라 쿠키를 생성하여 3일간 저장한다.
var $expChk = $("#expiresChk");
$(".closeBtn").on("click", closePop);

function closePop() {
    if($expChk.is(":checked")) {
        $.cookie("popup", "none", {expires:3, path:"/"});
    }
    $("#notice_wrap").fadeOut("fast");
}
```