# Level 1

### ✏️ K번째수 구하기
주어진 배열을 조건 배열에 따른 값 추출
- 조건
  - array를 조건[0]부터 조건[1]까지로 새로운 배열 만들기
  - 오름차순 정렬후, 조건[2]번째 수 찾기
  - 조건은 2차원 배열로 주워짐 
  - 예시 : [[a,b,c],[a1,b1,c1]] <br/>
  (a\~b번째 혹은 a1\~b1번째(다음 배열이 있을 경우 되풀이)추출해 오름차순으로 정렬하고 c번째 혹은 c1번째 수를 구해 배열로 나타내기)

- 예시
  - input   
    - array [1,2,5,4,7]
    - commands [[2,3,1][1,4,3]]
  - output: [2,4]

> **풀이내용**
```java
function solution(array, commands) {
    var result = [];

    for (let i = 0; i< commands.length; i++){
       let newArr = array.slice(commands[i][0]-1,commands[i][1]).sort((a,b) => a - b)
       result.push(newArr[commands[i][2]-1])
    }   

    return result


}

```

> 다른 사람 풀이
```java
function solution(array, commands) {
    return commands.map(command => {
        const [sPosition, ePosition, position] = command
        const newArray = array
            .filter((value, fIndex) => fIndex >= sPosition - 1 && fIndex <= ePosition - 1)
            .sort((a,b) => a - b)    

        return newArray[position - 1]
    })
}
```
각 조건을 a,b,c로 분해해 쓰려고 했는데, 중첩배열이라 어떻게 접근하지 고민하다 반복문으로 commands를 돌렸다. <br/>
위 풀이과정은 내가 원하던 답안이라 가져왔다. <br/>
map()메서드를 사용에 중첩배열 요소에 접근해 조건 1,2,3을 분해한 뒤,
그리고 filter()로 주어진 조건 a-1(0부터시작하기 때문에 -1해줌) <= array에 인덱스 <= b-1에 맞는 요소만 뽑아 오름차순으로 정렬 하고 조건 c-1번째 숫자가 담긴 배열을 만들어 return.


