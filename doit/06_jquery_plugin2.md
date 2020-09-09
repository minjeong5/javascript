# jQuery 플러그인
## jQuery UI 플러그인 활용하기

### 플러그인 내려받기
[jQuery UI](http://jqueryui.com)
[jQuery UI 데모 미리보기](https://jqueryui.com/demos)

### UI 플러그인으로 드래그 창 만들기
[예제 미리보기](https://jqueryui.com/draggable/)

``` html
<head>
    <script src="script/jquery-ui-1.12.1/jquery-ui.min.js"></script>
    <style>
        .layer_popup { 
            position: absolute;
            top: 50px;
            left: 50px;
            cursor: move;
            width: 400px;
            height: 400px;
            background: gray;
        }
    </style>
    <script>
        $(function(){
            $('.layer_popup').draggable();
        });
    </script>
</head>

<body>
    <div class="layer_popup">
        드래그가 가능한 레이어 창 만들기 예제
    </div>
</body>
```

### UI 플러그인으로 날짜 설정 달력 만들기
[예제 미리보기](https://jqueryui.com/datepicker/)
``` html
<head>
    <script src="script/jquery-3.5.1.js"></script>
    <script src="script/jquery-ui-1.12.1/jquery-ui.min.js"></script>
    <link rel="stylesheet" href="script/jquery-ui-1.12.1/jquery-ui.min.css"/>
    <script>
        $( function() {
            $( "#datepicker" ).datepicker({ 
                minDate: -20,
                maxDate: "+1M +10D"
            });
        } );
    </script>
</head>
<body>
    <p>
        <label for="datePicker">날짜선택</label>
        <input type="text" name="datePicker" id="datepicker"></p>
</body>
```