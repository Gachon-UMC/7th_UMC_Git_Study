## 핵심 키워드

---

<aside>
💡 주요 내용들에 대해 조사해보고, 자신만의 생각을 통해 정리해보세요!
레퍼런스를 참고하여 정의, 속성, 장단점 등을 적어주셔도 됩니다.
조사는 공식 홈페이지 **Best**, 블로그(최신 날짜) **Not Bad**

</aside>

-   원시 타입 🍠
    ### 원시 타입 (Primitive Type)
    자바스크립트에서 원시타입은, 쉽게 정의하면 객체가 아닌 다른 모든 타입을 의미합니다. 객체가 아니기에, 이러한 원시 타입은 메서드를 갖고 있지 않습니다.
    -   boolean
        ### boolean
        거짓과 참을 가질 수 있는 데이터 타입입니다. 주로 조건문에서 많이 사용됩니다.
        true / false와 같은 boolean 형의 값 외에도 조건문에서 마치 true와 false처럼 취급되는 truthy, falsy 값이 존재한다.

jsx
if (1) {
// 1을 true로 사용할 수 있다.
}

        if (0) {
        	// 0을 false로 사용할 수 있다.
        }

        if (NaN) {
        	// NaN을 false로 사용할 수 있다.
        }

        // 그 외에도 null / undefined / 공백이 없는 빈 문자열도 falsy한 값이다.


    - null

        ### null

        아직 값이 없거나, 비어 있는 값을 표현할 때 사용합니다.

        의도적으로 변수에 값이 없음을 표현하고 싶을 때 null을 사용합니다.



jsx
let matthew = null;
console.log(matthew); // null

        null이 가지고 있는 특별한 점은 다른 원시 타입 값과 다르게 타입을 체크했을 때, ‘object’라는 결과가 반환 된다는 점 입니다.



