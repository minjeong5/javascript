# 자바스크립트 프론트엔드 프로젝트 가이드
# GUI 기반 가위, 바위, 보

## 5.1 <button> 태그로 사용자 입력 받기
### 5.1.1 버튼 배치하기
``` html
<div>
    <button>가위</button>
    <button>바위</button>
    <button>보</button>
</div>
```

### 5.1.2 function 함수 키워드
#### 기본형
``` javascript
function 함수명 (인자1, 인자2, ...) {
    실행 코드;
    return 리턴값;
}

함수명();

```

### 5.1.3 함수로 작성된 클릭 이벤트 핸들러 적용하기
``` javascript
function onScissorsClick() {
    var comInput = Math.random();

    if (comInput < 0.33) {
        comInput = SCISSORS;
    } else if (comInput < 0.66) {
        comInput = ROCK;
    } else {
        comInput = PAPER;
    }

    if (comInput === SCISSORS) {
        alert('컴퓨터 : '+ comInput + ' - 컴퓨터와 비겼습니다');        
    } else if (comInput === ROCK) {
        alert('컴퓨터 : ' + comInput + ' - 컴퓨터에게 졌습니다');
    } else {
        alert('컴퓨터 : ' + comInput + ' - 컴퓨터를 이겼습니다');
    }
}
```
``` html
<button onclick="onScissorsClick()">가위</button>
<button onclick="onRockClick()">가위</button>
<button onclick="onPaperClick()">가위</button>
```


---


## 5.2 코드 개선하기
### 5.2.1 클릭 이벤트 핸들러 개선하기

``` javascript
var SCISSORS = '가위';
var ROCK = '바위';
var PAPER = '보';

function onButtonClick(userInput) {
    var comInput = Math.random();

    if (comInput < 0.33) {
        comInput = SCISSORS;
    } else if (comInput < 0.66) {
        comInput = ROCK;
    } else {
        comInput = PAPER;
    }

    if (userInput === SCISSORS) {
        if (comInput === SCISSORS) {
            alert('컴퓨터 패 : '+comInput+ ' - 비겼습니다');
        } else if (comInput === ROCK) {
            alert('컴퓨터 패 : '+comInput+ ' - 졌습니다');
        } else {
            alert('컴퓨터 패 : '+comInput+ ' - 이겼습니다');
        }
    } else if (userInput === ROCK) {
        if (comInput === SCISSORS) {
            alert('컴퓨터 패 : '+comInput+ ' - 이겼습니다');
        } else if (comInput === ROCK) {
            alert('컴퓨터 패 : '+comInput+ ' - 비겼습니다');
        } else {
            alert('컴퓨터 패 : '+comInput+ ' - 졌습니다');
        }
    } else {
        if (comInput === SCISSORS) {
            alert('컴퓨터 패 : '+comInput+ ' - 졌습니다');
        } else if (comInput === ROCK) {
            alert('컴퓨터 패 : '+comInput+ ' - 이겼습니다');
        } else {
            alert('컴퓨터 패 : '+comInput+ ' - 비겼습니다');
        }
    }
}
```
``` html
<button onclick="onButtonClick('가위')">가위</button>
<button onclick="onButtonClick('바위')">바위</button>
<button onclick="onButtonClick('보')">보</button>
```

### 5.2.2 결과 출력 부분 개선하기
``` javascript
var result = '컴퓨터 패 : ' + comInput;

result += ' - 비겼습니다';
result += ' - 이겼습니다';
result += ' - 졌습니다';

alert(result);
```
