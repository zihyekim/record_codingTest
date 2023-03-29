# Level 0

### ✏️ OX 퀴즈

주어진 객체배열을 구조분해 할당 수 마지막 수와 앞 선 두수의 합이 맞을 경우  "O"를 반혼 아니면 "x"를 반환해
정답 배열 객체를 만든다

> **다른 사람 풀이**
 ```java
 function solution(quiz) {
   return quiz.map((t) => {
        t = t.split("=")
        const [sum , result] = t
        
        return eval(sum) == Number(result) ? "O" : "X"
    })
 }
 
 ```
 
> 실패한 풀이
```java
function solution(quiz) {
    var answer = [];    
    
    // let divide = quiz.map()
    
    for(let i = 0 ; i < quiz.length; i++) {
        let str = quiz[i].split("=");
        let [sum,result] = str
        console.log(str)
        
//         let answer1 = "";
        
//         if(eval(sum) == Number(result)){
//             return answer1 = "O"
//             // console.log('O')
//         } else {
//             return answer1 = "X" 
//         // console.log('X')
//         }
        
        // answer.push(answer1);
    }
    
    return answer;
}
```

> 재풀이
``` java

function solution(quiz) {
    var answer = [];    
    
    // let divide = quiz.map()
    
    for(let i = 0 ; i < quiz.length; i++) {
        let [sum, result] = quiz[i].split("=");
        
        if(eval(sum)==Number(result)){
            answer.push("O")
        }else answer.push("X")
    }
    
    return answer;
}
```