jsx
typeof null === 'object'; // true

        왜 이렇게 개발했을지 의문을 충분히 가질 수 있습니다. 이는, 초창기 자바스크립트 개발 시 발생한 문제이고 **typeof null을 진짜로 null로 표현하고자 하는 많은 시도**가 있지만, 호환성 문제가 다른 코드에 영향을 주어 받아들여지지 않았다고 합니다.

        [Why is typeof null "object"?](https://stackoverflow.com/questions/18808226/why-is-typeof-null-object)

    - undefined

        ### undefined

        undefined는 선언한 후 값을 할당하지 않은 변수. 즉, 아직 변수 또는 프로퍼티가 할당되지 않았음을 의미합니다.



jsx
let matthew;
matthew // undefined;

        const matthewObject = {};
        matthewObject.key; // undefined


    - number 🍠

        자바스크립트는 bigint가 등장하기 전에는, 모든 숫자를 number라는 타입에 넣기 시작했다.

        ECMAScript 표준에 따르면

        $$
        -(2^{53}-1)과 2^{53}-1
        $$

        사이의 값을 저장할 수 있다.



jsx
42; // 정수 리터럴
3.14159; // 부동 소수점 리터럴
0b1010; // 2진수 리터럴 (binary literal)
0o755; // 8진수 리터럴 (octal literal)
0x1A3; // 16진수 리터럴 (hexadecimal literal)

        // 천 단위를 읽기 쉽게 해주는 표현(가독성)
        1_000_000; // 숫자 구분 기호 (Numeric Separators)


        ### 숫자 타입

        숫자 타입의 값은 **배정밀도 64비트 부동(떠다닐 부 浮 動) 소수점 형식**을 따릅니다. 즉 , 소수점 위치가 고정되어 있지 않아 실수부와 소수부로 나누는 것이 아닌 **지수와 가수를 이용하여 실수를 표현하는 방식**입니다. 또한 , **배정밀도**란 단정밀도(32bit)의 배수인 64bit의 정밀도를 가진다는 뜻입니다. 정밀도란 컴퓨터에서 유효 자리 숫자를 의미하는데 , 배정밀도는 단정밀도보다 더 많은 수를 표현할 수 있다는 것을 의미합니다.

        참고 : http://www.ktword.co.kr/test/view/view.php?no=4886

        Javascript로 소수점과 관련된 알고리즘 문제를 풀이하다보면 특정 부분에서 오류가 발생할 수 있습니다. (ex .반올림) 이는 부동 소수점이 이진법을 이용하기 때문에 특정 소수를 정확하게 표현하지 못하기 때문입니다.

        <aside>
        💡

        **Q : 이진법은 왜 특정 소수를 정확하게 표현하지 못하나요 ?**

        Chat GPT : 이진법에서는 일부 소수를 정확하게 표현하지 못하는 이유는, 10진법에서 유한한 소수로 표현되는 숫자가 2진법으로 변환되면 무한 소수로 나타나는 경우가 있기 때문입니다.

        예를 들어, 10진법에서 0.1은 유한 소수이지만, 2진법에서는 0.000110011001100...와 같이 무한 소수로 나타납니다. 이는 2진법에서 0.1을 정확하게 표현할 수 없다는 뜻입니다. 10진법에서는 분모가 2나 5의 거듭제곱으로 나뉘는 경우에만 유한 소수로 표현되지만, 2진법에서는 분모가 2의 거듭제곱으로 나뉘는 경우에만 유한 소수로 표현될 수 있습니다.

        따라서, 10진법에서 유한한 소수라도 2진법에서는 정확하게 표현되지 못하고 근사값으로 저장되게 됩니다. 컴퓨터에서 부동소수점 연산을 할 때 이러한 문제로 인해 정확한 값 대신 근사치가 사용됩니다.

        </aside>

        따라서 반올림 오차([**Number.prototype.toFixed()**](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/Number/toFixed))나 비교 오차가 발생할 수 있는데 , 이를 해결하기 위해서는

        1. 정수로 만들기 (자릿수까지 10^n을 곱하면 만들 수 있음)
        2. 정밀한 값을 요구하지 않는다면 , Math.prototype.round()과 같은 메서드를 사용하시면 됩니다.

        - JS에서 사칙연산을 하는 방법을 작성해주세요. 🍠
            - 더하기
            - 빼기
            - 곱하기
            - 나누기
            - 나머지 구하기
            - 거듭 제곱

            ### 암묵적 타입 변환 (Implicit Type Coercion)



jsx
console.log("1" + 1); //11 (string type)

            서로 다른 타입을 연산하는 코드가 오류를 발생시키는 것이 아니라 11의 결과를 내는 이유는 무엇일까요 ?

            바로 javascript의 **암묵적 타입 변환**때문입니다.

            ### 타입 변환

            개발자가 의도적으로 값의 타입을 변환하는 것을 명시적 타입 변환 또는 타입 캐스팅이라고 합니다.

            그렇지만 , Javascript처럼 개발자의 의도와는 상관없이 표현식을 평가하는 도중에 JS 엔진에 의해 암묵적으로 타입이 자동으로 바뀌는 경우가 있는데 이를 암묵적 타입 변환(타입 강제 변환)이라고 합니다.

            JS 엔진은 더하기 (+) 연산자를 평가할 때 , 피연산자 중 하나 이상이 문자열이면 **문자열 연결 연산자**로 동작합니다. 즉 , 숫자 타입의 값을 자동으로 문자열로 바꿔줍니다.



jsx
console.log("5" - 3); // 2
console.log("4" \* 2); // 8
console.log("10" / 2); // 5
console.log("10" % 3); // 1

            다른 연산자들은 더하기 연산자와 다르게 문자 타입을 숫자로 변환해주죠.

            따라서 , 사칙 연산을 진행할 때는 피연산자들의 타입이 숫자임을 확인하거나 적절한 메서드를 이용해 타입 변환을 진행한 후 , 연산을 진행해야 합니다.

        - JS에서 비교 연산을 하는 여러 가지 방법을 조사하여 정리해주세요. 🍠



jsx
console.log("1" == 1);
console.log("1" === 1);

            == , ! =(느슨한 동등 연산자)는 마찬가지로 타입이 다른 값들끼리 비교할 때 JS가 자동으로 타입을 변환한 후 비교합니다.



jsx
console.log(5 == "5"); // true (문자열 "5"가 숫자 5로 변환되어 비교됨)
console.log(0 == false); // true (false가 숫자 0으로 변환됨)
console.log(null == undefined); // true (null과 undefined는 동등하게 취급)
console.log([] == false); // true ([]가 숫자 0으로 변환되고 false도 숫자 0으로 변환됨)

            반면 === , ! == (엄격한 동등 연산자)는 타입 변환 없이 값을 비교합니다.

            ==를 사용하게 되면 결과 값을 예측하기가 어렵고 , 의도하지 않은 값을 낼 수 있게 되니 최대한 지양하고 === 를 사용해야 합니다.

        - JS에서 증가/감소 연산을 하는 여러가지 방법을 조사하여 정리해주세요. 🍠
        - 연산자 우선순위에 대해 작성해주세요. 🍠

            ### 1. **최우선 연산자 (우선순위 1-2)**

            - **그룹화 연산자 ( )**: 괄호로 묶인 부분이 가장 먼저 실행됩니다.
            - **멤버 접근 연산자 .**, **배열 요소 접근 [ ]**: 객체나 배열의 값을 접근할 때 사용합니다.



js
코드 복사
console.log(obj.property); // obj의 property 값 출력
console.log(arr[2]); // arr 배열의 2번째 요소 출력

            ### 2. **단항 연산자 및 증감 연산자 (우선순위 3-5)**

            - **단항 연산자 !**, **typeof**, **+**, **`**: 해당 연산자들이 피연산자에 먼저 적용됩니다.



js
코드 복사
console.log(!true); // false
console.log(typeof 5); // 'number'

            - **증감 연산자 ++**, **-**: 해당 변수를 1씩 증가 또는 감소시킵니다. (전위/후위에 따라 차이가 있음)



js
코드 복사
let a = 5;
console.log(++a); // 6 (먼저 증가 후 출력)
console.log(a++); // 6 (출력 후 증가)

            ### 3. **산술 연산자 (우선순위 6-7)**

            - *곱셈, 나눗셈, 나머지 `, /, %*가 덧셈, 뺄셈 +, 보다 우선순위가 높습니다.



js
코드 복사
console.log(2 + 3 * 4); // 14 (3*4가 먼저 계산)
console.log((2 + 3) \* 4); // 20 (괄호 내의 계산이 먼저)

            ### 4. **비교 연산자 (우선순위 8-10)**

            - **<, >, <=, >=**, **===, !==**: 비교 연산이 수행됩니다. 같음/다름을 비교하는 연산자가 더 낮은 우선순위를 가집니다.



js
코드 복사
console.log(5 > 3); // true
console.log(5 === '5'); // false (===은 타입까지 비교)

            ### 5. **논리 연산자 (우선순위 11-12)**

            - **AND &&**, **OR ||**: AND가 OR보다 높은 우선순위를 가집니다.



js
코드 복사
console.log(true || false && false); // true (&&가 먼저 계산됨)

            ### 6. **조건부(삼항) 연산자 (우선순위 13)**

            - **? :**: 조건이 참이면 첫 번째 값, 거짓이면 두 번째 값을 반환합니다.



js
코드 복사
let age = 18;
let result = (age >= 18) ? "성인" : "미성년자";
console.log(result); // "성인"

            ### 7. **대입 연산자 (우선순위 14)**

            - **=**, **+=**, **=**, **=**: 대입 연산자는 대부분의 연산자보다 우선순위가 낮으며, 우에서 좌로 실행됩니다.



js
코드 복사
let x = 5;
x += 2; // x = x + 2 와 동일
console.log(x); // 7

            ### 8. **콤마 연산자 (우선순위 15)**

            - **,**: 콤마 연산자는 가장 낮은 우선순위를 가지며, 좌측의 표현식을 평가한 후 우측의 표현식을 평가합니다.



js
코드 복사
let x = (1 + 2, 3 + 4); // 콤마 연산자로 인해 3+4의 결과인 7이 최종 값
console.log(x); // 7

            ### 연산자의 결합 방향

            - **좌에서 우로 결합 (Left-to-Right)**: 대부분의 연산자는 왼쪽에서 오른쪽으로 결합합니다. 예를 들어, 산술 연산자나 비교 연산자 등이 해당됩니다.
            - **우에서 좌로 결합 (Right-to-Left)**: 대입 연산자와 삼항 연산자는 오른쪽에서 왼쪽으로 결합합니다.

            이런 우선순위를 이해하고 사용하면 복잡한 표현식도 정확하게 해석하고 작성할 수 있습니다.


    - string 🍠

        ### string

        <aside>
        💡 https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/String/String

        </aside>

    - symbol

        ### Symbol

        Symbol 타입은 ES6에서 새롭게 추가된 7번째 타입입니다. 중복되지 않는, 고유한 값들을 나타내기 위해서 만들어졌습니다. 심벌을 생성하기 위해서는 Symbol()을 사용해야 합니다.

        왜 Symbol을 사용할까요?

        아래의 yongmin이라는 사람도 Matthew라는 영어 이름을 갖고 있고, sua 라는 사람 또한 Matthew 라는 영어 이름을 갖고 있다고 합시다.



jsx
const yongmin = 'Matthew';
const sua = 'Matthew';

        둘을 일치 연산자(===)로 비교하면 어떻게 될까요?



jsx
yongmin === sua // true

        당연히 true가 나옵니다.

        하지만, 우리가 원하는 시나리오는, 용민이라는 사람과, 수아라는 사람은 엄연히 다른 사람이기에, false가 나오기를 원한다고 가정해봅시다. 이런 경우 **Symbol을 활용**할 수 있습니다.



jsx
const yongmin = Symbol('Matthew');
const sua = Symbol('Matthew');

        다시 일치 연산자(===)로 비교해봅시다.



jsx
yongmin === sua // false

        이처럼 중복되지 않는 어떠한 고유한 값을 나타내고 싶으면 **Symbol 타입**을 활용하는 것이 매우 유용합니다.

    - bigint 🍠

        ### bigint

        <aside>
        💡 https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/BigInt
        BigInt는 정수 뒤에 n을 붙이거나 함수 BigInt()를 호출해 생성해낼 수 있습니다.

        주의해야 할 점은 BigInt는 Math 객체의 내장 메서드와 함께 사용할 수 없고 , 연산에서 Number와 혼합해서 사용할 수 엇습니다. 따라서 먼저 같은 자료형으로 변환해야 합니다. (근데 , BigInt를 굳이 Number로 바꾼다면 처음부터 BigInt를 사용할 필요가 있었을까요 ?)

        </aside>


-   객체 타입 🍠
    ### 객체 타입 (Object Type)
    위의 7개 원시 타입 제외 자바스크립트를 이루고 있는 대부분의 타입이 바로 객체 타입입니다. 여기에는 배열, 함수, 정규식, 클래스 등이 포함됩니다.
    여기서 한 가지 주목할 것이 **객체 타입은 참조를 전달**하기에, **참조 타입**으로도 불린다는 것입니다.

jsx
const hello1 = () => {};
const hello2 = () => {};

    위의 내용을 보면 실제로, 함수의 내용이 같아 보입니다. 하지만, 서로의 참조가 다르기에 false가 반환됨을 알 수 있습니다.

jsx
hello1 === hello2 // false

    - 배열

        ### 배열 (Array)

        자바스크립트에서 배열을 만드는 방법

        1. **배열 리터럴 []**



jsx
// 배열 리터럴 [] 를 사용하여 만드는 방법
let matthew = [];

        // 각각 인덱스를 [] 안에 넣어, 배열 안에 값을 할당할 수 있다.
        matthew[0] = 'kim';
        matthew[1] = 'yong';
        matthew[2] = 'min';

        // i = 0 부터, matthew의 길이 총 3(['kim', 'yong', 'min'], i++ (하나씩 증가)
        for (let i = 0; i < matthew.length; i++) {
        	console.log(matthew[i]);
        }


        ![스크린샷 2024-08-19 오후 2.37.59.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/f1912130-0409-4e90-a90f-6091ae253e73/60b44166-84c0-44c0-9b7c-59b0ccf931ce/%E1%84%89%E1%85%B3%E1%84%8F%E1%85%B3%E1%84%85%E1%85%B5%E1%86%AB%E1%84%89%E1%85%A3%E1%86%BA_2024-08-19_%E1%84%8B%E1%85%A9%E1%84%92%E1%85%AE_2.37.59.png)



jsx
// 배열 생성 (초기 값 할당)
let arr = ['kim', 'yong', 'min'];

        // 배열의 크기를 미리 지정하기
        let arr = [,,,]; // undefined가 출력된다.


        1. **Array() 생성자 함수로 배열 생성**

        배열 생성



jsx
// 배열 생성
let arr = new Array();

        arr[0] = 'kim';
        arr[1] = 'yong';
        arr[2] = 'min';

        for (let i = 0; i < arr.length; i++) {
        	console.log(arr[i]);
        }

        // 값을 할당한 채로 배열을 생성할 수 있다.
        let arr = new Array('kim', 'yong', 'min');

        // 배열의 크기를 지정하여 생성
        let arr = new Array(3);

        // 배열의 크기를 지정하여 생성한 후 원하는 값으로 채워넣을 수 있다.
        new Array(20).fill(0);

        // output: [0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0]


        - 다양한 Array method에 대해 정리해주세요. 🍠
            - sort 🍠 → 정렬하고 배열이 달라진다

                https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/Array/sort

                ### ❓**sort() 메서드는 어떤 정렬 알고리즘으로 구현되어 있을까 ?**

                !https://velog.velcdn.com/images/loiloi621/post/f60aa958-5290-4325-9b1a-a3e75d89375e/image.png

                mdn에서 sort() 메서드를 정의할 때 stable sort가 아닐 수 있다고 적혀있습니다.

                **stable sort**란 배열의 중복된 요소의 순서가 바뀌지 않는 것을 뜻합니다.

                예를 들어, const arr=[1,5(1),7(1),5(2),7(2)] 이라는 배열이 존재할 때 (중복 원소의 순서를 나타냅니다. ex) 1번째 5), stable sort는 arr=[1,5(1),5(2),7(1),7(2)]로 정렬된다는 것입니다.

                즉 , sort()는 정렬 과정에서 중복되는 요소의 자리가 바뀌는 (ex ) arr=[1,5(2),5(1),7(2),7(1)]) 불필요한 연산 과정이 포함될 수 있다는 것입니다.

                무슨 알고리즘으로 구현되어 있길래 그럴까요 ?

                ### ❗️sort()는 Tim sort 알고리즘으로 구성되어 있다.

                Time Sort는 Insertion sort와 Merge sort를 결합하여 만든 정렬 알고리즘입니다. 최선의 시간 복잡도는 O(n) , 평균과 최악은 O(nlogn)입니다. 작은 데이터 배열에 대해선 insertion sort를 사용하고 크기가 커질 때 merge sort를 사용하는 알고리즘입니다.

                [> Tim Sort에 대한 자세한 설명](https://d2.naver.com/helloworld/0315536)

                sort() 메서드는 원배열의 요소를 적절한 위치에 정렬한 후 , 해당 배열을 반환합니다. **즉 , 원본 배열이 변환된다는 뜻입니다.**

                ![스크린샷 2024-09-25 오전 12.51.29.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/f1912130-0409-4e90-a90f-6091ae253e73/c2f4b719-39c1-4079-ab80-81948e338df6/%E1%84%89%E1%85%B3%E1%84%8F%E1%85%B3%E1%84%85%E1%85%B5%E1%86%AB%E1%84%89%E1%85%A3%E1%86%BA_2024-09-25_%E1%84%8B%E1%85%A9%E1%84%8C%E1%85%A5%E1%86%AB_12.51.29.png)



jsx
const arr = [1, 3, 2, 0, 7, 5, 4];
arr.sort((a, b) => {
return b - a;
});
console.log(arr); //[7, 5, 4, 3,2, 1, 0]

            - join 🍠

                https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/Array/join

                Array.prototype.join() 메서드는 배열의 모든 요소를 join()의 인자 값으로 구분하여 **연결한 새 문자열을 만들어 반환홥니다.**



jsx
const arr = ["UMC", "WEB", "A팀", "화이팅"];
console.log(arr.join(" ")); // UMC WEB A팀 화이팅

            - reverse 🍠

                https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/Array/reverse

                reverse() 메서드는 배열의 순서를 반전합니다.

                O(n)의 시간 복잡도를 갖습니다.

                ~~아마도 새로운 배열을 만든 뒤에 뒷 부분부터 하나씩 갖고 오는 것 같음.~~

            - splice 🍠

                https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/Array/splice

                splice는 접착이라는 뜻을 가지고 있습니다. 기존 배열의 요소들 중 삭제, 대체 등의 기능을 위해 사용합니다.



jsx
let fruits = ['apple', 'banana', 'cherry', 'date'];

                // 인덱스 1부터 2개의 요소를 제거
                // item에 어떠한 요소도 지정하지 않으면 splice()는 요소를 제거하기만 합니다.
                let removed = fruits.splice(1, 2);

                console.log(fruits); // ['apple', 'date']
                console.log(removed); // ['banana', 'cherry']

                let fruits = ['apple', 'banana', 'date'];

                // 인덱스 1에 'cherry' 추가
                // 첫 번째 인덱스에 어떠한 요소도 삭제하지 않고, 'cherry' 요소만 추가
                fruits.splice(1, 0, 'cherry');

                console.log(fruits); // ['apple', 'cherry', 'banana', 'date']

                let fruits = ['apple', 'banana', 'cherry', 'date'];

                // 인덱스 1부터 2개의 요소를 제거하고 그 위치에 'grape', 'kiwi' 추가
                fruits.splice(1, 2, 'grape', 'kiwi');

                console.log(fruits); // ['apple', 'grape', 'kiwi', 'cherry', 'date']


            - slice 🍠

                slice() 메서드는 begin부터 end까지(end 미포함)에 대한 **얕은 복사본을 새로운 배열 객체**로 반환하며 , **원본 배열은 바뀌지 않습니다.**

                https://velog.io/@loiloi621/JS-깊은-복사와-얕은-복사

            - find 🍠

                find() 메서드는 배열에서 제공된 테스트 함수를 만족하는 첫 번째 요소를 반환합니다. (모든 요소를 반환하지 않습니다.) 테스트 함수에 만족하는 값이 없으면 undefined를 반환합니다.

                자매품 : findIndex (요소의 인덱스) , indexOf (값의 인덱스) , includes (return boolean) 등

            - filter 🍠

                filter()는 배열의 요소들을 각각 순회하여 주어진 조건을 만족하는 값들을 **얕은 복사본**으로 반환하는 메소드입니다. 희소 배열의 빈 슬롯에 대해서는 실행되지 않습니다.



jsx
const words = ['spray', 'elite', 'exuberant', 'destruction', 'present'];

                const result = words.filter((word) => word.length > 6);

                console.log(result);
                // Expected output: Array ["exuberant", "destruction", "present"]


            - map 🍠

                map() 메서드는 배열 내의 모든 요소 각각에 대하여 주어진 함수를 호출 한 결과를 모아 **새로운 배열을 반환**합니다. (원본 배열은 수정되지 않습니다. )

                지정한 idx를 건너뛰거나 할 수 있습니다.



jsx
const arr = ["UMC", "WEB", "A팀", "화이팅"];

                const arr1 = arr.map((el, idx) => {
                    if (idx === 1) return;
                    return el + "!";
                });
                console.log(arr1); // [ 'UMC!', undefined, 'A팀!', '화이팅!' ]

                // 자주 사용하는 코드
                ["1", "2", "3"].map(Number); // [1, 2, 3]


            - reduce 🍠

                reduce()는 배열의 각 요소에 대하여 지정한 콜백 함수를 실행하면서 하나의 누적된 결과값을 반환하는 메서드입니다. 주로 배열에서 조건을 통과한 값을 합치거나 , 모든 요소를 하나의 값으로 합칠 때 사용됩니다.



jsx
const data = [
"car",
"car",
"truck",
"truck",
"bike",
"walk",
"car",
"van",
"bike",
"walk",
"car",
"van",
"car",
"truck",
];
const vehicles = data.reduce((acc, cur) => {
if (!acc[cur]) {
acc[cur] = 0;
}
acc[cur]++;
return acc;
}, {}); // initialValue에 빈 객체 ({}) 를 넣어주어 , acc는 {}로 초기화된 후 시작
console.log(vehicles);

                // { car: 5, truck: 3, bike: 2, walk: 2, van: 2 }


            - some  🍠

                some() 메서드는 배열 안의 어떤 요소라도 주어진 테스트 함수를 적어도 하나라도 통과하는지 테스트합니다. 하나라도 통과하면 true 반환 그렇지 않으면 false를 반환합니다.

            - every 🍠

                every() 메서드는 배열 안의 어떤 요소라도 주어진 테스트 함수를 모두 통과하는지 테스트합니다. 모두 통과하면 true , 그렇지 않으면 false를 반환합니다.

            - forEach 🍠

                forEach() 메서드는 map() 메서드와 다르게 어떠한 값을 반환하고자 의도된 메서드가 아닙니다. (map과 다르게 항상 undefined를 반환합니다.) **즉 , 순회만을 목적으로 하여 부수 효과 (side effect)를 낼 뿐** , 어떤 값을 도출하기 위한 메서드가 아닙니다.

                또한 , forEach를 사용하면서 주의해야 할 점은 중간에 반복문을 멈출 수가 없다는 것입니다. 조기 종료를 수행하고 싶다면 for 문을 사용해야 합니다.

    - 함수

        ### 함수 (function)

        ### 함수 선언문



jsx
function subtraction(a, b) {
return a - b;
}

        subtraction(5, 3); // 2


        함수 선언문은 표현식이 아닌 일반 문(statement)으로 분류합니다.

        ### 함수 표현식



jsx
let subtraction2 = function (a, b) {
return a - b;
}

        subtraction2(5, 3); // 2


        함수 표현식은, 함수를 변수에 할당합니다.

        ### 화살표 함수



jsx
let subtraction3 = (a, b) => {
return a - b;
}

        subtraction3(5, 3); // 2


        ES6에 추가된 화살표 함수도 많이 사용합니다.

        <aside>
        💡

        함수 선언 방식별 this 바인딩

        </aside>

        ### 호이스팅 (Hoisting) 🍠

        ### 변수 선언 , 초기화 , 할당

        **변수 선언**이란 값을 저장하기 위한 메모리 공간을 확보하고 , 변수 이름과 확보된 메모리 공간의 주소를 연결하여 값을 저장할 수 있게 준비하는 것이다.

        let , const ,var 는 변수 선언을 위한 키워드이다.

        해당 식별자 (변수 이름 , 함수 이름 등)를 등록하여 스코프가 참조할 대상을 만든다.

        **변수 초기화**는 메모리에 변수 저장을 위한 공간을 확보하는 단계이다. 기본 값으로 undefined가 할당된다.

        ### let , const , var 키워드에 따른 변수 초기화 방법

        변수 선언은 소스 코드가 한 줄 씩 순차적으로 실행되는 시점 (런타임)이 아니라 그 이전에 실행된다.

        JS 엔진은 소스 코드의 **평가 과정(실행 컨텍스트 생성)에서 변수 선언을 포함한 모든 선언문 (변수 선언문 , 함수 선언문)을 소스 코드에서 찾아내 먼저 실행**한다.

        이후 , 평가 과정이 끝나면 선언문을 제외하고 , 소스 코드를 한 줄씩 순차적으로 실행한다. (런타임 인터프리트) ⇒ 변수 선언이 소스 코드의 어디 있는 상관 없이 다른 코드보다 먼저 실행됨을 의미

        이처럼 변수 선언문이 코드의 선두로 끌어올려진 것처럼 동작하는 자바스크립트 고유의 특징을 **변수 호이스팅**이라고 한다.

        <aside>
        💡

        hoist : 감아 올리기라는 뜻.

        </aside>

        **var (전역 스코프)**

        var 키워드 (거의 사용하지 않는)를 사용하면 변수 선언은 **선언 단계**와 **초기화 단계**가 **동시에 진행**된다. 즉 , 메모리 주소를 할당받는 동시에 undefined가 저장된다.



jsx
console.log(a); // undefined
var a = 5;

        **let (블록 레벨 스코프)**

        let 키워드로 선언한 변수는 선언 단계와 초기화 단계가 분리되어 진행 .

        **선언 단계**는 런타임 이전에 JS 엔진에 의해 암묵적으로 실행되지만 **초기화 단계**는 런타임에 변수 선언문에 도달했을 때 실행된다.

        ![모던자바스크립트 deep dive 12.jpeg](https://prod-files-secure.s3.us-west-2.amazonaws.com/f1912130-0409-4e90-a90f-6091ae253e73/c0840142-1125-4e54-850e-b73131eb95d4/%E1%84%86%E1%85%A9%E1%84%83%E1%85%A5%E1%86%AB%E1%84%8C%E1%85%A1%E1%84%87%E1%85%A1%E1%84%89%E1%85%B3%E1%84%8F%E1%85%B3%E1%84%85%E1%85%B5%E1%86%B8%E1%84%90%E1%85%B3_deep_dive_12.jpeg)

        **const (블록 레벨 스코프)**

        const 키워드로 선언한 변수는 반드시 선언과 동시에 초기화 되어야 한다. (let은 선언만 해도 괜찮음.) let과 같이 TDZ에 의해 안전하게 참조가 가능하다.



jsx
console.log(b); // ReferenceError: Cannot access 'b' before initialization
const b = 10;

    - 클래스

        ### 클래스 (class)

        Student라는 클래스를 만들어 보겠습니다.

        **class라는 키워드를 이용**해서 **선언**을 해주고, **constructor 생성자를 이용**해서, **나중에 object를 만들 때 필요한 데이터를 전달**해주면 됩니다.

        전달 받은 데이터를 class에 존재하는 필드에, 전달된 데이터를 바로 할당해줍니다.



jsx
// 클래스 선언
class Student {
constructor(name, school) {
// 필드
this.name = name;
this.school = school;
}
}

        이번엔 전달받은 클래스의 이름과 학교명을 갖고, 자기소개를 하는 **methods**를 만들어보겠습니다. 만드는 방법 또한 매우 간단합니다.



jsx
// 클래스 선언
class Student {
constructor(name, school) {
// 필드
this.name = name;
this.school = school;
}
// 메소드
introduction() {
console.log(`안녕하세요, ${this.name}입니다. ${this.school}에 다니고있습니다`)
}
}

        아래와 같이 만든 클래스를 이용하여, **new 키워드를 통해 새로운 object를 만들 수 있습니다.** name과 school을 맞는 위치에 같이 전달해주면 됩니다.



jsx
const matthew = new Student('matthew', '상명대학교');
console.log(matthew.name);
console.log(matthew.school);
matthew.introduction();

        ![스크린샷 2024-08-19 오후 3.59.50.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/f1912130-0409-4e90-a90f-6091ae253e73/4df14540-faeb-4238-940f-241c42af9c83/%E1%84%89%E1%85%B3%E1%84%8F%E1%85%B3%E1%84%85%E1%85%B5%E1%86%AB%E1%84%89%E1%85%A3%E1%86%BA_2024-08-19_%E1%84%8B%E1%85%A9%E1%84%92%E1%85%AE_3.59.50.png)

        ### 아래 내용에 대해 추가적으로 학습 후 정리해 보세요! 🍠

        <aside>
        💡 위의 예시의 코드를 활용해서, 코드를 작성해주시고, 설명 또한 작성해주세요!

        </aside>

        - getter 🍠
        - setter 🍠

### react에서 자주 사용하는 자바스크립트 문법

-   구조 분해 할당(Destructuring assignment)
    ### 구조 분해 할당 (배열)
    구조 분해 할당 구문은, 배열이나 객체의 속성을 해체하여 그 값을 개별 변수에 담게 하는 JS 표현식입니다.
    먼저, react에서는 컴포넌트에 state 변수를 추가할 수 있는 React Hook인 useState를 활용합니다.
    react를 아직 자세히 모르시는 분은, 이런 것을 나중에 배우는구나 하고 생각하며 이해만 하시면 됩니다. **useState**의 구조는 아래와 같습니다.

jsx
const [yongmin, setYongmin] = useState('초기값')

    useState는 2개의 배열을 반환하는 함수이며, 첫 번째 값을 value, 두번째 값을 value를 변경하는 setter로 사용이 가능합니다.

jsx
const UMC = ['WEB', 'SPRING', 'NODE', 'iOS', 'Android', 'PLAN', 'DESIGN'];

    const [first, , , , , last] = UMC;

    first; // 'WEB'
    last; // 'DESIGN'


    배열의 구조 분해 할당은 **,의 위치에 따라 값이 결정**됩니다.

    위의 방식은, 길이가 긴 배열일 경우,  실수를 할 가능성이 매우 크기에, 배열의 길이가 작은 경우 많이 활용합니다. 배열의 구조 분해 할당은 기본 값을 선언할 수 있습니다.

jsx
const array = [1, 2];
const [a = 'KIM', b = 'YONG', c = 'MIN'] = array;

    // a 1
    // b 2
    // c MIN (준비된 배열의 길이가 총 2개이지만, c는 3번째이기에, 미리 할당한 'MIN'을 출력)


    만약 먼저 선언한 배열의 길이보다, 사용하고자 하는 배열의 길이가 짧거나 값이 없는 경우에는 **undefined** 기본값을 사용합니다.

    특정 값 이후의 값을 다시 배열로 선언하고 싶은 경우에는 전개 연산자를 활용할 수 있습니다.

jsx
const UMC = ['WEB', 'SPRING', 'NODE', 'iOS', 'Android', 'PLAN', 'DESIGN'];
const [first, ...etc] = UMC;

    first // 'WEB'
    etc // ['SPRING', 'NODE', 'iOS', 'Android', 'PLAN', 'DESIGN']


    ### 구조 분해 할당 (객체)

    객체의 구조 분해 할당은, 객체에서 값을 뽑아온 뒤 할당하는 것을 의미합니다. 배열과는 다르게, 객체는, 객체의 내부 이름을 통해 뽑아온다는 차이점이 있습니다.

jsx
const myName = {
kim: '김',
yong: '용',
min: '민',
}

    const { kim, ...rest } = myName;

    // kim => '김'
    // rest => { yong: '용', min: '민' }


    기본 값 할당 또한 배열과 동일하게 가능합니다.

jsx
const myName = {
yong: '용',
min: '민',
}

    const { yong = '야', min = '호', yaho = '야호' } = myName

    yong // '용'
    min // '민'
    yaho // '야호'


    리액트에서 어떠한 값들을 전달할 때, props를 통해 부모에서 자식 컴포넌트로 값을 전달할 때 많이 활용되는 방식이므로 꼭 알고 있어야 하는 문법입니다.

jsx
// props.name, props.age 이러한 식으로 접근해야하지만
// 구조 분해 할당을 통해서 name, age로 접근이 가능합니다.
function ChildComponent({ name, age }) {
return (
<>
<h1>안녕하세요 {name}입니다.<h1/>
<span>{age}살 입니다.</span>
</>
)
}

    위의 리액트 코드는 웹을 처음 접하시면 당연히 이해할 수 없지만, 이러한 방식으로 많이 활용된다는 점을 이해해주시면 됩니다.

-   전개 연산자 (Spread Operator)
    ### 전개 연산자 (Spread Operator)
    React를 활용하여 웹 프로젝트를 진행하다보면, 배열 간에 합성을 해야 할 경우가 상당히 많이 생깁니다. 전개 연산자가 나오기 이전에는 배열 간 합성을 하기 위하여 push, splice, concat과 같은 배열 메서드를 사용해야 했습니다. 그러나, 전개 연산자를 활용하면, 배열을 쉽게 합성할 수 있습니다.

jsx
const yaho = ['y', 'a']
const realYaho = [...yaho, 'h', 'o'] // ['y', 'a', 'h', 'o']

    여기서, 살짝 참조에 관한 개념을 짚고 넘어가겠습니다.

jsx
const yongmin = ['Kim', 'Yong', 'Min'];
const yongmin2 = yongmin;

    yongmin === yongmin2; // true


    위의 결과 값이 true가 나온 이유는 무엇일까요? 내용이 아닌 **객체의 참조 주소를 복사하기에 true가 반환**됩니다.

    하지만, 전개 연산자를 활용하게 되면, 기존 배열에 영향을 미치지 않고, 배열을 복사하는 것이 가능합니다.

jsx
const yongmin = ['Kim', 'Yong', 'Min'];
const yongmin2 = [...yongmin];

    yongmin === yongmin2; // false


    실제로 값만 복사하고, 참조가 다르기에 false가 반환됩니다.

    ### 전개 구문 (객체)

jsx
const KIM_YONG_MIN = {
Kim: '김',
Yong: '용',
Min: '민'
}

    const KIM_YONG_MIN_2 = {
    	Ma: '매',
    	tthew: '튜'
    }

    const EN_KO_NAME = { ...KIM_YONG_MIN, ...KIM_YONG_MIN_2 };
    // {Kim: '김', Yong: '용', Min: '민', Ma: '매', tthew: '튜'}


    객체를 새로 만들 때 전개 구문을 활용할 수 있고, 객체를 합성하는 데 편리함을 제공해 줍니다.

jsx
const kim = {
k: 'K',
i: 'I',
m: 'M',
}

    const object1 = {
    	...kim,
    	m: 'N'
    } // {k: 'K', i: 'I', m: 'N'}

    const object2 = {
    	m: 'N',
    	...kim
    } // {m: 'M', k: 'K', i: 'I'}


    전개 연산자 이후, 값을 할당한다면, 전개 연산자를 값 할당 이전에 활용하냐, 이후에 활용하냐에 따라, 결과값이 완전히 달라짐을 유의해야 합니다.

-   객체 초기자(object shorthand assignment)
    ### 객체 초기자
    객체 초기자 또한, 상당히 많이 활용하는 방식입니다.
    객체에 집어 넣고자 하는 키와 값을 가지고 있는 변수가 이미 존재한다면, 해당 값을 매우 간단하게 넣을 수 있는 방식입니다.

jsx
const easy = 'easy';
const hard = 'hard';

    const difficulty = {
    	easy,
    	hard,
    }

    // {easy: 'easy', hard: 'hard'}

-   Array 프로토타입의 메서드
    -   map
        ### map
        map은 인수로 전달받은 배열과 동일한 길이의 새로운 배열을 반환하는 메서드입니다. 배열의 아이템을 순회하면서, 콜백으로 연산한 결과의 새로운 배열을 만들 수 있습니다.

jsx
const numbers = [1, 2, 3, 4, 5, 6];

        const numbersPlusTwo = numbers.map((number) => number + 2);
        // [3, 4, 5, 6, 7, 8]


        React에서는 data들을, 배열에 담아, 해당 내용들을 리액트 요소로 반환할 떄 많이 사용합니다.



jsx
const KimYongMin = ['김', '용', '민'];

        const ReturnElement = KimYongMin.map((name) => {
        	return <div key={name}>{name}</div>
        });


    - filter

        ### filter

        filter() 메서드는 주어진 배열의 일부에 대한 얕은 복사본을 생성하고, 주어진 배열에서 제공된 함수에 의해 구현된 테스트를 통과한 요소로만 필터링 합니다.



jsx
// 길이가 5 이하인 단어만 출력하는 방법
const words = ['sweetPotato', 'Potato', 'haha', 'yaho'];

        const answer = words.filter((word) => word.length < 6);
        // ['haha', 'yaho']


    - reduce

        ### reduce

        map, filter를 쉽다고 생각하셨으면 reduce와 같은 경우는 조금 어렵게 느껴지실 수 있습니다. 해당 메서드는 콜백 함수 이외에 initial value (초기값)을 추가로 인수를 받습니다.

        초기값이 무엇인지에 따라 어떠한 타입의 무엇인가를 반환할 수 있는 메서드가 바로 reduce 입니다.

        보통, 어떠한 값을 누적해서 더할 때 많이 사용합니다.



jsx
const numbers = [10, 20, 30, 40, 50];

        // result의 초기값은 0이라고 생각하면 쉽다.
        const sum = numbers.reduce((result, number) => {
        	return result + number;
        }, 0);

        sum // 150


        reducer 콜백 함수의 첫 번째 인수는 초기값의 현재값을 의미, 두 번째 인수는 현재 배열의 아이템입니다.

    - forEach

        ### forEach

        forEach 함수는 콜백 함수를 받아 배열을 순회하면서, 단순히 해당 콜백 함수를 실행만 하는 메서드입니다.



jsx
const Matthew = ['M', 'A', 'T', 'T', 'H', 'E', 'W'];

        Matthew.forEach((alpha) => console.log(alpha));

        // M, A, T, T, H, E, W


        forEach는 아무런 반환값이 없습니다. 단순히 콜백함수를 실행만 시키고, map처럼 결과를 반환하는 작업은 하지 않습니다. (forEach의 반환값은 undefined로 의미가 없습니다.)

    - length

        ### length

        **length** 데이터 속성은 해당 배열의 요소 수를 나타냅니다.



jsx
const Matthew = ['M', 'A', 'T', 'T', 'H', 'E', 'W'];

        Matthew.length // 7



-   삼항 조건 연산자 (Ternary Operator)
    ### 삼항 조건 연산자
    **조건 (삼항) 연산자**는 JavaScript에서 세 개의 피연산자를 받는 유일한 연산자입니다. 앞에서부터 조건문, 물음표(?), 조건문이 참(truthy)일 경우 실행할 표현식, 콜론(:), 조건문이 거짓([falsy](https://developer.mozilla.org/ko/docs/Glossary/Falsy))일 경우 실행할 표현식이 배치됩니다. 해당 연산자는 [if...else](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Statements/if...else)문의 대체재로 빈번히 사용됩니다.

jsx
const number = 27;

    const isOdd = number % 2 !== 0 ? true : false
    // true (27은 홀수 이므로)


    아래와 같은 기준이라고 생각하면 이해하기 쉽습니다.

jsx
조건문 ? 조건문이 참인 경우 값 : 조건문이 거짓인 경우 값;

### DOM 조작 🍠

<aside>
💡

DOM 조작은 웹 개발에서 매우 중요한 개념으로, 미션 1을 수행하는 데 필수적인 내용을 다루고 있습니다. 특히, React와 같은 프론트엔드 라이브러리와 밀접하게 연관되어 있기 때문에, 이 부분에 대한 깊이 있는 이해는 필수적입니다.

구글 검색을 통해 관련된 자료들을 찾아보면 DOM 조작에 대한 매우 상세하고 유익한 설명을 쉽게 얻을 수 있습니다. 이러한 자료들을 참고하여 DOM 조작에 대한 핵심 키워드를 정리하고, 워크북에 체계적으로 기록해 주시기 바랍니다.

DOM 조작은 브라우저 상에서 HTML 문서의 구조를 동적으로 수정하고, 사용자와의 상호작용을 처리하는 중요한 방법론입니다. JavaScript를 통해 DOM을 조작하는 방법을 정확히 이해하고 익히는 것이 앞으로의 학습에 큰 도움이 될 것입니다. React에서의 상태 관리와 컴포넌트 렌더링 최적화 역시 DOM 조작의 원리를 기반으로 하고 있기 때문에, 시간을 들여 꼼꼼히 학습하시길 바랍니다.

-   UMC 7th 중앙 WEB 파트장 매튜/김용민 -

</aside>

-   태그 가져오기
    getElementsByTagName()
-   이벤트 리스너 추가하기
    addEventListener()
-   이벤트 리스너 제거하기
    removeEventListener()
-   키보드와 마우스 이벤트
    | **keydown** | 사용자가 키를 누를 때 발생하는 이벤트. |
    | ----------- | -------------------------------------- |
    | **keypress** | 사용자가 텍스트 입력 가능한 키를 누를 때 발생하는 이벤트 (deprecated). |
    | ------------ | ---------------------------------------------------------------------- |
    | **keyup** | 사용자가 키를 뗄 때 발생하는 이벤트. |
    | --------- | ------------------------------------ |
    | **click** | 사용자가 요소를 클릭할 때 발생하는 이벤트. |
    | --------- | ------------------------------------------ |
    | **dblclick** | 사용자가 요소를 더블 클릭할 때 발생하는 이벤트. |
    | ------------ | ----------------------------------------------- |
    | **mousedown** | 마우스 버튼을 누를 때 발생하는 이벤트. |
    | ------------- | -------------------------------------- |
    | **mouseup** | 마우스 버튼을 뗄 때 발생하는 이벤트. |
    | ----------- | ------------------------------------ |
    | **mousemove** | 마우스를 움직일 때 발생하는 이벤트. |
    | ------------- | ----------------------------------- |
    | **mouseover** | 마우스가 요소 위에 올려졌을 때 발생하는 이벤트 (자식 요소에도 발생). |
    | ------------- | -------------------------------------------------------------------- |
    | **mouseout** | 마우스가 요소에서 벗어났을 때 발생하는 이벤트. |
    | ------------ | ---------------------------------------------- |
    | **mouseenter** | 마우스가 요소 위로 처음 들어갈 때 발생하는 이벤트 (자식 요소 제외). |
    | -------------- | ------------------------------------------------------------------- |
    | **mouseleave** | 마우스가 요소에서 벗어날 때 발생하는 이벤트 (자식 요소 제외). |
    | -------------- | ------------------------------------------------------------- |
    | **contextmenu** | 마우스 오른쪽 버튼을 클릭해 컨텍스트 메뉴를 열 때 발생하는 이벤트. |
    | --------------- | ------------------------------------------------------------------ |
    | **wheel** | 마우스 휠이 움직일 때 발생하는 이벤트. |
    | --------- | -------------------------------------- |
    | **dragstart** | 사용자가 드래그를 시작할 때 발생하는 이벤트. |
    | ------------- | -------------------------------------------- |
    | **drag** | 드래그 중에 발생하는 이벤트. |
    | -------- | ---------------------------- |
    | **dragend** | 드래그가 끝날 때 발생하는 이벤트. |
    | ----------- | --------------------------------- |
    | **dragenter** | 드래그된 요소가 다른 요소 위로 들어갈 때 발생하는 이벤트. |
    | ------------- | --------------------------------------------------------- |
    | **dragover** | 드래그된 요소가 다른 요소 위에 있을 때 발생하는 이벤트. |
    | ------------ | ------------------------------------------------------- |
    | **dragleave** | 드래그된 요소가 다른 요소 밖으로 나갈 때 발생하는 이벤트. |
    | ------------- | --------------------------------------------------------- |
    | **drop** | 드래그된 요소가 드롭될 때 발생하는 이벤트. |
    | -------- | ------------------------------------------ |
    | **focus** | 요소에 포커스가 갈 때 발생하는 이벤트. |
    | --------- | -------------------------------------- |
    | **blur** | 요소에서 포커스가 벗어날 때 발생하는 이벤트. |
    | -------- | -------------------------------------------- |
    | **scroll** | 스크롤할 때 발생하는 이벤트. |
    | ---------- | ---------------------------- |
-   태그 속성 다루기
    setAttribute()
-   부모와 자식 태그 찾기
    parentElement()
    children()
-   새로운 태그 만들기
    createElement()
-   태그 복제하기
    cloneNode()
