##1. Javascript 
출력은 되지 않지만 모듈로써 가져다 쓸 수는 있음
###1-1. if 논리 연산자 (==)
    ==, === : 참
    >== : 이상
    <== : 이하
    !== : false
    
```javascript
console.log(null==undefined); --true
console.log(null===undefined); --false
```
  ==은 형 변환을 시키면서 다른 문자열을 같다고 표기
  ===은 값이 다른 것으로 인식하여 다른 값으로 표기
  
###1-2. if 논리 연산자 (&&)
     두 조건에 모두 적합할 시에 (&&)을 씀 (and)
     
```javascript
var num =4;
if (num>3 && num<6){
  console.log('4 is greater than 3')
  }
```
    num 이 if의 두 조건 모두 충족할 시에 씀

###1-3. if 논리 연산자 (||)
      두 조건 중 하나만 적합할 시에 씀 (or)
      
```javascript
var count =9;
if (count>8 || count<4){
  console.log('number');
}
```

###1-4. 삼항 연산자
     00 (T/F) ?  : T : F; 의 구조
```javascript
!true? console.log('true'): console.log('false');
```
    -여러 항을 쓸 수도 있지만 마지막에는 3항으로 마무리 해줘야 함
```javascript
var condition = 'ramos';

condition === 'hesus'?
console.log('is hesus'):
condition === 'zeus'?
console.log('is zeus'):
condition === 'zeus'?
console.log('is zeus'):
condition === 'ramos'?
console.log('is ramos'):
console.log('.......');
```

###1-5. Function (함수)
    -Return: 함수에 연산된 결과 값을 반환 할 때 씀
```javascript
  if(money !== 0){
    money=money || 100;
  }
  //if 안에만 들어가는 || 가 밖으로 나오게 되면 불리언 값으로 (?)
  if (typeof money !== 'number'){
    console.error('ERROR');
  }

return '너가 원하는 금액은' + money + '구나';
}

var result = getMoney(0);
console.log(result);
```
결과는 ‘너가 원하는 금액은 (‘설정값') 이구나' 로 출력 됨

##2. SASS
###2-1. Output Style

      compact: 한 줄로 정리 (촘촘하게)
      compress: 압축 (공백 없이)
      expanded: 확장 
      nested: 중첩 

**Tab과  Space 키를 혼용하면 안됨
**Sass는 indent가 중요 (인덴트 된 요소를 자식 요소로 인식)

###2-2. Sass 문법

#####1. &: 상위 요소
```css
  a
    color: #333
    &:hover,
    &:focus
      color: pink
```
```css

 a:hover,  a:focus {
  color: pink;
}
```
#####2. @extend: 가중 상속 가능
```css
.box
  display: block
  width: 100px
  height: 100px

.box-black
  @extend .box
  background: #000

.box-yellow
  @extend .box
  background: #ff0
```
-CSS로 변환 시
```css
.box, .box-black, .box-yellow, .box-red {
  display: block;
  width: 100px;
  height: 100px;
}

.box-black {
  background: #000;
}

.box-yellow {
  background: #ff0;
}
```
#####3.%: Module not shown ( 대체 선택자 )
 -출력은 되지 않지만 모듈로써 가져다 쓸 수는 있음
```css

%reset-list
  margin:
    top: 0
    bottom: 0
  padding-left: 0
  list-style: none
nav#gnb
  ul
    @extend %reset-list
 ```

