# 스킬체크 문제

### ✏️ 첫번째
등차수열 관련 문제 
전달인자 a,b가 주어지며 a가 b번 a만큼 더해져 나오는 값들을 배열로 묶는다.

- 예시 
a=2, b=4 라면 
결과는 **[2,4,6,8]** 가 나오도록 함수를 코딩해야한다.

> **풀이내용**
```
function solution(x, n) {

    var answer = []; 
    // 풀이과정 시작
    
    for(let i = 0; i < n; i++){
        let result = x;
        result = result + x*i
        answer.push(result);
    }// 풀이과정 끝
    
    return answer;
}

```


### ✏️ 두번째
윤년 요일구하기 문제
월과 일을 나타내는 각 전달인자 a,b가 주어지며 2016년 a월 b일의 요일을 구해야한다.

- 조건
  - 2016년의 1월 1일은 금요일이다.
  - 해당 연도는 윤년이다.

- 예시 
a=3, b=14 라면 
2016년 3월 14일은 목요일로 요일을 나타내는 영어 약자 **'THU'** 가 추출되도록 코딩해야한다.

> **풀이내용**
```
function solution(a, b) {

    let day = ['FRI','SAT','SUN','MON','TUE','WED','THU'];
    let dateCount = [31,29,31,30,31,30,31,31,30,31,30,31];

    let month = a-1;
    let date = b-1;

    for(let i = 0; i < month; i++) {
        date += dateCount[i]
    }    
    date = date % 7;

    let answer = day[date];
    return answer;
}
```
