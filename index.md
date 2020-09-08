```markdown
/* -------------------------------------------------------------
객체 생성자 함수를 만들어서 두 학생(kimgun, ohgun)의 객체를 생성한다.
속성으로 이름, 국어점수, 영어점수를 등록한다.

1. 객체를 생성하면 prototype으로 함수를 등록한다.
2. getTestInfo() 함수를 실행하면 이름, 국어, 영어 정보를 출력한다.
3. getAvg() 함수를 실행하면 평균 점수를 출력한다.
------------------------------------------------------------- */
function TestScore(name, kor, eng) {
    this.userName = name;
    this.korNum = kor;
    this.engNum = eng;
    
    this.getTestInfo = function() {
        document.write("이름:"+this.userName,"<br/>");
        document.write("국어점수:"+this.korNum,"<br/>");
        document.write("영어범수:"+this.engNum,"<br/>");
    }
    this.getAvg = function() {
        return (this.korNum + this.engNum)/2;
    }
}
var kimgun = new TestScore("김군", 80, 90);
var ohgun = new TestScore("오군", 100, 80);

kimgun.getTestInfo();
document.write("평균점수:"+kimgun.getAvg(), "<br/>");
ohgun.getTestInfo();
document.write("평균점수:"+ohgun.getAvg(),"<br/>");
```
