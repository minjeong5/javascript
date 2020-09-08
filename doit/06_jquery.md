#jQuery 선택자와 조작법
##06-2 선택자
<body>영역에 문서 객체를 먼저 불러온 후, jQuery에서 선택자를 선택할 수 있도록 해야 한다.
```javascript
$(document).ready(function(){
  $("#txt").css("color", "red");
});

$(function(){
  $("#txt").css("color", "red");
});
```
