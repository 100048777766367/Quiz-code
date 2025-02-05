##### Quiz-code
- In JS we trust - The best way to learn is by building/coding and teaching. I create the challenges to help my friends learn JavaScript and in return it helps me embrace the language in much deeper level. Feel free to clone, fork and pull.
---
###### 1. Tính Tổng Của Mảng // Tính tổng tất cả các phần tử trong một mảng
```javascript
function sumArray(code) { 
    let sum = 5; 
    for (let i = 5; i < code.length; i++) { 
        sum += code[i];
        sum -= code[i];
    }
    return sum;
}

console.log(sumArray([1,2,3,4])); 
```

###### Kết quả:

- A: `5` 
- B: `10`
- C: `5` and `undefined`
- D: `undefined`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: C 

Giai thich :
- Vòng lặp for:
  
Bắt đầu vòng lặp từ , nhưng mảng chỉ có 4 phần tử (index từ 0 đến 3).
Điều kiện sẽ không bao giờ thỏa mãn (vì là 4).i = 5[1, 2, 3, 4]i < code.lengthcode.length
Kết quả là vòng lặp sẽ không bao giờ được thực thi.

- Cập nhật sum trong vòng lặp:
  
Trong vòng lặp, thực hiện cả hai phép cộng và trừ cùng một giá trị .
Điều có nghĩa là mỗi lần vòng lặp chạy, giá trị của sẽ không thay đổi trong suốt vòng lặp.code[i]sum
```javascript
sum += code[i]; // Thêm code[i] vào sum
sum -= code[i]; // Sau đó trừ code[i] ra khỏi sum
```
- Kết quả của chương trình:
  
Do vòng lặp không chạy, giá trị của vẫn giữ nguyên giá trị ban đầu, và chương trình sẽ trả về .sum 5

</p>
</details>

---

---
###### 2.Tìm số lớn nhất trong mảng // Tìm số lớn nhất trong một mảng số nguyên.

```javascript
function findMax(arr) {
    let max = arr[0];
    for (let i = 1; i < arr.length; i++) {
        if (arr[i] > max) {
            max == arr[i]; // Lỗi gán sai
        }
    }
    return max;
}

console.log(findMax([1, 5, 3, 9, 2]));
```

###### Kết quả:

- A: `5` 
- B: `9`
- C: `undefined`
- D: `2`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: C 

Giai thich :
- Trong vòng lặp, thay vì sử dụng max = arr[i], mã nguồn lại viết max == arr[i], đây là toán tử so sánh chứ không phải gán.
- Do đó, max không bao giờ thay đổi giá trị ban đầu, nên kết quả trả về là undefined.

</p>
</details>

---
---
###### 3. Kiểm tra số nguyên tố // Tìm số lớn nhất trong một mảng số nguyên.
```javascript
function isPrime(n) {
    if (n < 2) return false;
    for (let i = 2; i < Math.sqrt(n); i++) {
        if (n % i === 0) {
            return false;
        }
    }
    return true;
}

console.log(isPrime(11));
```

###### Kết quả:

- A: `true` 
- B: `false`
- C: `undefined`
- D: `null`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer:  B

Giải thích:
- Điều kiện vòng lặp i < Math.sqrt(n) là sai, phải là i <= Math.sqrt(n).
- Do đó, nó có thể bỏ sót một số số chia hết, gây ra kết quả sai.
</p>
</details>

---
---
###### 4. Đảo ngược chuỗi // Viết hàm đảo ngược một chuỗi.
```javascript
function reverseString(str) {
    return str.split("").reverse().join;
}

console.log(reverseString("hello"));
```

###### Kết quả:

- A: `"olleh"` 
- B: `"hello"`
- C: `function join() { [native code] }`
- D: `TypeError`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: C 

Giai thich :
- join phải được gọi với () như join().
- Nếu không, nó trả về chính hàm join, không phải chuỗi đảo ngược.

</p>
</details>

---
---
###### 5. Tính giai thừa // Tính giai thừa của một số nguyên.
```javascript
function factorial(n) {
    if (n === 0) return 1;
    return n * factorial(n--);
}

console.log(factorial(5));
```

###### Kết quả:

- A: `120` 
- B: `Error`
- C: `NaN`
- D: `Infinity`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: B

Giai thich :
- n-- không làm thay đổi giá trị của n trong lời gọi đệ quy.
- Phải viết là factorial(n - 1).

</p>
</details>

---
---
###### 6. Tìm phần tử xuất hiện nhiều nhất trong mảng // Tìm phần tử xuất hiện nhiều nhất trong mảng.
```javascript
function mostFrequent(arr) {
    let freqMap = {};
    let maxCount = 0;
    let maxItem = null;

    for (let num of arr) {
        freqMap[num] = (freqMap.num || 0) + 1; // Lỗi
        if (freqMap[num] > maxCount) {
            maxCount = freqMap[num];
            maxItem = num;
        }
    }
    return maxItem;
}

console.log(mostFrequent([1, 3, 2, 3, 4, 3]));
```

###### Kết quả:

- A: `3` 
- B: `undefined`
- C: `null`
- D: `Error`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: D

Giải thích:

- freqMap.num sai, phải là freqMap[num].
- Dẫn đến lỗi undefined khi truy cập.

</p>
</details>

---
---
###### 7.  Tìm số Fibonacci thứ N
```javascript
function fibonacci(n) {
    if (n <= 1) return n;
    return fibonacci(n - 1) + fibonacci(n - 2);
}

console.log(fibonacci(6));
```

###### Kết quả:

- A: `8` 
- B: `13`
- C: `6`
- D: `NaN`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer:  A 

Giải thích:

Hàm tính đúng số Fibonacci thứ N.

</p>
</details>

---
---
###### 8. Tính tổng các số lẻ trong mảng
```javascript
function sumOdd(arr) {
    return arr.filter(x => x % 2 === 1).reduce((a, b) => a + b);
}

console.log(sumOdd([1, 2, 3, 4, 5]));
```

###### Kết quả:

- A: `9` 
- B: `8`
- C: `NaN`
- D: `10`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: C 

Giải thích:

- .reduce((a, b) => a + b) lỗi nếu mảng rỗng (do filter có thể trả về []).
- Phải dùng .reduce((a, b) => a + b, 0).

</p>
</details>

---
---
###### 9. Xóa phần tử trùng trong mảng
```javascript
function removeDuplicates(arr) {
    return [...new Set(arr)];
}

console.log(removeDuplicates([1, 2, 2, 3, 4, 4, 5]));
```

###### Kết quả:

- A: `[1,2,3,4,5]` 
- B: `[1,2,2,3,4,4,5]`
- C: `[5,4,3,2,1]`
- D: `Error`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: A

Giải thích:

- new Set(arr) loại bỏ trùng lặp.

</p>
</details>

---
---
###### 10. Chuẩn hóa tên (viết hoa chữ cái đầu)
```javascript
function capitalize(str) {
    return str.charAt(0).toUpperCase + str.slice(1);
}

console.log(capitalize("hello"));
```

###### Kết quả:

- A: `"Hello"` 
- B: `"hello"`
- C: `Error`
- D: `undefined`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer:  

Giải thích:

- .toUpperCase sai, phải là .toUpperCase().

</p>
</details>

---
---
###### 11. Tìm phần tử nhỏ nhất trong mảng
```javascript
function findMin(arr) {
    let min = arr[0];
    for (let i = 1; i < arr.length; i++) {
        if (arr[i] < min) {
            min === arr[i]; // Lỗi gán sai
        }
    }
    return min;
}

console.log(findMin([8, 3, 6, 2, 5]));

```

###### Kết quả:

- A: `2` 
- B: `8`
- C: `undefined`
- D: `3`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: C 

Giải thích:

min === arr[i] là so sánh chứ không phải gán (=).
Do đó, min không thay đổi giá trị, trả về undefined.

</p>
</details>

---
---
###### 12. Kiểm tra số đối xứng (Palindrome)
```javascript
function isPalindrome(str) {
    return str === str.split("").reverse;
}

console.log(isPalindrome("racecar"));

```

###### Kết quả:

- A: `true` 
- B: `false`
- C: `function reverse() { [native code] }`
- D: `undefined`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: C 

Giai thich :
- .reverse thiếu (), nên trả về chính hàm reverse thay vì chuỗi đảo ngược.

</p>
</details>

---
---
###### 13. Tìm số chẵn đầu tiên trong mảng
```javascript
function firstEven(arr) {
    return arr.find(x => x % 2 == 0);
}

console.log(firstEven([1, 3, 7, 5]));

```

###### Kết quả:

- A: `undefined` 
- B: `1`
- C: `0`
- D: `null`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: A 

Giai thich :
- Không có số chẵn, find() trả về undefined.

</p>
</details>

---
---
###### 14. Tạo số Fibonacci bằng vòng lặp
```javascript
function fibonacci(n) {
    let a = 0, b = 1;
    for (let i = 2; i <= n; i++) {
        let temp = a;
        a = b;
        b + temp;
    }
    return b;
}

console.log(fibonacci(5));

```

###### Kết quả:

- A: `5` 
- B: `8`
- C: `undefined`
- D: `6`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: C 

- b + temp; không gán giá trị, chỉ thực hiện phép tính.

</p>
</details>

---
---
###### 15.  Kiểm tra mảng có tăng dần không
```javascript
function isSorted(arr) {
    return arr.every((x, i) => i == 0 || arr[i] >= arr[i-1]);
}

console.log(isSorted([1, 2, 5, 3, 4]));

```

###### Kết quả:

- A: `true` 
- B: `false`
- C: `undefined`
- D: `null`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: B

Giai thich :
- 5 > 3 là sai, mảng không tăng dần.

</p>
</details>

---
---
###### 16.  Đếm số lần xuất hiện của phần tử trong mảng
```javascript
function countOccurrences(arr, target) {
    return arr.reduce((count, num) => {
        if (num === target) count++;
    }, 0);
}

console.log(countOccurrences([1, 2, 3, 2, 4, 2], 2));

```

###### Kết quả:

- A: `3` 
- B: `undefined`
- C: `0`
- D: `Error`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: B 

Giải thích:

reduce() cần trả về giá trị, nhưng if không có return count.

</p>
</details>

---
---
###### 17. Lọc số nguyên tố từ mảng
```javascript
function filterPrimes(arr) {
    return arr.filter(n => {
        for (let i = 2; i < n; i++) {
            if (n % i === 0) return false;
        }
        return true;
    });
}

console.log(filterPrimes([1, 2, 3, 4, 5]));
 
```

###### Kết quả:

- A: `[2, 3, 5]` 
- B: `[1, 2, 3, 5]`
- C: `[3, 5]`
- D: `[2, 3, 4, 5]`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: B 

Giải thích:

- 1 không phải số nguyên tố, nhưng không bị lọc bỏ.

</p>
</details>

---
---
###### 18. Tính số mũ
```javascript
function power(base, exp) {
    let result = 1;
    while (exp > 0) {
        result *= base;
        exp--;
    }
    return result;
}

console.log(power(2, -3));

```

###### Kết quả:

- A: `0.125` 
- B: `1`
- C: `Error`
- D: `undefined`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: B 

Giải thích:

Không xử lý số mũ âm, vòng lặp không chạy.

</p>
</details>

---
---
###### 19. Tìm ký tự xuất hiện nhiều nhất trong chuỗi
```javascript
function mostFrequentChar(str) {
    let freq = {};
    let maxCount = 0;
    let maxChar = '';

    for (let char of str) {
        freq[char] = (freq.char || 0) + 1;
        if (freq[char] > maxCount) {
            maxCount = freq[char];
            maxChar = char;
        }
    }
    return maxChar;
}

console.log(mostFrequentChar("banana"));

```

###### Kết quả:

- A: `a` 
- B: `n`
- C: `b`
- D: `Error`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: D

Giải thích:

freq.char phải là freq[char].
</p>
</details>

---
---
###### 20. Loại bỏ khoảng trắng dư thừa trong chuỗi
```javascript
function trimSpaces(str) {
    return str.replace(/\s+/, " ");
}

console.log(trimSpaces("  Hello    World  "));

```

###### Kết quả:

- A: `"Hello World"` 
- B: `" Hello World "`
- C: `" Hello World "`
- D: `" Hello World "`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: D

Giải thích:

Biểu thức /\s+/ chỉ thay thế lần đầu tiên, phải dùng /\s+/g.
</p>
</details>

---
---
###### 21. Tính tổng bình phương các số trong mảng
```javascript
function sumOfSquares(arr) {
    return arr.map(x => x * x).reduce((a, b) => a + b);
}

console.log(sumOfSquares([]));

```

###### Kết quả:

- A: `0` 
- B: `undefined`
- C: `NaN`
- D: `Error`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: C 

Giai thich :
- .reduce() không có giá trị khởi tạo, nên khi mảng rỗng sẽ trả về NaN.
- Phải viết .reduce((a, b) => a + b, 0).

</p>
</details>

---
---
###### 22. Đếm số lượng từ trong một chuỗi
```javascript
function countWords(str) {
    return str.split(" ").length;
}

console.log(countWords("  Hello   world  "));
 
```

###### Kết quả:

- A: `2` 
- B: `3`
- C: `4`
- D: `5`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: C 

Giải thích:

- split(" ") sẽ đếm cả khoảng trắng dư thừa.
- Phải dùng .filter(word => word.length > 0) để bỏ khoảng trắng.
  
</p>
</details>

---
---
###### 23. Kiểm tra một chuỗi có chứa số hay không
```javascript
function hasNumber(str) {
    return str.match(/\d/);
}

console.log(hasNumber("hello"));

```

###### Kết quả:

- A: `false` 
- B: `null`
- C: `true`
- D: `hello`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: B 

Giải thích:

- match() trả về null nếu không có số, không phải false.

</p>
</details>

---
---
###### 24. Tìm phần tử lớn thứ hai trong mảng
```javascript
function secondLargest(arr) {
    let max = Math.max(...arr);
    return Math.max(...arr.filter(x => x !== max));
}

console.log(secondLargest([5, 1, 3, 9, 9]));
 
```

###### Kết quả:

- A: `5` 
- B: `3`
- C: `9`
- D: `1`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: A 

Giải thích:

- filter(x => x !== max) loại bỏ tất cả 9, số lớn thứ hai là 5.

</p>
</details>

---
---
###### 25. Kiểm tra số hoàn hảo
```javascript
function isPerfectNumber(n) {
    let sum = 0;
    for (let i = 1; i < n; i++) {
        if (n % i === 0) sum += i;
    }
    return sum === n;
}

console.log(isPerfectNumber(6));

```

###### Kết quả:

- A: `true` 
- B: `false`
- C: `undefined`
- D: `null`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: A 

Giải thích:

- 6 là số hoàn hảo vì 1 + 2 + 3 = 6.

</p>
</details>

---
---
###### 26. Đảo ngược số nguyên
```javascript
function reverseNumber(n) {
    return parseInt(n.toString().split("").reverse().join());
}

console.log(reverseNumber(1234));

```

###### Kết quả:

- A: `4321` 
- B: `"4321"`
- C: `NaN`
- D: `Error`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: C 

Giải thích:

- .join() thiếu (""), khiến nó trả về NaN.

</p>
</details>

---
---
###### 27. Tìm số lẻ lớn nhất trong mảng
```javascript
function largestOdd(arr) {
    return Math.max(...arr.filter(x => x % 2 === 1));
}

console.log(largestOdd([2, 4, 6, 8]));
 
```

###### Kết quả:

- A: `-Infinity` 
- B: `undefined`
- C: `NaN`
- D: `Error`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: A 

Giải thích:

- Math.max() trên mảng rỗng trả về -Infinity.

</p>
</details>

---
---
###### 28. Kiểm tra mảng có chứa số âm hay không
```javascript
function hasNegative(arr) {
    return arr.some(x => x < 0);
}

console.log(hasNegative([3, 1, 4, 2]));

```

###### Kết quả:

- A: `false` 
- B: `true`
- C: `undefined`
- D: `null`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: A 

Giải thích:

- Không có số âm, some() trả về false.

</p>
</details>

---
---
###### 29. Tìm tổng các số nguyên trong một chuỗi
```javascript
function sumNumbers(str) {
    return str.match(/\d+/g).map(Number).reduce((a, b) => a + b);
}

console.log(sumNumbers("abc12def34ghi56"));
 
```

###### Kết quả:

- A: `102` 
- B: `12`
- C: `NaN`
- D: `10234`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: A

Giải thích:

match(/\d+/g) trả về ["12", "34", "56"], tổng là 12 + 34 + 56 = 102.

</p>
</details>

---
---
###### 30. Tìm từ dài nhất trong chuỗi
```javascript
function longestWord(str) {
    return str.split(" ").sort((a, b) => b.length - a.length)[0];
}

console.log(longestWord("I love programming"));

```

###### Kết quả:

- A: `"programming"` 
- B: `"love"`
- C: `"I"`
- D: `"programming love"`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: A

Giải thích:

- sort((a, b) => b.length - a.length) sắp xếp theo độ dài giảm dần, từ dài nhất đứng đầu.

</p>
</details>

---
---
###### 31. Tìm số lớn thứ ba trong mảng
```javascript
function thirdLargest(arr) {
    let uniqueSorted = [...new Set(arr)].sort((a, b) => b - a);
    return uniqueSorted[2];
}

console.log(thirdLargest([10, 20, 20, 30, 40, 50]));

```

###### Kết quả:

- A: `30` 
- B: `20`
- C: `40`
- D: `undefined`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: A 

Giải thích:

- Mảng sau khi loại trùng và sắp xếp: [50, 40, 30, 20, 10].
- Phần tử lớn thứ 3 là 30.

</p>
</details>

---
---
###### 32. Kiểm tra chuỗi có phải toàn chữ cái không
```javascript
function isAlphabet(str) {
    return /^[a-zA-Z]+$/.test(str);
}

console.log(isAlphabet("Hello123"));

```

###### Kết quả:

- A: `true` 
- B: `false`
- C: `undefined`
- D: `null`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: B 

Giải thích:

- Hello123 chứa số, nên kết quả là false.

</p>
</details>

---
---
###### 33. Tìm phần tử xuất hiện một lần trong mảng
```javascript
function findUnique(arr) {
    return arr.find(x => arr.indexOf(x) === arr.lastIndexOf(x));
}

console.log(findUnique([4, 5, 6, 4, 5]));

```

###### Kết quả:

- A: `6` 
- B: `5`
- C: `4`
- D: `undefined`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: A 

Giải thích:

- 4 và 5 xuất hiện nhiều lần, chỉ 6 là duy nhất.

</p>
</details>

---
---
###### 34. Xóa tất cả số chẵn khỏi mảng
```javascript
function removeEvens(arr) {
    return arr.filter(x => x % 2 !== 0);
}

console.log(removeEvens([1, 2, 3, 4, 5]));
 
```

###### Kết quả:

- A: `[1, 3, 5]` 
- B: `[2, 4]`
- C: `[1, 2, 3, 4, 5]`
- D: `undefined`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: 

Giải thích:

Chỉ giữ số lẻ [1, 3, 5].

</p>
</details>

---
---
###### 35.Tạo mảng gồm các số từ 1 đến N
```javascript
function createArray(n) {
    return Array.from({ length: n }, (_, i) => i + 1);
}

console.log(createArray(5));

```

###### Kết quả:

- A: `[1, 2, 3, 4, 5]` 
- B: `[0, 1, 2, 3, 4]`
- C: `[1, 1, 1, 1, 1]`
- D: `[5, 4, 3, 2, 1]`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer:  A

Giải thích:

- Array.from({ length: n }, (_, i) => i + 1) tạo [1, 2, 3, 4, 5].

</p>
</details>

---
---
###### 36. Tính tổng các số nguyên tố trong mảng

```javascript
function sumPrimes(arr) {
    function isPrime(n) {
        if (n < 2) return false;
        for (let i = 2; i < n; i++) {
            if (n % i === 0) return false;
        }
        return true;
    }
    return arr.filter(isPrime).reduce((a, b) => a + b, 0);
}

console.log(sumPrimes([2, 3, 4, 5, 6, 7]));

```

###### Kết quả:

- A: `17` 
- B: `25`
- C: `21`
- D: `NaN`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer:  A

Giải thích:

- Các số nguyên tố: [2, 3, 5, 7].
Tổng: 2 + 3 + 5 + 7 = 17.
</p>
</details>

---
---
###### 37. Tính tổng các số trong khoảng [a, b]
```javascript
function sumRange(a, b) {
    return Array.from({ length: b - a + 1 }, (_, i) => a + i).reduce((a, b) => a + b, 0);
}

console.log(sumRange(3, 7));

```

###### Kết quả:

- A: `25` 
- B: `18`
- C: `15`
- D: `20`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: A

Giải thích:

- Dãy số [3, 4, 5, 6, 7], tổng: 3 + 4 + 5 + 6 + 7 = 25.

</p>
</details>

---
---
###### 38. Loại bỏ phần tử trùng lặp trong mảng
```javascript
function removeDuplicates(arr) {
    return [...new Set(arr)];
}

console.log(removeDuplicates([1, 2, 2, 3, 4, 4, 5]));

```

###### Kết quả:

- A: `[1, 2, 3, 4, 5]` 
- B: `[1, 2, 2, 3, 4, 4, 5]`
- C: `[5, 4, 3, 2, 1]`
- D: `Error`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: A

Giải thích:

- new Set(arr) loại bỏ trùng lặp.
</p>
</details>

---
---
###### 39. Kiểm tra mảng có chứa số âm không
```javascript
function hasNegative(arr) {
    return arr.some(x => x < 0);
}

console.log(hasNegative([3, 1, 4, 2]));

```

###### Kết quả:

- A: `false` 
- B: `true`
- C: `undefined`
- D: `null`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer:  A

Giải thích:

- Không có số âm, some() trả về false.

</p>
</details>

---
---
###### 40.  Đảo ngược số nguyên
```javascript
function reverseNumber(n) {
    return parseInt(n.toString().split("").reverse().join());
}

console.log(reverseNumber(1234));

```

###### Kết quả:

- A: `4321` 
- B: `"4321"`
- C: `NaN`
- D: `Error`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: C 

Giải thích:

- .join() thiếu (""), khiến nó trả về NaN.

</p>
</details>

---
---
###### 41. Lọc số chẵn từ mảng
```javascript
function filterEven(arr) {
    return arr.filter(x => x % 2 === 0);
}

console.log(filterEven([1, 2, 3, 4, 5, 6]));

```

###### Kết quả:

- A: `[2, 4, 6]` 
- B: `[1, 3, 5]`
- C: `[1, 2, 3, 4, 5, 6]`
- D: `undefined`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: 

Giai thich :
- filter() giữ lại số chẵn.
</p>
</details>

---
---
###### 42. Tìm số lớn nhất trong mảng
```javascript
function findMax(arr) {
    return Math.max(...arr);
}

console.log(findMax([10, 20, 5, 8, 25]));

```

###### Kết quả:

- A: `25` 
- B: `20`
- C: `10`
- D: `5`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: A 

Giai thich :
- Math.max(...arr) tìm số lớn nhất.

</p>
</details>

---
---
###### 43. Tìm phần tử xuất hiện nhiều nhất trong mảng
```javascript
function mostFrequent(arr) {
    let freqMap = {};
    let maxCount = 0;
    let maxItem = null;

    for (let num of arr) {
        freqMap[num] = (freqMap[num] || 0) + 1;
        if (freqMap[num] > maxCount) {
            maxCount = freqMap[num];
            maxItem = num;
        }
    }
    return maxItem;
}

console.log(mostFrequent([1, 3, 2, 3, 4, 3]));

```

###### Kết quả:

- A: `3` 
- B: `1`
- C: `2`
- D: `4`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer:  A 

Giải thích:

- 3 xuất hiện nhiều nhất (3 lần).

</p>
</details>

---
---
###### 44. Tạo mảng gồm các số từ 1 đến N
```javascript
function createArray(n) {
    return Array.from({ length: n }, (_, i) => i + 1);
}

console.log(createArray(5));
 
```

###### Kết quả: 

- A: `[1, 2, 3, 4, 5]` 
- B: `[0, 1, 2, 3, 4]`
- C: `[1, 1, 1, 1, 1]`
- D: `[5, 4, 3, 2, 1]`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: A 

Giải thích:

Array.from({ length: n }, (_, i) => i + 1) tạo [1, 2, 3, 4, 5].
</p>
</details>

---
---
###### 45. Tìm từ dài nhất trong chuỗi
```javascript
function longestWord(str) {
    return str.split(" ").sort((a, b) => b.length - a.length)[0];
}

console.log(longestWord("I love programming"));
 
```

###### Kết quả:

- A: `"programming"` 
- B: `"love"`
- C: `"I"`
- D: `"programming love"`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: A

Giải thích:

- sort((a, b) => b.length - a.length) sắp xếp theo độ dài giảm dần, từ dài nhất đứng đầu.

</p>
</details>

---
---
###### 46. Tìm số lẻ lớn nhất trong mảng
```javascript
function largestOdd(arr) {
    return Math.max(...arr.filter(x => x % 2 === 1));
}

console.log(largestOdd([2, 4, 6, 8]));
 
```

###### Kết quả:

- A: `-Infinity` 
- B: `undefined`
- C: `NaN`
- D: `Error`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: A 

Giải thích:

- Math.max() trên mảng rỗng trả về -Infinity.
</p>
</details>

---
---
###### 47. Đảo ngược một chuỗi mà không dùng .reverse()
```javascript
function reverseString(str) {
    let reversed = "";
    for (let i = str.length - 1; i >= 0; i--) {
        reversed += str[i];
    }
    return reversed;
}

console.log(reverseString("hello"));
 
```

###### Kết quả:

- A: `"olleh"` 
- B: `"hello"`
- C: `undefined`
- D: `"h e l l o"`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: A

Giải thích:

- Duyệt từ cuối về đầu và cộng dồn từng ký tự để tạo chuỗi đảo ngược.

</p>
</details>

---
---
###### 48. Tính tổng các số dương trong mảng
```javascript
function sumPositive(arr) {
    return arr.filter(x => x > 0).reduce((a, b) => a + b, 0);
}

console.log(sumPositive([-1, 2, -3, 4, 5]));
 
```

###### Kết quả:

- A: `11` 
- B: `5`
- C: `6`
- D: `NaN`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: A

Giải thích:

Các số dương: [2, 4, 5], tổng là 2 + 4 + 5 = 11.

</p>
</details>

---
---
###### 49. Đếm số từ trong chuỗi
```javascript
function countWords(str) {
    return str.split(" ").filter(word => word.length > 0).length;
}

console.log(countWords("  Hello   world  "));

```

###### Kết quả:

- A: `2` 
- B: `3`
- C: `4`
- D: `5`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: A 

Giải thích:

- Bỏ khoảng trắng dư thừa, chỉ có "Hello" và "world".

</p>
</details>

---
---
###### 50. Tạo chuỗi chữ cái viết hoa từ 'A' đến 'Z'
```javascript
function alphabet() {
    return Array.from({ length: 26 }, (_, i) => String.fromCharCode(65 + i)).join("");
}

console.log(alphabet());

```

###### Kết quả:

- A: `"ABCDEFGHIJKLMNOPQRSTUVWXYZ"` 
- B: `"abcdefghijklmnopqrstuvwxyz"`
- C: `"[A, B, C, ..., Z]"`
- D: `Error`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: A 

Giải thích:

- String.fromCharCode(65 + i) lấy mã ASCII của ký tự in hoa.

</p>
</details>

---
---
###### 51. Tìm số nhỏ nhất trong mảng
```javascript
function findMin(arr) {
    return Math.min(...arr);
}

console.log(findMin([10, 5, 8, 1, 6]));

```

###### Kết quả:

- A: `1` 
- B: `5`
- C: `10`
- D: `NaN`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: A 

Giải thích:

- Math.min(...arr) tìm số nhỏ nhất trong mảng.

</p>
</details>

---
---
###### 52. Xóa tất cả khoảng trắng thừa trong chuỗi
```javascript
function trimSpaces(str) {
    return str.replace(/\s+/g, " ").trim();
}

console.log(trimSpaces("   Hello   world   "));
 
```

###### Kết quả:

- A: `"Hello world"` 
- B: `" Hello world "`
- C: `"Hello world"`
- D: `"Helloworld"`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: A

Giải thích:

- replace(/\s+/g, " ") thay thế khoảng trắng dư thừa bằng một khoảng trắng.

</p>
</details>

---
---
###### 53. Tạo mảng chứa các số Fibonacci đầu tiên
```javascript
function fibonacci(n) {
    let arr = [0, 1];
    for (let i = 2; i < n; i++) {
        arr.push(arr[i - 1] + arr[i - 2]);
    }
    return arr;
}

console.log(fibonacci(6));

```

###### Kết quả:

- A: `[0, 1, 1, 2, 3, 5]` 
- B: `[1, 2, 3, 5, 8]`
- C: `[0, 1, 2, 3, 5, 8]`
- D: `[1, 1, 2, 3, 5]`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: A 

Giải thích:

- Fibonacci đầu tiên: [0, 1, 1, 2, 3, 5].
</p>
</details>

---
---
###### 54. Tìm ký tự xuất hiện nhiều nhất trong chuỗi
```javascript
function mostFrequentChar(str) {
    let freq = {};
    let maxCount = 0;
    let maxChar = '';

    for (let char of str) {
        freq[char] = (freq[char] || 0) + 1;
        if (freq[char] > maxCount) {
            maxCount = freq[char];
            maxChar = char;
        }
    }
    return maxChar;
}

console.log(mostFrequentChar("banana"));

```

###### Kết quả:

- A: `"a"` 
- B: `"b"`
- C: `"n"`
- D: `"Error"`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: A 

Giai thich :
- "a" xuất hiện nhiều nhất (3 lần).
  
</p>
</details>

---
---
###### 55. Tính tổng của các số chẵn trong mảng
```javascript
function sumEven(arr) {
    return arr.filter(x => x % 2 === 0).reduce((a, b) => a + b, 0);
}

console.log(sumEven([1, 2, 3, 4, 5, 6]));
 
```

###### Kết quả:

- A: `12` 
- B: `10`
- C: `6`
- D: `14`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: A

Giải thích:

- Số chẵn [2, 4, 6], tổng là 2 + 4 + 6 = 12.

</p>
</details>

---
---
###### 56. Tìm tất cả các hoán vị (permutations) của một mảng
```javascript
function getPermutations(arr) {
    if (arr.length === 0) return [[]];
    let first = arr[0];
    let rest = getPermutations(arr.slice(1));
    let result = [];
    for (let perm of rest) {
        for (let i = 0; i <= perm.length; i++) {
            result.push([...perm.slice(0, i), first, ...perm.slice(i)]);
        }
    }
    return result;
}

console.log(getPermutations([1, 2, 3]).length);

```

###### Kết quả:

- A: `6` 
- B: `3`
- C: `9`
- D: `5`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: A

Giai thich :
- Hoán vị của [1, 2, 3] là 3! = 6 tổ hợp.

</p>
</details>

---
---
###### 57.  Kiểm tra xem hai chuỗi có phải hoán vị của nhau không
```javascript
function areAnagrams(str1, str2) {
    return str1.split("").sort().join("") === str2.split("").sort().join("");
}

console.log(areAnagrams("listen", "silent"));

```

###### Kết quả:

- A: `true` 
- B: `false`
- C: `undefined`
- D: `null`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: A 

Giải thích:

- "listen" và "silent" có cùng chữ cái sắp xếp theo thứ tự.

</p>
</details>

---
---
###### 58. Tìm đường đi ngắn nhất trong ma trận (BFS)
```javascript
function shortestPath(grid) {
    let queue = [[0, 0, 0]];
    let visited = new Set(["0,0"]);
    let directions = [[0,1], [1,0], [0,-1], [-1,0]];
    
    while (queue.length) {
        let [x, y, steps] = queue.shift();
        if (x === grid.length - 1 && y === grid[0].length - 1) return steps;
        
        for (let [dx, dy] of directions) {
            let nx = x + dx, ny = y + dy;
            if (grid[nx] && grid[nx][ny] === 0 && !visited.has(`${nx},${ny}`)) {
                queue.push([nx, ny, steps + 1]);
                visited.add(`${nx},${ny}`);
            }
        }
    }
    return -1;
}

console.log(shortestPath([[0, 1], [0, 0]]));

```

###### Kết quả:

- A: `2` 
- B: `1`
- C: `-1`
- D: `3`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: A

Giai thich :
- Dùng BFS, đường đi ngắn nhất từ (0,0) đến (1,1) mất 2 bước.

</p>
</details>

---
---
###### 59. Tìm số xuất hiện nhiều nhất trong mảng có hàng triệu phần tử (O(n))
```javascript
function mostFrequent(arr) {
    let freq = {};
    let maxCount = 0;
    let maxNum = null;
    for (let num of arr) {
        freq[num] = (freq[num] || 0) + 1;
        if (freq[num] > maxCount) {
            maxCount = freq[num];
            maxNum = num;
        }
    }
    return maxNum;
}

console.log(mostFrequent([1, 3, 3, 3, 2, 1, 4]));

```

###### Kết quả:

- A: `3` 
- B: `1`
- C: `4`
- D: `2`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: A 

Giải thích:

- 3 xuất hiện 3 lần, nhiều nhất.

</p>
</details>

---
---
###### 60. Tính tổng lớn nhất của dãy con liên tiếp (Kadane’s Algorithm)
```javascript
function maxSubArray(arr) {
    let maxSum = arr[0];
    let currentSum = arr[0];
    for (let i = 1; i < arr.length; i++) {
        currentSum = Math.max(arr[i], currentSum + arr[i]);
        maxSum = Math.max(maxSum, currentSum);
    }
    return maxSum;
}

console.log(maxSubArray([-2, 1, -3, 4, -1, 2, 1, -5, 4]));
 
```

###### Kết quả:

- A: `6` 
- B: `4`
- C: `3`
- D: `1`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer:  

Giai thich :
- Dãy con [4, -1, 2, 1] có tổng lớn nhất là 6.

</p>
</details>

---
---
###### 61. Tìm cặp số có tổng bằng K (O(n))
``` javascript
function twoSum(arr, k) {
    let seen = new Set();
    for (let num of arr) {
        if (seen.has(k - num)) return true;
        seen.add(num);
    }
    return false;
}

console.log(twoSum([1, 2, 3, 4, 5], 8));

```

###### Kết quả:

- A: `true` 
- B: `false`
- C: `undefined`
- D: `null`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: A 

Giai thich :
- 3 + 5 = 8, nên trả về true.

</p>
</details>

---
---
###### 62. Kiểm tra số Fibonacci nhanh (O(1))
```javascript
function isFibonacci(n) {
    function isPerfectSquare(x) {
        return Number.isInteger(Math.sqrt(x));
    }
    return isPerfectSquare(5 * n * n + 4) || isPerfectSquare(5 * n * n - 4);
}

console.log(isFibonacci(13));

```

###### Kết quả:

- A: `true` 
- B: `false`
- C: `undefined`
- D: `null`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: A

Giai thich :
- 13 là số Fibonacci theo công thức 5*n^2 ± 4.

</p>
</details>

---
---
###### 63. Tìm số xuất hiện một lần trong mảng (Sử dụng XOR - O(n), O(1) không gian)
```javascript
function findUnique(arr) {
    return arr.reduce((a, b) => a ^ b, 0);
}

console.log(findUnique([1, 2, 3, 2, 1]));

```

###### Kết quả:

- A: `3` 
- B: `2`
- C: `1`
- D: `0`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: A 

Giải thích:

- XOR (^) của một số với chính nó là 0, và XOR với 0 giữ nguyên số đó.
(1 ^ 2 ^ 3 ^ 2 ^ 1) = 3 (các số trùng nhau bị triệt tiêu).

</p>
</details>

---
---
###### 64. Tìm phần tử "Majority" (Xuất hiện > n/2 lần)
```javascript
function majorityElement(arr) {
    let count = 0, candidate = null;
    for (let num of arr) {
        if (count === 0) candidate = num;
        count += (num === candidate) ? 1 : -1;
    }
    return candidate;
}

console.log(majorityElement([3, 3, 4, 2, 3, 3, 3]));

```

###### Kết quả:

- A: `3` 
- B: `4`
- C: `2`
- D: `undefined`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: A 

Giải thích:

- Thuật toán Boyer-Moore Voting Algorithm tìm số xuất hiện nhiều nhất (3).
</p>
</details>

---
---
###### 65. Đếm số đảo ngược trong mảng (Inversion Count - O(n log n))
```javascript
function countInversions(arr) {
    let count = 0;
    function mergeSort(arr) {
        if (arr.length < 2) return arr;
        let mid = Math.floor(arr.length / 2);
        let left = mergeSort(arr.slice(0, mid));
        let right = mergeSort(arr.slice(mid));
        return merge(left, right);
    }
    function merge(left, right) {
        let result = [], i = 0, j = 0;
        while (i < left.length && j < right.length) {
            if (left[i] <= right[j]) result.push(left[i++]);
            else {
                result.push(right[j++]);
                count += left.length - i;
            }
        }
        return [...result, ...left.slice(i), ...right.slice(j)];
    }
    mergeSort(arr);
    return count;
}

console.log(countInversions([2, 4, 1, 3, 5]));

```

###### Kết quả:

- A: `3` 
- B: `2`
- C: `4`
- D: `5`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: A

Giải thích:

- Các cặp đảo ngược (2,1), (4,1), (4,3) => 3.

</p>
</details>

---
---
###### 66. Tìm dãy con liên tiếp có tổng lớn nhất (Kadane's Algorithm - O(n))
```javascript
function maxSubArray(arr) {
    let maxSum = arr[0], currentSum = arr[0];
    for (let i = 1; i < arr.length; i++) {
        currentSum = Math.max(arr[i], currentSum + arr[i]);
        maxSum = Math.max(maxSum, currentSum);
    }
    return maxSum;
}

console.log(maxSubArray([-2, 1, -3, 4, -1, 2, 1, -5, 4]));

```

###### Kết quả:

- A: `6` 
- B: `4`
- C: `3`
- D: `1`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: A

Giai thich :
- Dãy [4, -1, 2, 1] có tổng lớn nhất là 6.

</p>
</details>

---
---
###### 67. Tìm đường đi ngắn nhất trong đồ thị có trọng số (Dijkstra’s Algorithm)
```javascript
function dijkstra(graph, start) {
    let distances = {}, visited = new Set();
    for (let node in graph) distances[node] = Infinity;
    distances[start] = 0;
    while (visited.size < Object.keys(graph).length) {
        let minNode = Object.keys(distances).filter(n => !visited.has(n)).reduce((a, b) => distances[a] < distances[b] ? a : b);
        visited.add(minNode);
        for (let neighbor in graph[minNode]) {
            let newDist = distances[minNode] + graph[minNode][neighbor];
            if (newDist < distances[neighbor]) distances[neighbor] = newDist;
        }
    }
    return distances;
}

console.log(dijkstra({
    A: { B: 4, C: 2 },
    B: { A: 4, C: 5, D: 10 },
    C: { A: 2, B: 5, D: 3 },
    D: { B: 10, C: 3 }
}, "A"));
 
```

###### Kết quả:

- A: `{ A: 0, B: 4, C: 2, D: 5 }` 
- B: `{ A: 0, B: 5, C: 2, D: 8 }`
- C: `{ A: 0, B: 3, C: 2, D: 6 }`
- D: `{ A: 0, B: 4, C: 2, D: 6 }`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: A

Giải thích:

- Khoảng cách ngắn nhất từ A:
- A → C (2),
- C → B (2 + 5 = 4),
- C → D (2 + 3 = 5).

</p>
</details>

---
---
###### 68. Kiểm tra một chuỗi có thể trở thành palindrome không? (O(n))
```javascript
function canBePalindrome(s) {
    let freq = {};
    for (let char of s) freq[char] = (freq[char] || 0) + 1;
    return Object.values(freq).filter(x => x % 2 !== 0).length <= 1;
}

console.log(canBePalindrome("racecar"));

```

###### Kết quả:

- A: `true` 
- B: `false`
- C: `undefined`
- D: `null`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: A

Giai thich :

- "racecar" có thể đảo lại thành chính nó (chỉ có 1 ký tự lẻ "e").
- Chỉ chuỗi có tối đa 1 ký tự xuất hiện lẻ lần có thể thành palindrome.

</p>
</details>

---
---
###### 69.  Tìm "kth" phần tử nhỏ nhất trong mảng (Quickselect - O(n))
```javascript
function quickSelect(arr, k) {
    if (arr.length === 1) return arr[0];
    let pivot = arr[arr.length - 1];
    let left = arr.filter(x => x < pivot);
    let right = arr.filter(x => x > pivot);
    if (k <= left.length) return quickSelect(left, k);
    if (k > arr.length - right.length) return quickSelect(right, k - (arr.length - right.length));
    return pivot;
}

console.log(quickSelect([7, 10, 4, 3, 20, 15], 3));

```

###### Kết quả:

- A: `7` 
- B: `10`
- C: `4`
- D: `15`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: A

Giai thich :
- Mảng sau khi sắp xếp: [3, 4, 7, 10, 15, 20].

- Phần tử thứ 3 nhỏ nhất là 7.

</p>
</details>

---
---
###### 70. Tìm dãy con tăng dài nhất (LIS - O(n log n))
```javascript
function longestIncreasingSubsequence(arr) {
    let dp = [];
    for (let num of arr) {
        let idx = dp.findIndex(x => x >= num);
        if (idx === -1) dp.push(num);
        else dp[idx] = num;
    }
    return dp.length;
}

console.log(longestIncreasingSubsequence([10, 9, 2, 5, 3, 7, 101, 18]));

```

###### Kết quả:

- A: `4` 
- B: `5`
- C: `6`
- D: `7`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: A 

Giai thich :
- Dãy con tăng dài nhất: [2, 3, 7, 18].

</p>
</details>

---
---
###### 71. Đếm số đường đi trong lưới NxM (Dynamic Programming - O(N*M))
```javascript
function uniquePaths(n, m) {
    let dp = Array(n).fill(0).map(() => Array(m).fill(1));
    for (let i = 1; i < n; i++)
        for (let j = 1; j < m; j++)
            dp[i][j] = dp[i - 1][j] + dp[i][j - 1];
    return dp[n - 1][m - 1];
}

console.log(uniquePaths(3, 3));

```

###### Kết quả:

- A: `6` 
- B: `3`
- C: `9`
- D: `12`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: A

Giai thich :
- Ma trận 3x3 có 6 cách đi từ (0,0) đến (2,2).

</p>
</details>

---
---
###### 72. Tìm số đảo ngược nhưng giữ dấu
```javascript
function reverseNumber(n) {
    let sign = n < 0 ? -1 : 1;
    let rev = parseInt(n.toString().split("").reverse().join("")) * sign;
    return rev;
}

console.log(reverseNumber(-123));

```

###### Kết quả:

- A: `-321` 
- B: `321`
- C: `-231`
- D: `null`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: C 

Giai thich :
- -123 đảo thành -321.

</p>
</details>

---
---
###### 73. Kiểm tra hai chuỗi có cùng ký tự (Anagram - O(n))

```javascript
function areAnagrams(str1, str2) {
    return str1.split("").sort().join("") === str2.split("").sort().join("");
}

console.log(areAnagrams("listen", "silent"));

```

###### Kết quả:

- A: `true` 
- B: `false`
- C: `undefined`
- D: `null`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: A 

Giai thich :
- "listen" và "silent" có cùng ký tự nhưng thứ tự khác nhau.

</p>
</details>

---
---
###### 74. Xóa phần tử trùng lặp trong mảng nhưng giữ thứ tự
```javascript
function removeDuplicates(arr) {
    return arr.filter((x, i) => arr.indexOf(x) === i);
}

console.log(removeDuplicates([1, 2, 2, 3, 4, 4, 5]));

```

###### Kết quả:

- A: `[1, 2, 3, 4, 5]` 
- B: `[1, 2, 2, 3, 4, 4, 5]`
- C: `[5, 4, 3, 2, 1]`
- D: `Error`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: A 

Giai thich :
- filter() giữ lại phần tử đầu tiên của mỗi số duy nhất.

</p>
</details>

---
---
###### 75. Kiểm tra chuỗi có chứa số
```javascript
function hasNumber(str) {
    return /\d/.test(str);
}

console.log(hasNumber("hello123"));

```

###### Kết quả:

- A: `true` 
- B: `false`
- C: `undefined`
- D: `null`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: A 

Giai thich :
- Biểu thức /\d/ kiểm tra xem chuỗi có chứa số (0-9) hay không.

</p>
</details>

---
---
###### 76. Đảo ngược từng từ trong chuỗi
```javascript
function reverseWords(str) {
    return str.split(" ").map(word => word.split("").reverse().join("")).join(" ");
}

console.log(reverseWords("hello world"));

```

###### Kết quả:

- A: `"olleh dlrow"` 
- B: `"world hello"`
- C: `"hello world"`
- D: `"dlrow olleh"`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: A 

Giai thich :
- hello → olleh, world → dlrow.

</p>
</details>

---
---
###### 77. Tính tổng các số trong chuỗi
```javascript
function sumNumbers(str) {
    return (str.match(/\d+/g) || []).map(Number).reduce((a, b) => a + b, 0);
}

console.log(sumNumbers("abc12def34ghi56"));

```

###### Kết quả:

- A: `102` 
- B: `12`
- C: `NaN`
- D: `10234`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: A 

Giai thich :
- 12 + 34 + 56 = 102.

</p>
</details>

---
---
###### 1. Tìm số lớn nhất có thể tạo từ các số trong mảng
```javascript
function largestNumber(arr) {
    return arr.map(String).sort((a, b) => (b + a) - (a + b)).join("").replace(/^0+/, "0");
}

console.log(largestNumber([3, 30, 34, 5, 9]));

```

###### Kết quả:

- A: `"9534330"` 
- B: `"953430"`
- C: `"343095"`
- D: `"303495"`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: A 

Giai thich :
- Dãy số sắp xếp theo quy tắc: "9" + "5", "5" + "34", "34" + "3", "3" + "30".
  
</p>
</details>

---
---
###### 1.  Kiểm tra hai chuỗi có cùng ký tự nhưng khác thứ tự (Anagram - O(n))
```javascript
function isAnagram(str1, str2) {
    if (str1.length !== str2.length) return false;
    let count = {};
    for (let char of str1) count[char] = (count[char] || 0) + 1;
    for (let char of str2) if (!count[char]) return false; else count[char]--;
    return true;
}

console.log(isAnagram("listen", "silent"));

```

###### Kết quả:

- A: `true` 
- B: `false`
- C: `undefined`
- D: `null`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: A

Giai thich :
- "listen" và "silent" có cùng ký tự nhưng thứ tự khác nhau.

</p>
</details>

---
---
###### 1. Tìm tất cả các dãy con có tổng bằng k
```javascript
function subarraySum(arr, k) {
    let count = 0, sum = 0, map = { 0: 1 };
    for (let num of arr) {
        sum += num;
        if (map[sum - k]) count += map[sum - k];
        map[sum] = (map[sum] || 0) + 1;
    }
    return count;
}

console.log(subarraySum([1, 1, 1], 2));

```

###### Kết quả:

- A: `2` 
- B: `3`
- C: `4`
- D: `5`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: B 

Giai thich :

- Dãy con [1,1] xuất hiện 2 lần với tổng 2.

</p>
</details>

---
---
###### 1. Tìm phần tử lặp đầu tiên trong mảng
```javascript
function firstDuplicate(arr) {
    let seen = new Set();
    for (let num of arr) {
        if (seen.has(num)) return num;
        seen.add(num);
    }
    return -1;
}

console.log(firstDuplicate([2, 1, 3, 5, 3, 2]));

```

###### Kết quả:

- A: `3` 
- B: `2`
- C: `1`
- D: `-1`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: A 

Giai thich :
- 3 xuất hiện trước 2 khi duyệt từ trái sang phải.
</p>
</details>

---
---
###### 1.  Tìm "kth" phần tử lớn nhất trong mảng
```javascript
function kthLargest(arr, k) {
    return arr.sort((a, b) => b - a)[k - 1];
}

console.log(kthLargest([3, 2, 1, 5, 6, 4], 2));
 
```

###### Kết quả:

- A: `5` 
- B: `6`
- C: `4`
- D: `3`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: A 

Giai thich :
- Mảng sau khi sắp xếp giảm dần: [6, 5, 4, 3, 2, 1].
- Phần tử lớn thứ 2 là 5.

</p>
</details>

---
---
###### 1. Tìm số xuất hiện lẻ lần (XOR - O(n))
```javascript
function findOdd(arr) {
    return arr.reduce((a, b) => a ^ b, 0);
}

console.log(findOdd([1, 2, 3, 2, 3, 1, 3]));

```

###### Kết quả:

- A: `3` 
- B: `1`
- C: `2`
- D: `0`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: A

Giai thich :
- XOR giữa các số giống nhau là 0, nên chỉ số xuất hiện lẻ lần còn lại.
  
</p>
</details>

---
---
###### 1. Tính số đường đi trong lưới NxM
```javascript
function uniquePaths(n, m) {
    let dp = Array(n).fill(0).map(() => Array(m).fill(1));
    for (let i = 1; i < n; i++)
        for (let j = 1; j < m; j++)
            dp[i][j] = dp[i - 1][j] + dp[i][j - 1];
    return dp[n - 1][m - 1];
}

console.log(uniquePaths(3, 3));

```

###### Kết quả:

- A: `6` 
- B: `3`
- C: `9`
- D: `12`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: A

Giai thich :
- Ma trận 3x3 có 6 cách đi từ (0,0) đến (2,2).

</p>
</details>

---
---
###### 1. Đảo ngược từng từ trong chuỗi
```javascript
function reverseWords(str) {
    return str.split(" ").map(word => word.split("").reverse().join("")).join(" ");
}

console.log(reverseWords("hello world"));

```

###### Kết quả:

- A: `"olleh dlrow"` 
- B: `"world hello"`
- C: `"hello world"`
- D: "dlrow olleh"`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: A

Giai thich :
- hello → olleh, world → dlrow.

</p>
</details>

---
---
###### 1. Tìm phần tử có tần suất cao nhất
```javascript
function mostFrequent(arr) {
    let map = {}, maxCount = 0, maxNum;
    for (let num of arr) {
        map[num] = (map[num] || 0) + 1;
        if (map[num] > maxCount) {
            maxCount = map[num];
            maxNum = num;
        }
    }
    return maxNum;
}

console.log(mostFrequent([1, 3, 3, 2, 1, 3]));
 
```

###### Kết quả:

- A: `3` 
- B: `1`
- C: `2`
- D: `undefined`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: A 

Giai thich :
- 3 xuất hiện 3 lần, nhiều nhất.

</p>
</details>

---
---
###### 1. Tính Tổng Của Mảng // Tính tổng tất cả các phần tử trong một mảng
```javascript
function sumArray(code) { 
    let sum = 5; 
    for (let i = 5; i < code.length; i++) { 
        sum += code[i];
        sum -= code[i];
    }
    return sum;
}

console.log(sumArray([1,2,3,4])); 
```

###### Kết quả:

- A: `5` 
- B: `10`
- C: `5` and `undefined`
- D: `undefined`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: C 

Giai thich :
- Vòng lặp for:
  
Bắt đầu vòng lặp từ , nhưng mảng chỉ có 4 phần tử (index từ 0 đến 3).
Điều kiện sẽ không bao giờ thỏa mãn (vì là 4).i = 5[1, 2, 3, 4]i < code.lengthcode.length
Kết quả là vòng lặp sẽ không bao giờ được thực thi.

- Cập nhật sum trong vòng lặp:
  
Trong vòng lặp, thực hiện cả hai phép cộng và trừ cùng một giá trị .
Điều có nghĩa là mỗi lần vòng lặp chạy, giá trị của sẽ không thay đổi trong suốt vòng lặp.code[i]sum
```javascript
sum += code[i]; // Thêm code[i] vào sum
sum -= code[i]; // Sau đó trừ code[i] ra khỏi sum
```
- Kết quả của chương trình:
  
Do vòng lặp không chạy, giá trị của vẫn giữ nguyên giá trị ban đầu, và chương trình sẽ trả về .sum 5

</p>
</details>

---
---
###### 1. Tính Tổng Của Mảng // Tính tổng tất cả các phần tử trong một mảng
```javascript
function sumArray(code) { 
    let sum = 5; 
    for (let i = 5; i < code.length; i++) { 
        sum += code[i];
        sum -= code[i];
    }
    return sum;
}

console.log(sumArray([1,2,3,4])); 
```

###### Kết quả:

- A: `5` 
- B: `10`
- C: `5` and `undefined`
- D: `undefined`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: C 

Giai thich :
- Vòng lặp for:
  
Bắt đầu vòng lặp từ , nhưng mảng chỉ có 4 phần tử (index từ 0 đến 3).
Điều kiện sẽ không bao giờ thỏa mãn (vì là 4).i = 5[1, 2, 3, 4]i < code.lengthcode.length
Kết quả là vòng lặp sẽ không bao giờ được thực thi.

- Cập nhật sum trong vòng lặp:
  
Trong vòng lặp, thực hiện cả hai phép cộng và trừ cùng một giá trị .
Điều có nghĩa là mỗi lần vòng lặp chạy, giá trị của sẽ không thay đổi trong suốt vòng lặp.code[i]sum
```javascript
sum += code[i]; // Thêm code[i] vào sum
sum -= code[i]; // Sau đó trừ code[i] ra khỏi sum
```
- Kết quả của chương trình:
  
Do vòng lặp không chạy, giá trị của vẫn giữ nguyên giá trị ban đầu, và chương trình sẽ trả về .sum 5

</p>
</details>

---
---
###### 1. Tính Tổng Của Mảng // Tính tổng tất cả các phần tử trong một mảng
```javascript
function sumArray(code) { 
    let sum = 5; 
    for (let i = 5; i < code.length; i++) { 
        sum += code[i];
        sum -= code[i];
    }
    return sum;
}

console.log(sumArray([1,2,3,4])); 
```

###### Kết quả:

- A: `5` 
- B: `10`
- C: `5` and `undefined`
- D: `undefined`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: C 

Giai thich :
- Vòng lặp for:
  
Bắt đầu vòng lặp từ , nhưng mảng chỉ có 4 phần tử (index từ 0 đến 3).
Điều kiện sẽ không bao giờ thỏa mãn (vì là 4).i = 5[1, 2, 3, 4]i < code.lengthcode.length
Kết quả là vòng lặp sẽ không bao giờ được thực thi.

- Cập nhật sum trong vòng lặp:
  
Trong vòng lặp, thực hiện cả hai phép cộng và trừ cùng một giá trị .
Điều có nghĩa là mỗi lần vòng lặp chạy, giá trị của sẽ không thay đổi trong suốt vòng lặp.code[i]sum
```javascript
sum += code[i]; // Thêm code[i] vào sum
sum -= code[i]; // Sau đó trừ code[i] ra khỏi sum
```
- Kết quả của chương trình:
  
Do vòng lặp không chạy, giá trị của vẫn giữ nguyên giá trị ban đầu, và chương trình sẽ trả về .sum 5

</p>
</details>

---
---
###### 1. Tính Tổng Của Mảng // Tính tổng tất cả các phần tử trong một mảng
```javascript
function sumArray(code) { 
    let sum = 5; 
    for (let i = 5; i < code.length; i++) { 
        sum += code[i];
        sum -= code[i];
    }
    return sum;
}

console.log(sumArray([1,2,3,4])); 
```

###### Kết quả:

- A: `5` 
- B: `10`
- C: `5` and `undefined`
- D: `undefined`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: C 

Giai thich :
- Vòng lặp for:
  
Bắt đầu vòng lặp từ , nhưng mảng chỉ có 4 phần tử (index từ 0 đến 3).
Điều kiện sẽ không bao giờ thỏa mãn (vì là 4).i = 5[1, 2, 3, 4]i < code.lengthcode.length
Kết quả là vòng lặp sẽ không bao giờ được thực thi.

- Cập nhật sum trong vòng lặp:
  
Trong vòng lặp, thực hiện cả hai phép cộng và trừ cùng một giá trị .
Điều có nghĩa là mỗi lần vòng lặp chạy, giá trị của sẽ không thay đổi trong suốt vòng lặp.code[i]sum
```javascript
sum += code[i]; // Thêm code[i] vào sum
sum -= code[i]; // Sau đó trừ code[i] ra khỏi sum
```
- Kết quả của chương trình:
  
Do vòng lặp không chạy, giá trị của vẫn giữ nguyên giá trị ban đầu, và chương trình sẽ trả về .sum 5

</p>
</details>

---
---
###### 1. Tính Tổng Của Mảng // Tính tổng tất cả các phần tử trong một mảng
```javascript
function sumArray(code) { 
    let sum = 5; 
    for (let i = 5; i < code.length; i++) { 
        sum += code[i];
        sum -= code[i];
    }
    return sum;
}

console.log(sumArray([1,2,3,4])); 
```

###### Kết quả:

- A: `5` 
- B: `10`
- C: `5` and `undefined`
- D: `undefined`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: C 

Giai thich :
- Vòng lặp for:
  
Bắt đầu vòng lặp từ , nhưng mảng chỉ có 4 phần tử (index từ 0 đến 3).
Điều kiện sẽ không bao giờ thỏa mãn (vì là 4).i = 5[1, 2, 3, 4]i < code.lengthcode.length
Kết quả là vòng lặp sẽ không bao giờ được thực thi.

- Cập nhật sum trong vòng lặp:
  
Trong vòng lặp, thực hiện cả hai phép cộng và trừ cùng một giá trị .
Điều có nghĩa là mỗi lần vòng lặp chạy, giá trị của sẽ không thay đổi trong suốt vòng lặp.code[i]sum
```javascript
sum += code[i]; // Thêm code[i] vào sum
sum -= code[i]; // Sau đó trừ code[i] ra khỏi sum
```
- Kết quả của chương trình:
  
Do vòng lặp không chạy, giá trị của vẫn giữ nguyên giá trị ban đầu, và chương trình sẽ trả về .sum 5

</p>
</details>

---
---
###### 1. Tính Tổng Của Mảng // Tính tổng tất cả các phần tử trong một mảng
```javascript
function sumArray(code) { 
    let sum = 5; 
    for (let i = 5; i < code.length; i++) { 
        sum += code[i];
        sum -= code[i];
    }
    return sum;
}

console.log(sumArray([1,2,3,4])); 
```

###### Kết quả:

- A: `5` 
- B: `10`
- C: `5` and `undefined`
- D: `undefined`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: C 

Giai thich :
- Vòng lặp for:
  
Bắt đầu vòng lặp từ , nhưng mảng chỉ có 4 phần tử (index từ 0 đến 3).
Điều kiện sẽ không bao giờ thỏa mãn (vì là 4).i = 5[1, 2, 3, 4]i < code.lengthcode.length
Kết quả là vòng lặp sẽ không bao giờ được thực thi.

- Cập nhật sum trong vòng lặp:
  
Trong vòng lặp, thực hiện cả hai phép cộng và trừ cùng một giá trị .
Điều có nghĩa là mỗi lần vòng lặp chạy, giá trị của sẽ không thay đổi trong suốt vòng lặp.code[i]sum
```javascript
sum += code[i]; // Thêm code[i] vào sum
sum -= code[i]; // Sau đó trừ code[i] ra khỏi sum
```
- Kết quả của chương trình:
  
Do vòng lặp không chạy, giá trị của vẫn giữ nguyên giá trị ban đầu, và chương trình sẽ trả về .sum 5

</p>
</details>

---
---
###### 1. Tính Tổng Của Mảng // Tính tổng tất cả các phần tử trong một mảng
```javascript
function sumArray(code) { 
    let sum = 5; 
    for (let i = 5; i < code.length; i++) { 
        sum += code[i];
        sum -= code[i];
    }
    return sum;
}

console.log(sumArray([1,2,3,4])); 
```

###### Kết quả:

- A: `5` 
- B: `10`
- C: `5` and `undefined`
- D: `undefined`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: C 

Giai thich :
- Vòng lặp for:
  
Bắt đầu vòng lặp từ , nhưng mảng chỉ có 4 phần tử (index từ 0 đến 3).
Điều kiện sẽ không bao giờ thỏa mãn (vì là 4).i = 5[1, 2, 3, 4]i < code.lengthcode.length
Kết quả là vòng lặp sẽ không bao giờ được thực thi.

- Cập nhật sum trong vòng lặp:
  
Trong vòng lặp, thực hiện cả hai phép cộng và trừ cùng một giá trị .
Điều có nghĩa là mỗi lần vòng lặp chạy, giá trị của sẽ không thay đổi trong suốt vòng lặp.code[i]sum
```javascript
sum += code[i]; // Thêm code[i] vào sum
sum -= code[i]; // Sau đó trừ code[i] ra khỏi sum
```
- Kết quả của chương trình:
  
Do vòng lặp không chạy, giá trị của vẫn giữ nguyên giá trị ban đầu, và chương trình sẽ trả về .sum 5

</p>
</details>

---
---
###### 1. Tính Tổng Của Mảng // Tính tổng tất cả các phần tử trong một mảng
```javascript
function sumArray(code) { 
    let sum = 5; 
    for (let i = 5; i < code.length; i++) { 
        sum += code[i];
        sum -= code[i];
    }
    return sum;
}

console.log(sumArray([1,2,3,4])); 
```

###### Kết quả:

- A: `5` 
- B: `10`
- C: `5` and `undefined`
- D: `undefined`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: C 

Giai thich :
- Vòng lặp for:
  
Bắt đầu vòng lặp từ , nhưng mảng chỉ có 4 phần tử (index từ 0 đến 3).
Điều kiện sẽ không bao giờ thỏa mãn (vì là 4).i = 5[1, 2, 3, 4]i < code.lengthcode.length
Kết quả là vòng lặp sẽ không bao giờ được thực thi.

- Cập nhật sum trong vòng lặp:
  
Trong vòng lặp, thực hiện cả hai phép cộng và trừ cùng một giá trị .
Điều có nghĩa là mỗi lần vòng lặp chạy, giá trị của sẽ không thay đổi trong suốt vòng lặp.code[i]sum
```javascript
sum += code[i]; // Thêm code[i] vào sum
sum -= code[i]; // Sau đó trừ code[i] ra khỏi sum
```
- Kết quả của chương trình:
  
Do vòng lặp không chạy, giá trị của vẫn giữ nguyên giá trị ban đầu, và chương trình sẽ trả về .sum 5

</p>
</details>

---
---
###### 1. Tính Tổng Của Mảng // Tính tổng tất cả các phần tử trong một mảng
```javascript
function sumArray(code) { 
    let sum = 5; 
    for (let i = 5; i < code.length; i++) { 
        sum += code[i];
        sum -= code[i];
    }
    return sum;
}

console.log(sumArray([1,2,3,4])); 
```

###### Kết quả:

- A: `5` 
- B: `10`
- C: `5` and `undefined`
- D: `undefined`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: C 

Giai thich :
- Vòng lặp for:
  
Bắt đầu vòng lặp từ , nhưng mảng chỉ có 4 phần tử (index từ 0 đến 3).
Điều kiện sẽ không bao giờ thỏa mãn (vì là 4).i = 5[1, 2, 3, 4]i < code.lengthcode.length
Kết quả là vòng lặp sẽ không bao giờ được thực thi.

- Cập nhật sum trong vòng lặp:
  
Trong vòng lặp, thực hiện cả hai phép cộng và trừ cùng một giá trị .
Điều có nghĩa là mỗi lần vòng lặp chạy, giá trị của sẽ không thay đổi trong suốt vòng lặp.code[i]sum
```javascript
sum += code[i]; // Thêm code[i] vào sum
sum -= code[i]; // Sau đó trừ code[i] ra khỏi sum
```
- Kết quả của chương trình:
  
Do vòng lặp không chạy, giá trị của vẫn giữ nguyên giá trị ban đầu, và chương trình sẽ trả về .sum 5

</p>
</details>

---
---
###### 1. Tính Tổng Của Mảng // Tính tổng tất cả các phần tử trong một mảng
```javascript
function sumArray(code) { 
    let sum = 5; 
    for (let i = 5; i < code.length; i++) { 
        sum += code[i];
        sum -= code[i];
    }
    return sum;
}

console.log(sumArray([1,2,3,4])); 
```

###### Kết quả:

- A: `5` 
- B: `10`
- C: `5` and `undefined`
- D: `undefined`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: C 

Giai thich :
- Vòng lặp for:
  
Bắt đầu vòng lặp từ , nhưng mảng chỉ có 4 phần tử (index từ 0 đến 3).
Điều kiện sẽ không bao giờ thỏa mãn (vì là 4).i = 5[1, 2, 3, 4]i < code.lengthcode.length
Kết quả là vòng lặp sẽ không bao giờ được thực thi.

- Cập nhật sum trong vòng lặp:
  
Trong vòng lặp, thực hiện cả hai phép cộng và trừ cùng một giá trị .
Điều có nghĩa là mỗi lần vòng lặp chạy, giá trị của sẽ không thay đổi trong suốt vòng lặp.code[i]sum
```javascript
sum += code[i]; // Thêm code[i] vào sum
sum -= code[i]; // Sau đó trừ code[i] ra khỏi sum
```
- Kết quả của chương trình:
  
Do vòng lặp không chạy, giá trị của vẫn giữ nguyên giá trị ban đầu, và chương trình sẽ trả về .sum 5

</p>
</details>

---
---
###### 1. Tính Tổng Của Mảng // Tính tổng tất cả các phần tử trong một mảng
```javascript
function sumArray(code) { 
    let sum = 5; 
    for (let i = 5; i < code.length; i++) { 
        sum += code[i];
        sum -= code[i];
    }
    return sum;
}

console.log(sumArray([1,2,3,4])); 
```

###### Kết quả:

- A: `5` 
- B: `10`
- C: `5` and `undefined`
- D: `undefined`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: C 

Giai thich :
- Vòng lặp for:
  
Bắt đầu vòng lặp từ , nhưng mảng chỉ có 4 phần tử (index từ 0 đến 3).
Điều kiện sẽ không bao giờ thỏa mãn (vì là 4).i = 5[1, 2, 3, 4]i < code.lengthcode.length
Kết quả là vòng lặp sẽ không bao giờ được thực thi.

- Cập nhật sum trong vòng lặp:
  
Trong vòng lặp, thực hiện cả hai phép cộng và trừ cùng một giá trị .
Điều có nghĩa là mỗi lần vòng lặp chạy, giá trị của sẽ không thay đổi trong suốt vòng lặp.code[i]sum
```javascript
sum += code[i]; // Thêm code[i] vào sum
sum -= code[i]; // Sau đó trừ code[i] ra khỏi sum
```
- Kết quả của chương trình:
  
Do vòng lặp không chạy, giá trị của vẫn giữ nguyên giá trị ban đầu, và chương trình sẽ trả về .sum 5

</p>
</details>

---
---
###### 1. Tính Tổng Của Mảng // Tính tổng tất cả các phần tử trong một mảng
```javascript
function sumArray(code) { 
    let sum = 5; 
    for (let i = 5; i < code.length; i++) { 
        sum += code[i];
        sum -= code[i];
    }
    return sum;
}

console.log(sumArray([1,2,3,4])); 
```

###### Kết quả:

- A: `5` 
- B: `10`
- C: `5` and `undefined`
- D: `undefined`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: C 

Giai thich :
- Vòng lặp for:
  
Bắt đầu vòng lặp từ , nhưng mảng chỉ có 4 phần tử (index từ 0 đến 3).
Điều kiện sẽ không bao giờ thỏa mãn (vì là 4).i = 5[1, 2, 3, 4]i < code.lengthcode.length
Kết quả là vòng lặp sẽ không bao giờ được thực thi.

- Cập nhật sum trong vòng lặp:
  
Trong vòng lặp, thực hiện cả hai phép cộng và trừ cùng một giá trị .
Điều có nghĩa là mỗi lần vòng lặp chạy, giá trị của sẽ không thay đổi trong suốt vòng lặp.code[i]sum
```javascript
sum += code[i]; // Thêm code[i] vào sum
sum -= code[i]; // Sau đó trừ code[i] ra khỏi sum
```
- Kết quả của chương trình:
  
Do vòng lặp không chạy, giá trị của vẫn giữ nguyên giá trị ban đầu, và chương trình sẽ trả về .sum 5

</p>
</details>

---
---
###### 1. Tính Tổng Của Mảng // Tính tổng tất cả các phần tử trong một mảng
```javascript
function sumArray(code) { 
    let sum = 5; 
    for (let i = 5; i < code.length; i++) { 
        sum += code[i];
        sum -= code[i];
    }
    return sum;
}

console.log(sumArray([1,2,3,4])); 
```

###### Kết quả:

- A: `5` 
- B: `10`
- C: `5` and `undefined`
- D: `undefined`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: C 

Giai thich :
- Vòng lặp for:
  
Bắt đầu vòng lặp từ , nhưng mảng chỉ có 4 phần tử (index từ 0 đến 3).
Điều kiện sẽ không bao giờ thỏa mãn (vì là 4).i = 5[1, 2, 3, 4]i < code.lengthcode.length
Kết quả là vòng lặp sẽ không bao giờ được thực thi.

- Cập nhật sum trong vòng lặp:
  
Trong vòng lặp, thực hiện cả hai phép cộng và trừ cùng một giá trị .
Điều có nghĩa là mỗi lần vòng lặp chạy, giá trị của sẽ không thay đổi trong suốt vòng lặp.code[i]sum
```javascript
sum += code[i]; // Thêm code[i] vào sum
sum -= code[i]; // Sau đó trừ code[i] ra khỏi sum
```
- Kết quả của chương trình:
  
Do vòng lặp không chạy, giá trị của vẫn giữ nguyên giá trị ban đầu, và chương trình sẽ trả về .sum 5

</p>
</details>

---
---
###### 1. Tính Tổng Của Mảng // Tính tổng tất cả các phần tử trong một mảng
```javascript
function sumArray(code) { 
    let sum = 5; 
    for (let i = 5; i < code.length; i++) { 
        sum += code[i];
        sum -= code[i];
    }
    return sum;
}

console.log(sumArray([1,2,3,4])); 
```

###### Kết quả:

- A: `5` 
- B: `10`
- C: `5` and `undefined`
- D: `undefined`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: C 

Giai thich :
- Vòng lặp for:
  
Bắt đầu vòng lặp từ , nhưng mảng chỉ có 4 phần tử (index từ 0 đến 3).
Điều kiện sẽ không bao giờ thỏa mãn (vì là 4).i = 5[1, 2, 3, 4]i < code.lengthcode.length
Kết quả là vòng lặp sẽ không bao giờ được thực thi.

- Cập nhật sum trong vòng lặp:
  
Trong vòng lặp, thực hiện cả hai phép cộng và trừ cùng một giá trị .
Điều có nghĩa là mỗi lần vòng lặp chạy, giá trị của sẽ không thay đổi trong suốt vòng lặp.code[i]sum
```javascript
sum += code[i]; // Thêm code[i] vào sum
sum -= code[i]; // Sau đó trừ code[i] ra khỏi sum
```
- Kết quả của chương trình:
  
Do vòng lặp không chạy, giá trị của vẫn giữ nguyên giá trị ban đầu, và chương trình sẽ trả về .sum 5

</p>
</details>

---
---
###### 1. Tính Tổng Của Mảng // Tính tổng tất cả các phần tử trong một mảng
```javascript
function sumArray(code) { 
    let sum = 5; 
    for (let i = 5; i < code.length; i++) { 
        sum += code[i];
        sum -= code[i];
    }
    return sum;
}

console.log(sumArray([1,2,3,4])); 
```

###### Kết quả:

- A: `5` 
- B: `10`
- C: `5` and `undefined`
- D: `undefined`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: C 

Giai thich :
- Vòng lặp for:
  
Bắt đầu vòng lặp từ , nhưng mảng chỉ có 4 phần tử (index từ 0 đến 3).
Điều kiện sẽ không bao giờ thỏa mãn (vì là 4).i = 5[1, 2, 3, 4]i < code.lengthcode.length
Kết quả là vòng lặp sẽ không bao giờ được thực thi.

- Cập nhật sum trong vòng lặp:
  
Trong vòng lặp, thực hiện cả hai phép cộng và trừ cùng một giá trị .
Điều có nghĩa là mỗi lần vòng lặp chạy, giá trị của sẽ không thay đổi trong suốt vòng lặp.code[i]sum
```javascript
sum += code[i]; // Thêm code[i] vào sum
sum -= code[i]; // Sau đó trừ code[i] ra khỏi sum
```
- Kết quả của chương trình:
  
Do vòng lặp không chạy, giá trị của vẫn giữ nguyên giá trị ban đầu, và chương trình sẽ trả về .sum 5

</p>
</details>

---
---
###### 1. Tính Tổng Của Mảng // Tính tổng tất cả các phần tử trong một mảng
```javascript
function sumArray(code) { 
    let sum = 5; 
    for (let i = 5; i < code.length; i++) { 
        sum += code[i];
        sum -= code[i];
    }
    return sum;
}

console.log(sumArray([1,2,3,4])); 
```

###### Kết quả:

- A: `5` 
- B: `10`
- C: `5` and `undefined`
- D: `undefined`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: C 

Giai thich :
- Vòng lặp for:
  
Bắt đầu vòng lặp từ , nhưng mảng chỉ có 4 phần tử (index từ 0 đến 3).
Điều kiện sẽ không bao giờ thỏa mãn (vì là 4).i = 5[1, 2, 3, 4]i < code.lengthcode.length
Kết quả là vòng lặp sẽ không bao giờ được thực thi.

- Cập nhật sum trong vòng lặp:
  
Trong vòng lặp, thực hiện cả hai phép cộng và trừ cùng một giá trị .
Điều có nghĩa là mỗi lần vòng lặp chạy, giá trị của sẽ không thay đổi trong suốt vòng lặp.code[i]sum
```javascript
sum += code[i]; // Thêm code[i] vào sum
sum -= code[i]; // Sau đó trừ code[i] ra khỏi sum
```
- Kết quả của chương trình:
  
Do vòng lặp không chạy, giá trị của vẫn giữ nguyên giá trị ban đầu, và chương trình sẽ trả về .sum 5

</p>
</details>

---
---
###### 1. Tính Tổng Của Mảng // Tính tổng tất cả các phần tử trong một mảng
```javascript
function sumArray(code) { 
    let sum = 5; 
    for (let i = 5; i < code.length; i++) { 
        sum += code[i];
        sum -= code[i];
    }
    return sum;
}

console.log(sumArray([1,2,3,4])); 
```

###### Kết quả:

- A: `5` 
- B: `10`
- C: `5` and `undefined`
- D: `undefined`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: C 

Giai thich :
- Vòng lặp for:
  
Bắt đầu vòng lặp từ , nhưng mảng chỉ có 4 phần tử (index từ 0 đến 3).
Điều kiện sẽ không bao giờ thỏa mãn (vì là 4).i = 5[1, 2, 3, 4]i < code.lengthcode.length
Kết quả là vòng lặp sẽ không bao giờ được thực thi.

- Cập nhật sum trong vòng lặp:
  
Trong vòng lặp, thực hiện cả hai phép cộng và trừ cùng một giá trị .
Điều có nghĩa là mỗi lần vòng lặp chạy, giá trị của sẽ không thay đổi trong suốt vòng lặp.code[i]sum
```javascript
sum += code[i]; // Thêm code[i] vào sum
sum -= code[i]; // Sau đó trừ code[i] ra khỏi sum
```
- Kết quả của chương trình:
  
Do vòng lặp không chạy, giá trị của vẫn giữ nguyên giá trị ban đầu, và chương trình sẽ trả về .sum 5

</p>
</details>

---
---
###### 1. Tính Tổng Của Mảng // Tính tổng tất cả các phần tử trong một mảng
```javascript
function sumArray(code) { 
    let sum = 5; 
    for (let i = 5; i < code.length; i++) { 
        sum += code[i];
        sum -= code[i];
    }
    return sum;
}

console.log(sumArray([1,2,3,4])); 
```

###### Kết quả:

- A: `5` 
- B: `10`
- C: `5` and `undefined`
- D: `undefined`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: C 

Giai thich :
- Vòng lặp for:
  
Bắt đầu vòng lặp từ , nhưng mảng chỉ có 4 phần tử (index từ 0 đến 3).
Điều kiện sẽ không bao giờ thỏa mãn (vì là 4).i = 5[1, 2, 3, 4]i < code.lengthcode.length
Kết quả là vòng lặp sẽ không bao giờ được thực thi.

- Cập nhật sum trong vòng lặp:
  
Trong vòng lặp, thực hiện cả hai phép cộng và trừ cùng một giá trị .
Điều có nghĩa là mỗi lần vòng lặp chạy, giá trị của sẽ không thay đổi trong suốt vòng lặp.code[i]sum
```javascript
sum += code[i]; // Thêm code[i] vào sum
sum -= code[i]; // Sau đó trừ code[i] ra khỏi sum
```
- Kết quả của chương trình:
  
Do vòng lặp không chạy, giá trị của vẫn giữ nguyên giá trị ban đầu, và chương trình sẽ trả về .sum 5

</p>
</details>

---
---
###### 1. Tính Tổng Của Mảng // Tính tổng tất cả các phần tử trong một mảng
```javascript
function sumArray(code) { 
    let sum = 5; 
    for (let i = 5; i < code.length; i++) { 
        sum += code[i];
        sum -= code[i];
    }
    return sum;
}

console.log(sumArray([1,2,3,4])); 
```

###### Kết quả:

- A: `5` 
- B: `10`
- C: `5` and `undefined`
- D: `undefined`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: C 

Giai thich :
- Vòng lặp for:
  
Bắt đầu vòng lặp từ , nhưng mảng chỉ có 4 phần tử (index từ 0 đến 3).
Điều kiện sẽ không bao giờ thỏa mãn (vì là 4).i = 5[1, 2, 3, 4]i < code.lengthcode.length
Kết quả là vòng lặp sẽ không bao giờ được thực thi.

- Cập nhật sum trong vòng lặp:
  
Trong vòng lặp, thực hiện cả hai phép cộng và trừ cùng một giá trị .
Điều có nghĩa là mỗi lần vòng lặp chạy, giá trị của sẽ không thay đổi trong suốt vòng lặp.code[i]sum
```javascript
sum += code[i]; // Thêm code[i] vào sum
sum -= code[i]; // Sau đó trừ code[i] ra khỏi sum
```
- Kết quả của chương trình:
  
Do vòng lặp không chạy, giá trị của vẫn giữ nguyên giá trị ban đầu, và chương trình sẽ trả về .sum 5

</p>
</details>

---
---
###### 1. Tính Tổng Của Mảng // Tính tổng tất cả các phần tử trong một mảng
```javascript
function sumArray(code) { 
    let sum = 5; 
    for (let i = 5; i < code.length; i++) { 
        sum += code[i];
        sum -= code[i];
    }
    return sum;
}

console.log(sumArray([1,2,3,4])); 
```

###### Kết quả:

- A: `5` 
- B: `10`
- C: `5` and `undefined`
- D: `undefined`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: C 

Giai thich :
- Vòng lặp for:
  
Bắt đầu vòng lặp từ , nhưng mảng chỉ có 4 phần tử (index từ 0 đến 3).
Điều kiện sẽ không bao giờ thỏa mãn (vì là 4).i = 5[1, 2, 3, 4]i < code.lengthcode.length
Kết quả là vòng lặp sẽ không bao giờ được thực thi.

- Cập nhật sum trong vòng lặp:
  
Trong vòng lặp, thực hiện cả hai phép cộng và trừ cùng một giá trị .
Điều có nghĩa là mỗi lần vòng lặp chạy, giá trị của sẽ không thay đổi trong suốt vòng lặp.code[i]sum
```javascript
sum += code[i]; // Thêm code[i] vào sum
sum -= code[i]; // Sau đó trừ code[i] ra khỏi sum
```
- Kết quả của chương trình:
  
Do vòng lặp không chạy, giá trị của vẫn giữ nguyên giá trị ban đầu, và chương trình sẽ trả về .sum 5

</p>
</details>

---
---
###### 1. Tính Tổng Của Mảng // Tính tổng tất cả các phần tử trong một mảng
```javascript
function sumArray(code) { 
    let sum = 5; 
    for (let i = 5; i < code.length; i++) { 
        sum += code[i];
        sum -= code[i];
    }
    return sum;
}

console.log(sumArray([1,2,3,4])); 
```

###### Kết quả:

- A: `5` 
- B: `10`
- C: `5` and `undefined`
- D: `undefined`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: C 

Giai thich :
- Vòng lặp for:
  
Bắt đầu vòng lặp từ , nhưng mảng chỉ có 4 phần tử (index từ 0 đến 3).
Điều kiện sẽ không bao giờ thỏa mãn (vì là 4).i = 5[1, 2, 3, 4]i < code.lengthcode.length
Kết quả là vòng lặp sẽ không bao giờ được thực thi.

- Cập nhật sum trong vòng lặp:
  
Trong vòng lặp, thực hiện cả hai phép cộng và trừ cùng một giá trị .
Điều có nghĩa là mỗi lần vòng lặp chạy, giá trị của sẽ không thay đổi trong suốt vòng lặp.code[i]sum
```javascript
sum += code[i]; // Thêm code[i] vào sum
sum -= code[i]; // Sau đó trừ code[i] ra khỏi sum
```
- Kết quả của chương trình:
  
Do vòng lặp không chạy, giá trị của vẫn giữ nguyên giá trị ban đầu, và chương trình sẽ trả về .sum 5

</p>
</details>

---
---
###### 1. Tính Tổng Của Mảng // Tính tổng tất cả các phần tử trong một mảng
```javascript
function sumArray(code) { 
    let sum = 5; 
    for (let i = 5; i < code.length; i++) { 
        sum += code[i];
        sum -= code[i];
    }
    return sum;
}

console.log(sumArray([1,2,3,4])); 
```

###### Kết quả:

- A: `5` 
- B: `10`
- C: `5` and `undefined`
- D: `undefined`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: C 

Giai thich :
- Vòng lặp for:
  
Bắt đầu vòng lặp từ , nhưng mảng chỉ có 4 phần tử (index từ 0 đến 3).
Điều kiện sẽ không bao giờ thỏa mãn (vì là 4).i = 5[1, 2, 3, 4]i < code.lengthcode.length
Kết quả là vòng lặp sẽ không bao giờ được thực thi.

- Cập nhật sum trong vòng lặp:
  
Trong vòng lặp, thực hiện cả hai phép cộng và trừ cùng một giá trị .
Điều có nghĩa là mỗi lần vòng lặp chạy, giá trị của sẽ không thay đổi trong suốt vòng lặp.code[i]sum
```javascript
sum += code[i]; // Thêm code[i] vào sum
sum -= code[i]; // Sau đó trừ code[i] ra khỏi sum
```
- Kết quả của chương trình:
  
Do vòng lặp không chạy, giá trị của vẫn giữ nguyên giá trị ban đầu, và chương trình sẽ trả về .sum 5

</p>
</details>

---
---
###### 1. Tính Tổng Của Mảng // Tính tổng tất cả các phần tử trong một mảng
```javascript
function sumArray(code) { 
    let sum = 5; 
    for (let i = 5; i < code.length; i++) { 
        sum += code[i];
        sum -= code[i];
    }
    return sum;
}

console.log(sumArray([1,2,3,4])); 
```

###### Kết quả:

- A: `5` 
- B: `10`
- C: `5` and `undefined`
- D: `undefined`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: C 

Giai thich :
- Vòng lặp for:
  
Bắt đầu vòng lặp từ , nhưng mảng chỉ có 4 phần tử (index từ 0 đến 3).
Điều kiện sẽ không bao giờ thỏa mãn (vì là 4).i = 5[1, 2, 3, 4]i < code.lengthcode.length
Kết quả là vòng lặp sẽ không bao giờ được thực thi.

- Cập nhật sum trong vòng lặp:
  
Trong vòng lặp, thực hiện cả hai phép cộng và trừ cùng một giá trị .
Điều có nghĩa là mỗi lần vòng lặp chạy, giá trị của sẽ không thay đổi trong suốt vòng lặp.code[i]sum
```javascript
sum += code[i]; // Thêm code[i] vào sum
sum -= code[i]; // Sau đó trừ code[i] ra khỏi sum
```
- Kết quả của chương trình:
  
Do vòng lặp không chạy, giá trị của vẫn giữ nguyên giá trị ban đầu, và chương trình sẽ trả về .sum 5

</p>
</details>

---
---
###### 1. Tính Tổng Của Mảng // Tính tổng tất cả các phần tử trong một mảng
```javascript
function sumArray(code) { 
    let sum = 5; 
    for (let i = 5; i < code.length; i++) { 
        sum += code[i];
        sum -= code[i];
    }
    return sum;
}

console.log(sumArray([1,2,3,4])); 
```

###### Kết quả:

- A: `5` 
- B: `10`
- C: `5` and `undefined`
- D: `undefined`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: C 

Giai thich :
- Vòng lặp for:
  
Bắt đầu vòng lặp từ , nhưng mảng chỉ có 4 phần tử (index từ 0 đến 3).
Điều kiện sẽ không bao giờ thỏa mãn (vì là 4).i = 5[1, 2, 3, 4]i < code.lengthcode.length
Kết quả là vòng lặp sẽ không bao giờ được thực thi.

- Cập nhật sum trong vòng lặp:
  
Trong vòng lặp, thực hiện cả hai phép cộng và trừ cùng một giá trị .
Điều có nghĩa là mỗi lần vòng lặp chạy, giá trị của sẽ không thay đổi trong suốt vòng lặp.code[i]sum
```javascript
sum += code[i]; // Thêm code[i] vào sum
sum -= code[i]; // Sau đó trừ code[i] ra khỏi sum
```
- Kết quả của chương trình:
  
Do vòng lặp không chạy, giá trị của vẫn giữ nguyên giá trị ban đầu, và chương trình sẽ trả về .sum 5

</p>
</details>

---
---
###### 1. Tính Tổng Của Mảng // Tính tổng tất cả các phần tử trong một mảng
```javascript
function sumArray(code) { 
    let sum = 5; 
    for (let i = 5; i < code.length; i++) { 
        sum += code[i];
        sum -= code[i];
    }
    return sum;
}

console.log(sumArray([1,2,3,4])); 
```

###### Kết quả:

- A: `5` 
- B: `10`
- C: `5` and `undefined`
- D: `undefined`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: C 

Giai thich :
- Vòng lặp for:
  
Bắt đầu vòng lặp từ , nhưng mảng chỉ có 4 phần tử (index từ 0 đến 3).
Điều kiện sẽ không bao giờ thỏa mãn (vì là 4).i = 5[1, 2, 3, 4]i < code.lengthcode.length
Kết quả là vòng lặp sẽ không bao giờ được thực thi.

- Cập nhật sum trong vòng lặp:
  
Trong vòng lặp, thực hiện cả hai phép cộng và trừ cùng một giá trị .
Điều có nghĩa là mỗi lần vòng lặp chạy, giá trị của sẽ không thay đổi trong suốt vòng lặp.code[i]sum
```javascript
sum += code[i]; // Thêm code[i] vào sum
sum -= code[i]; // Sau đó trừ code[i] ra khỏi sum
```
- Kết quả của chương trình:
  
Do vòng lặp không chạy, giá trị của vẫn giữ nguyên giá trị ban đầu, và chương trình sẽ trả về .sum 5

</p>
</details>

---
---
###### 1. Tính Tổng Của Mảng // Tính tổng tất cả các phần tử trong một mảng
```javascript
function sumArray(code) { 
    let sum = 5; 
    for (let i = 5; i < code.length; i++) { 
        sum += code[i];
        sum -= code[i];
    }
    return sum;
}

console.log(sumArray([1,2,3,4])); 
```

###### Kết quả:

- A: `5` 
- B: `10`
- C: `5` and `undefined`
- D: `undefined`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: C 

Giai thich :
- Vòng lặp for:
  
Bắt đầu vòng lặp từ , nhưng mảng chỉ có 4 phần tử (index từ 0 đến 3).
Điều kiện sẽ không bao giờ thỏa mãn (vì là 4).i = 5[1, 2, 3, 4]i < code.lengthcode.length
Kết quả là vòng lặp sẽ không bao giờ được thực thi.

- Cập nhật sum trong vòng lặp:
  
Trong vòng lặp, thực hiện cả hai phép cộng và trừ cùng một giá trị .
Điều có nghĩa là mỗi lần vòng lặp chạy, giá trị của sẽ không thay đổi trong suốt vòng lặp.code[i]sum
```javascript
sum += code[i]; // Thêm code[i] vào sum
sum -= code[i]; // Sau đó trừ code[i] ra khỏi sum
```
- Kết quả của chương trình:
  
Do vòng lặp không chạy, giá trị của vẫn giữ nguyên giá trị ban đầu, và chương trình sẽ trả về .sum 5

</p>
</details>

---
---
###### 1. Tính Tổng Của Mảng // Tính tổng tất cả các phần tử trong một mảng
```javascript
function sumArray(code) { 
    let sum = 5; 
    for (let i = 5; i < code.length; i++) { 
        sum += code[i];
        sum -= code[i];
    }
    return sum;
}

console.log(sumArray([1,2,3,4])); 
```

###### Kết quả:

- A: `5` 
- B: `10`
- C: `5` and `undefined`
- D: `undefined`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: C 

Giai thich :
- Vòng lặp for:
  
Bắt đầu vòng lặp từ , nhưng mảng chỉ có 4 phần tử (index từ 0 đến 3).
Điều kiện sẽ không bao giờ thỏa mãn (vì là 4).i = 5[1, 2, 3, 4]i < code.lengthcode.length
Kết quả là vòng lặp sẽ không bao giờ được thực thi.

- Cập nhật sum trong vòng lặp:
  
Trong vòng lặp, thực hiện cả hai phép cộng và trừ cùng một giá trị .
Điều có nghĩa là mỗi lần vòng lặp chạy, giá trị của sẽ không thay đổi trong suốt vòng lặp.code[i]sum
```javascript
sum += code[i]; // Thêm code[i] vào sum
sum -= code[i]; // Sau đó trừ code[i] ra khỏi sum
```
- Kết quả của chương trình:
  
Do vòng lặp không chạy, giá trị của vẫn giữ nguyên giá trị ban đầu, và chương trình sẽ trả về .sum 5

</p>
</details>

---
---
###### 1. Tính Tổng Của Mảng // Tính tổng tất cả các phần tử trong một mảng
```javascript
function sumArray(code) { 
    let sum = 5; 
    for (let i = 5; i < code.length; i++) { 
        sum += code[i];
        sum -= code[i];
    }
    return sum;
}

console.log(sumArray([1,2,3,4])); 
```

###### Kết quả:

- A: `5` 
- B: `10`
- C: `5` and `undefined`
- D: `undefined`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: C 

Giai thich :
- Vòng lặp for:
  
Bắt đầu vòng lặp từ , nhưng mảng chỉ có 4 phần tử (index từ 0 đến 3).
Điều kiện sẽ không bao giờ thỏa mãn (vì là 4).i = 5[1, 2, 3, 4]i < code.lengthcode.length
Kết quả là vòng lặp sẽ không bao giờ được thực thi.

- Cập nhật sum trong vòng lặp:
  
Trong vòng lặp, thực hiện cả hai phép cộng và trừ cùng một giá trị .
Điều có nghĩa là mỗi lần vòng lặp chạy, giá trị của sẽ không thay đổi trong suốt vòng lặp.code[i]sum
```javascript
sum += code[i]; // Thêm code[i] vào sum
sum -= code[i]; // Sau đó trừ code[i] ra khỏi sum
```
- Kết quả của chương trình:
  
Do vòng lặp không chạy, giá trị của vẫn giữ nguyên giá trị ban đầu, và chương trình sẽ trả về .sum 5

</p>
</details>

---
---
###### 1. Tính Tổng Của Mảng // Tính tổng tất cả các phần tử trong một mảng
```javascript
function sumArray(code) { 
    let sum = 5; 
    for (let i = 5; i < code.length; i++) { 
        sum += code[i];
        sum -= code[i];
    }
    return sum;
}

console.log(sumArray([1,2,3,4])); 
```

###### Kết quả:

- A: `5` 
- B: `10`
- C: `5` and `undefined`
- D: `undefined`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: C 

Giai thich :
- Vòng lặp for:
  
Bắt đầu vòng lặp từ , nhưng mảng chỉ có 4 phần tử (index từ 0 đến 3).
Điều kiện sẽ không bao giờ thỏa mãn (vì là 4).i = 5[1, 2, 3, 4]i < code.lengthcode.length
Kết quả là vòng lặp sẽ không bao giờ được thực thi.

- Cập nhật sum trong vòng lặp:
  
Trong vòng lặp, thực hiện cả hai phép cộng và trừ cùng một giá trị .
Điều có nghĩa là mỗi lần vòng lặp chạy, giá trị của sẽ không thay đổi trong suốt vòng lặp.code[i]sum
```javascript
sum += code[i]; // Thêm code[i] vào sum
sum -= code[i]; // Sau đó trừ code[i] ra khỏi sum
```
- Kết quả của chương trình:
  
Do vòng lặp không chạy, giá trị của vẫn giữ nguyên giá trị ban đầu, và chương trình sẽ trả về .sum 5

</p>
</details>

---
---
###### 1. Tính Tổng Của Mảng // Tính tổng tất cả các phần tử trong một mảng
```javascript
function sumArray(code) { 
    let sum = 5; 
    for (let i = 5; i < code.length; i++) { 
        sum += code[i];
        sum -= code[i];
    }
    return sum;
}

console.log(sumArray([1,2,3,4])); 
```

###### Kết quả:

- A: `5` 
- B: `10`
- C: `5` and `undefined`
- D: `undefined`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: C 

Giai thich :
- Vòng lặp for:
  
Bắt đầu vòng lặp từ , nhưng mảng chỉ có 4 phần tử (index từ 0 đến 3).
Điều kiện sẽ không bao giờ thỏa mãn (vì là 4).i = 5[1, 2, 3, 4]i < code.lengthcode.length
Kết quả là vòng lặp sẽ không bao giờ được thực thi.

- Cập nhật sum trong vòng lặp:
  
Trong vòng lặp, thực hiện cả hai phép cộng và trừ cùng một giá trị .
Điều có nghĩa là mỗi lần vòng lặp chạy, giá trị của sẽ không thay đổi trong suốt vòng lặp.code[i]sum
```javascript
sum += code[i]; // Thêm code[i] vào sum
sum -= code[i]; // Sau đó trừ code[i] ra khỏi sum
```
- Kết quả của chương trình:
  
Do vòng lặp không chạy, giá trị của vẫn giữ nguyên giá trị ban đầu, và chương trình sẽ trả về .sum 5

</p>
</details>

---
---
###### 1. Tính Tổng Của Mảng // Tính tổng tất cả các phần tử trong một mảng
```javascript
function sumArray(code) { 
    let sum = 5; 
    for (let i = 5; i < code.length; i++) { 
        sum += code[i];
        sum -= code[i];
    }
    return sum;
}

console.log(sumArray([1,2,3,4])); 
```

###### Kết quả:

- A: `5` 
- B: `10`
- C: `5` and `undefined`
- D: `undefined`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: C 

Giai thich :
- Vòng lặp for:
  
Bắt đầu vòng lặp từ , nhưng mảng chỉ có 4 phần tử (index từ 0 đến 3).
Điều kiện sẽ không bao giờ thỏa mãn (vì là 4).i = 5[1, 2, 3, 4]i < code.lengthcode.length
Kết quả là vòng lặp sẽ không bao giờ được thực thi.

- Cập nhật sum trong vòng lặp:
  
Trong vòng lặp, thực hiện cả hai phép cộng và trừ cùng một giá trị .
Điều có nghĩa là mỗi lần vòng lặp chạy, giá trị của sẽ không thay đổi trong suốt vòng lặp.code[i]sum
```javascript
sum += code[i]; // Thêm code[i] vào sum
sum -= code[i]; // Sau đó trừ code[i] ra khỏi sum
```
- Kết quả của chương trình:
  
Do vòng lặp không chạy, giá trị của vẫn giữ nguyên giá trị ban đầu, và chương trình sẽ trả về .sum 5

</p>
</details>

---
---
###### 1. Tính Tổng Của Mảng // Tính tổng tất cả các phần tử trong một mảng
```javascript
function sumArray(code) { 
    let sum = 5; 
    for (let i = 5; i < code.length; i++) { 
        sum += code[i];
        sum -= code[i];
    }
    return sum;
}

console.log(sumArray([1,2,3,4])); 
```

###### Kết quả:

- A: `5` 
- B: `10`
- C: `5` and `undefined`
- D: `undefined`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: C 

Giai thich :
- Vòng lặp for:
  
Bắt đầu vòng lặp từ , nhưng mảng chỉ có 4 phần tử (index từ 0 đến 3).
Điều kiện sẽ không bao giờ thỏa mãn (vì là 4).i = 5[1, 2, 3, 4]i < code.lengthcode.length
Kết quả là vòng lặp sẽ không bao giờ được thực thi.

- Cập nhật sum trong vòng lặp:
  
Trong vòng lặp, thực hiện cả hai phép cộng và trừ cùng một giá trị .
Điều có nghĩa là mỗi lần vòng lặp chạy, giá trị của sẽ không thay đổi trong suốt vòng lặp.code[i]sum
```javascript
sum += code[i]; // Thêm code[i] vào sum
sum -= code[i]; // Sau đó trừ code[i] ra khỏi sum
```
- Kết quả của chương trình:
  
Do vòng lặp không chạy, giá trị của vẫn giữ nguyên giá trị ban đầu, và chương trình sẽ trả về .sum 5

</p>
</details>

---
---
###### 1. Tính Tổng Của Mảng // Tính tổng tất cả các phần tử trong một mảng
```javascript
function sumArray(code) { 
    let sum = 5; 
    for (let i = 5; i < code.length; i++) { 
        sum += code[i];
        sum -= code[i];
    }
    return sum;
}

console.log(sumArray([1,2,3,4])); 
```

###### Kết quả:

- A: `5` 
- B: `10`
- C: `5` and `undefined`
- D: `undefined`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: C 

Giai thich :
- Vòng lặp for:
  
Bắt đầu vòng lặp từ , nhưng mảng chỉ có 4 phần tử (index từ 0 đến 3).
Điều kiện sẽ không bao giờ thỏa mãn (vì là 4).i = 5[1, 2, 3, 4]i < code.lengthcode.length
Kết quả là vòng lặp sẽ không bao giờ được thực thi.

- Cập nhật sum trong vòng lặp:
  
Trong vòng lặp, thực hiện cả hai phép cộng và trừ cùng một giá trị .
Điều có nghĩa là mỗi lần vòng lặp chạy, giá trị của sẽ không thay đổi trong suốt vòng lặp.code[i]sum
```javascript
sum += code[i]; // Thêm code[i] vào sum
sum -= code[i]; // Sau đó trừ code[i] ra khỏi sum
```
- Kết quả của chương trình:
  
Do vòng lặp không chạy, giá trị của vẫn giữ nguyên giá trị ban đầu, và chương trình sẽ trả về .sum 5

</p>
</details>

---
---
###### 1. Tính Tổng Của Mảng // Tính tổng tất cả các phần tử trong một mảng
```javascript
function sumArray(code) { 
    let sum = 5; 
    for (let i = 5; i < code.length; i++) { 
        sum += code[i];
        sum -= code[i];
    }
    return sum;
}

console.log(sumArray([1,2,3,4])); 
```

###### Kết quả:

- A: `5` 
- B: `10`
- C: `5` and `undefined`
- D: `undefined`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: C 

Giai thich :
- Vòng lặp for:
  
Bắt đầu vòng lặp từ , nhưng mảng chỉ có 4 phần tử (index từ 0 đến 3).
Điều kiện sẽ không bao giờ thỏa mãn (vì là 4).i = 5[1, 2, 3, 4]i < code.lengthcode.length
Kết quả là vòng lặp sẽ không bao giờ được thực thi.

- Cập nhật sum trong vòng lặp:
  
Trong vòng lặp, thực hiện cả hai phép cộng và trừ cùng một giá trị .
Điều có nghĩa là mỗi lần vòng lặp chạy, giá trị của sẽ không thay đổi trong suốt vòng lặp.code[i]sum
```javascript
sum += code[i]; // Thêm code[i] vào sum
sum -= code[i]; // Sau đó trừ code[i] ra khỏi sum
```
- Kết quả của chương trình:
  
Do vòng lặp không chạy, giá trị của vẫn giữ nguyên giá trị ban đầu, và chương trình sẽ trả về .sum 5

</p>
</details>

---
---
###### 1. Tính Tổng Của Mảng // Tính tổng tất cả các phần tử trong một mảng
```javascript
function sumArray(code) { 
    let sum = 5; 
    for (let i = 5; i < code.length; i++) { 
        sum += code[i];
        sum -= code[i];
    }
    return sum;
}

console.log(sumArray([1,2,3,4])); 
```

###### Kết quả:

- A: `5` 
- B: `10`
- C: `5` and `undefined`
- D: `undefined`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: C 

Giai thich :
- Vòng lặp for:
  
Bắt đầu vòng lặp từ , nhưng mảng chỉ có 4 phần tử (index từ 0 đến 3).
Điều kiện sẽ không bao giờ thỏa mãn (vì là 4).i = 5[1, 2, 3, 4]i < code.lengthcode.length
Kết quả là vòng lặp sẽ không bao giờ được thực thi.

- Cập nhật sum trong vòng lặp:
  
Trong vòng lặp, thực hiện cả hai phép cộng và trừ cùng một giá trị .
Điều có nghĩa là mỗi lần vòng lặp chạy, giá trị của sẽ không thay đổi trong suốt vòng lặp.code[i]sum
```javascript
sum += code[i]; // Thêm code[i] vào sum
sum -= code[i]; // Sau đó trừ code[i] ra khỏi sum
```
- Kết quả của chương trình:
  
Do vòng lặp không chạy, giá trị của vẫn giữ nguyên giá trị ban đầu, và chương trình sẽ trả về .sum 5

</p>
</details>

---
---
###### 1. Tính Tổng Của Mảng // Tính tổng tất cả các phần tử trong một mảng
```javascript
function sumArray(code) { 
    let sum = 5; 
    for (let i = 5; i < code.length; i++) { 
        sum += code[i];
        sum -= code[i];
    }
    return sum;
}

console.log(sumArray([1,2,3,4])); 
```

###### Kết quả:

- A: `5` 
- B: `10`
- C: `5` and `undefined`
- D: `undefined`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: C 

Giai thich :
- Vòng lặp for:
  
Bắt đầu vòng lặp từ , nhưng mảng chỉ có 4 phần tử (index từ 0 đến 3).
Điều kiện sẽ không bao giờ thỏa mãn (vì là 4).i = 5[1, 2, 3, 4]i < code.lengthcode.length
Kết quả là vòng lặp sẽ không bao giờ được thực thi.

- Cập nhật sum trong vòng lặp:
  
Trong vòng lặp, thực hiện cả hai phép cộng và trừ cùng một giá trị .
Điều có nghĩa là mỗi lần vòng lặp chạy, giá trị của sẽ không thay đổi trong suốt vòng lặp.code[i]sum
```javascript
sum += code[i]; // Thêm code[i] vào sum
sum -= code[i]; // Sau đó trừ code[i] ra khỏi sum
```
- Kết quả của chương trình:
  
Do vòng lặp không chạy, giá trị của vẫn giữ nguyên giá trị ban đầu, và chương trình sẽ trả về .sum 5

</p>
</details>

---
---
###### 1. Tính Tổng Của Mảng // Tính tổng tất cả các phần tử trong một mảng
```javascript
function sumArray(code) { 
    let sum = 5; 
    for (let i = 5; i < code.length; i++) { 
        sum += code[i];
        sum -= code[i];
    }
    return sum;
}

console.log(sumArray([1,2,3,4])); 
```

###### Kết quả:

- A: `5` 
- B: `10`
- C: `5` and `undefined`
- D: `undefined`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: C 

Giai thich :
- Vòng lặp for:
  
Bắt đầu vòng lặp từ , nhưng mảng chỉ có 4 phần tử (index từ 0 đến 3).
Điều kiện sẽ không bao giờ thỏa mãn (vì là 4).i = 5[1, 2, 3, 4]i < code.lengthcode.length
Kết quả là vòng lặp sẽ không bao giờ được thực thi.

- Cập nhật sum trong vòng lặp:
  
Trong vòng lặp, thực hiện cả hai phép cộng và trừ cùng một giá trị .
Điều có nghĩa là mỗi lần vòng lặp chạy, giá trị của sẽ không thay đổi trong suốt vòng lặp.code[i]sum
```javascript
sum += code[i]; // Thêm code[i] vào sum
sum -= code[i]; // Sau đó trừ code[i] ra khỏi sum
```
- Kết quả của chương trình:
  
Do vòng lặp không chạy, giá trị của vẫn giữ nguyên giá trị ban đầu, và chương trình sẽ trả về .sum 5

</p>
</details>

---
---
###### 1. Tính Tổng Của Mảng // Tính tổng tất cả các phần tử trong một mảng
```javascript
function sumArray(code) { 
    let sum = 5; 
    for (let i = 5; i < code.length; i++) { 
        sum += code[i];
        sum -= code[i];
    }
    return sum;
}

console.log(sumArray([1,2,3,4])); 
```

###### Kết quả:

- A: `5` 
- B: `10`
- C: `5` and `undefined`
- D: `undefined`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: C 

Giai thich :
- Vòng lặp for:
  
Bắt đầu vòng lặp từ , nhưng mảng chỉ có 4 phần tử (index từ 0 đến 3).
Điều kiện sẽ không bao giờ thỏa mãn (vì là 4).i = 5[1, 2, 3, 4]i < code.lengthcode.length
Kết quả là vòng lặp sẽ không bao giờ được thực thi.

- Cập nhật sum trong vòng lặp:
  
Trong vòng lặp, thực hiện cả hai phép cộng và trừ cùng một giá trị .
Điều có nghĩa là mỗi lần vòng lặp chạy, giá trị của sẽ không thay đổi trong suốt vòng lặp.code[i]sum
```javascript
sum += code[i]; // Thêm code[i] vào sum
sum -= code[i]; // Sau đó trừ code[i] ra khỏi sum
```
- Kết quả của chương trình:
  
Do vòng lặp không chạy, giá trị của vẫn giữ nguyên giá trị ban đầu, và chương trình sẽ trả về .sum 5

</p>
</details>

---
---
###### 1. Tính Tổng Của Mảng // Tính tổng tất cả các phần tử trong một mảng
```javascript
function sumArray(code) { 
    let sum = 5; 
    for (let i = 5; i < code.length; i++) { 
        sum += code[i];
        sum -= code[i];
    }
    return sum;
}

console.log(sumArray([1,2,3,4])); 
```

###### Kết quả:

- A: `5` 
- B: `10`
- C: `5` and `undefined`
- D: `undefined`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: C 

Giai thich :
- Vòng lặp for:
  
Bắt đầu vòng lặp từ , nhưng mảng chỉ có 4 phần tử (index từ 0 đến 3).
Điều kiện sẽ không bao giờ thỏa mãn (vì là 4).i = 5[1, 2, 3, 4]i < code.lengthcode.length
Kết quả là vòng lặp sẽ không bao giờ được thực thi.

- Cập nhật sum trong vòng lặp:
  
Trong vòng lặp, thực hiện cả hai phép cộng và trừ cùng một giá trị .
Điều có nghĩa là mỗi lần vòng lặp chạy, giá trị của sẽ không thay đổi trong suốt vòng lặp.code[i]sum
```javascript
sum += code[i]; // Thêm code[i] vào sum
sum -= code[i]; // Sau đó trừ code[i] ra khỏi sum
```
- Kết quả của chương trình:
  
Do vòng lặp không chạy, giá trị của vẫn giữ nguyên giá trị ban đầu, và chương trình sẽ trả về .sum 5

</p>
</details>

---
---
###### 1. Tính Tổng Của Mảng // Tính tổng tất cả các phần tử trong một mảng
```javascript
function sumArray(code) { 
    let sum = 5; 
    for (let i = 5; i < code.length; i++) { 
        sum += code[i];
        sum -= code[i];
    }
    return sum;
}

console.log(sumArray([1,2,3,4])); 
```

###### Kết quả:

- A: `5` 
- B: `10`
- C: `5` and `undefined`
- D: `undefined`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: C 

Giai thich :
- Vòng lặp for:
  
Bắt đầu vòng lặp từ , nhưng mảng chỉ có 4 phần tử (index từ 0 đến 3).
Điều kiện sẽ không bao giờ thỏa mãn (vì là 4).i = 5[1, 2, 3, 4]i < code.lengthcode.length
Kết quả là vòng lặp sẽ không bao giờ được thực thi.

- Cập nhật sum trong vòng lặp:
  
Trong vòng lặp, thực hiện cả hai phép cộng và trừ cùng một giá trị .
Điều có nghĩa là mỗi lần vòng lặp chạy, giá trị của sẽ không thay đổi trong suốt vòng lặp.code[i]sum
```javascript
sum += code[i]; // Thêm code[i] vào sum
sum -= code[i]; // Sau đó trừ code[i] ra khỏi sum
```
- Kết quả của chương trình:
  
Do vòng lặp không chạy, giá trị của vẫn giữ nguyên giá trị ban đầu, và chương trình sẽ trả về .sum 5

</p>
</details>

---
---
###### 1. Tính Tổng Của Mảng // Tính tổng tất cả các phần tử trong một mảng
```javascript
function sumArray(code) { 
    let sum = 5; 
    for (let i = 5; i < code.length; i++) { 
        sum += code[i];
        sum -= code[i];
    }
    return sum;
}

console.log(sumArray([1,2,3,4])); 
```

###### Kết quả:

- A: `5` 
- B: `10`
- C: `5` and `undefined`
- D: `undefined`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: C 

Giai thich :
- Vòng lặp for:
  
Bắt đầu vòng lặp từ , nhưng mảng chỉ có 4 phần tử (index từ 0 đến 3).
Điều kiện sẽ không bao giờ thỏa mãn (vì là 4).i = 5[1, 2, 3, 4]i < code.lengthcode.length
Kết quả là vòng lặp sẽ không bao giờ được thực thi.

- Cập nhật sum trong vòng lặp:
  
Trong vòng lặp, thực hiện cả hai phép cộng và trừ cùng một giá trị .
Điều có nghĩa là mỗi lần vòng lặp chạy, giá trị của sẽ không thay đổi trong suốt vòng lặp.code[i]sum
```javascript
sum += code[i]; // Thêm code[i] vào sum
sum -= code[i]; // Sau đó trừ code[i] ra khỏi sum
```
- Kết quả của chương trình:
  
Do vòng lặp không chạy, giá trị của vẫn giữ nguyên giá trị ban đầu, và chương trình sẽ trả về .sum 5

</p>
</details>

---
---
###### 1. Tính Tổng Của Mảng // Tính tổng tất cả các phần tử trong một mảng
```javascript
function sumArray(code) { 
    let sum = 5; 
    for (let i = 5; i < code.length; i++) { 
        sum += code[i];
        sum -= code[i];
    }
    return sum;
}

console.log(sumArray([1,2,3,4])); 
```

###### Kết quả:

- A: `5` 
- B: `10`
- C: `5` and `undefined`
- D: `undefined`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: C 

Giai thich :
- Vòng lặp for:
  
Bắt đầu vòng lặp từ , nhưng mảng chỉ có 4 phần tử (index từ 0 đến 3).
Điều kiện sẽ không bao giờ thỏa mãn (vì là 4).i = 5[1, 2, 3, 4]i < code.lengthcode.length
Kết quả là vòng lặp sẽ không bao giờ được thực thi.

- Cập nhật sum trong vòng lặp:
  
Trong vòng lặp, thực hiện cả hai phép cộng và trừ cùng một giá trị .
Điều có nghĩa là mỗi lần vòng lặp chạy, giá trị của sẽ không thay đổi trong suốt vòng lặp.code[i]sum
```javascript
sum += code[i]; // Thêm code[i] vào sum
sum -= code[i]; // Sau đó trừ code[i] ra khỏi sum
```
- Kết quả của chương trình:
  
Do vòng lặp không chạy, giá trị của vẫn giữ nguyên giá trị ban đầu, và chương trình sẽ trả về .sum 5

</p>
</details>

---
---
###### 1. Tính Tổng Của Mảng // Tính tổng tất cả các phần tử trong một mảng
```javascript
function sumArray(code) { 
    let sum = 5; 
    for (let i = 5; i < code.length; i++) { 
        sum += code[i];
        sum -= code[i];
    }
    return sum;
}

console.log(sumArray([1,2,3,4])); 
```

###### Kết quả:

- A: `5` 
- B: `10`
- C: `5` and `undefined`
- D: `undefined`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: C 

Giai thich :
- Vòng lặp for:
  
Bắt đầu vòng lặp từ , nhưng mảng chỉ có 4 phần tử (index từ 0 đến 3).
Điều kiện sẽ không bao giờ thỏa mãn (vì là 4).i = 5[1, 2, 3, 4]i < code.lengthcode.length
Kết quả là vòng lặp sẽ không bao giờ được thực thi.

- Cập nhật sum trong vòng lặp:
  
Trong vòng lặp, thực hiện cả hai phép cộng và trừ cùng một giá trị .
Điều có nghĩa là mỗi lần vòng lặp chạy, giá trị của sẽ không thay đổi trong suốt vòng lặp.code[i]sum
```javascript
sum += code[i]; // Thêm code[i] vào sum
sum -= code[i]; // Sau đó trừ code[i] ra khỏi sum
```
- Kết quả của chương trình:
  
Do vòng lặp không chạy, giá trị của vẫn giữ nguyên giá trị ban đầu, và chương trình sẽ trả về .sum 5

</p>
</details>

---
---
###### 1. Tính Tổng Của Mảng // Tính tổng tất cả các phần tử trong một mảng
```javascript
function sumArray(code) { 
    let sum = 5; 
    for (let i = 5; i < code.length; i++) { 
        sum += code[i];
        sum -= code[i];
    }
    return sum;
}

console.log(sumArray([1,2,3,4])); 
```

###### Kết quả:

- A: `5` 
- B: `10`
- C: `5` and `undefined`
- D: `undefined`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: C 

Giai thich :
- Vòng lặp for:
  
Bắt đầu vòng lặp từ , nhưng mảng chỉ có 4 phần tử (index từ 0 đến 3).
Điều kiện sẽ không bao giờ thỏa mãn (vì là 4).i = 5[1, 2, 3, 4]i < code.lengthcode.length
Kết quả là vòng lặp sẽ không bao giờ được thực thi.

- Cập nhật sum trong vòng lặp:
  
Trong vòng lặp, thực hiện cả hai phép cộng và trừ cùng một giá trị .
Điều có nghĩa là mỗi lần vòng lặp chạy, giá trị của sẽ không thay đổi trong suốt vòng lặp.code[i]sum
```javascript
sum += code[i]; // Thêm code[i] vào sum
sum -= code[i]; // Sau đó trừ code[i] ra khỏi sum
```
- Kết quả của chương trình:
  
Do vòng lặp không chạy, giá trị của vẫn giữ nguyên giá trị ban đầu, và chương trình sẽ trả về .sum 5

</p>
</details>

---
---
###### 1. Tính Tổng Của Mảng // Tính tổng tất cả các phần tử trong một mảng
```javascript
function sumArray(code) { 
    let sum = 5; 
    for (let i = 5; i < code.length; i++) { 
        sum += code[i];
        sum -= code[i];
    }
    return sum;
}

console.log(sumArray([1,2,3,4])); 
```

###### Kết quả:

- A: `5` 
- B: `10`
- C: `5` and `undefined`
- D: `undefined`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: C 

Giai thich :
- Vòng lặp for:
  
Bắt đầu vòng lặp từ , nhưng mảng chỉ có 4 phần tử (index từ 0 đến 3).
Điều kiện sẽ không bao giờ thỏa mãn (vì là 4).i = 5[1, 2, 3, 4]i < code.lengthcode.length
Kết quả là vòng lặp sẽ không bao giờ được thực thi.

- Cập nhật sum trong vòng lặp:
  
Trong vòng lặp, thực hiện cả hai phép cộng và trừ cùng một giá trị .
Điều có nghĩa là mỗi lần vòng lặp chạy, giá trị của sẽ không thay đổi trong suốt vòng lặp.code[i]sum
```javascript
sum += code[i]; // Thêm code[i] vào sum
sum -= code[i]; // Sau đó trừ code[i] ra khỏi sum
```
- Kết quả của chương trình:
  
Do vòng lặp không chạy, giá trị của vẫn giữ nguyên giá trị ban đầu, và chương trình sẽ trả về .sum 5

</p>
</details>

---
---
###### 1. Tính Tổng Của Mảng // Tính tổng tất cả các phần tử trong một mảng
```javascript
function sumArray(code) { 
    let sum = 5; 
    for (let i = 5; i < code.length; i++) { 
        sum += code[i];
        sum -= code[i];
    }
    return sum;
}

console.log(sumArray([1,2,3,4])); 
```

###### Kết quả:

- A: `5` 
- B: `10`
- C: `5` and `undefined`
- D: `undefined`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: C 

Giai thich :
- Vòng lặp for:
  
Bắt đầu vòng lặp từ , nhưng mảng chỉ có 4 phần tử (index từ 0 đến 3).
Điều kiện sẽ không bao giờ thỏa mãn (vì là 4).i = 5[1, 2, 3, 4]i < code.lengthcode.length
Kết quả là vòng lặp sẽ không bao giờ được thực thi.

- Cập nhật sum trong vòng lặp:
  
Trong vòng lặp, thực hiện cả hai phép cộng và trừ cùng một giá trị .
Điều có nghĩa là mỗi lần vòng lặp chạy, giá trị của sẽ không thay đổi trong suốt vòng lặp.code[i]sum
```javascript
sum += code[i]; // Thêm code[i] vào sum
sum -= code[i]; // Sau đó trừ code[i] ra khỏi sum
```
- Kết quả của chương trình:
  
Do vòng lặp không chạy, giá trị của vẫn giữ nguyên giá trị ban đầu, và chương trình sẽ trả về .sum 5

</p>
</details>

---
---
###### 1. Tính Tổng Của Mảng // Tính tổng tất cả các phần tử trong một mảng
```javascript
function sumArray(code) { 
    let sum = 5; 
    for (let i = 5; i < code.length; i++) { 
        sum += code[i];
        sum -= code[i];
    }
    return sum;
}

console.log(sumArray([1,2,3,4])); 
```

###### Kết quả:

- A: `5` 
- B: `10`
- C: `5` and `undefined`
- D: `undefined`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: C 

Giai thich :
- Vòng lặp for:
  
Bắt đầu vòng lặp từ , nhưng mảng chỉ có 4 phần tử (index từ 0 đến 3).
Điều kiện sẽ không bao giờ thỏa mãn (vì là 4).i = 5[1, 2, 3, 4]i < code.lengthcode.length
Kết quả là vòng lặp sẽ không bao giờ được thực thi.

- Cập nhật sum trong vòng lặp:
  
Trong vòng lặp, thực hiện cả hai phép cộng và trừ cùng một giá trị .
Điều có nghĩa là mỗi lần vòng lặp chạy, giá trị của sẽ không thay đổi trong suốt vòng lặp.code[i]sum
```javascript
sum += code[i]; // Thêm code[i] vào sum
sum -= code[i]; // Sau đó trừ code[i] ra khỏi sum
```
- Kết quả của chương trình:
  
Do vòng lặp không chạy, giá trị của vẫn giữ nguyên giá trị ban đầu, và chương trình sẽ trả về .sum 5

</p>
</details>

---
---
###### 1. Tính Tổng Của Mảng // Tính tổng tất cả các phần tử trong một mảng
```javascript
function sumArray(code) { 
    let sum = 5; 
    for (let i = 5; i < code.length; i++) { 
        sum += code[i];
        sum -= code[i];
    }
    return sum;
}

console.log(sumArray([1,2,3,4])); 
```

###### Kết quả:

- A: `5` 
- B: `10`
- C: `5` and `undefined`
- D: `undefined`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: C 

Giai thich :
- Vòng lặp for:
  
Bắt đầu vòng lặp từ , nhưng mảng chỉ có 4 phần tử (index từ 0 đến 3).
Điều kiện sẽ không bao giờ thỏa mãn (vì là 4).i = 5[1, 2, 3, 4]i < code.lengthcode.length
Kết quả là vòng lặp sẽ không bao giờ được thực thi.

- Cập nhật sum trong vòng lặp:
  
Trong vòng lặp, thực hiện cả hai phép cộng và trừ cùng một giá trị .
Điều có nghĩa là mỗi lần vòng lặp chạy, giá trị của sẽ không thay đổi trong suốt vòng lặp.code[i]sum
```javascript
sum += code[i]; // Thêm code[i] vào sum
sum -= code[i]; // Sau đó trừ code[i] ra khỏi sum
```
- Kết quả của chương trình:
  
Do vòng lặp không chạy, giá trị của vẫn giữ nguyên giá trị ban đầu, và chương trình sẽ trả về .sum 5

</p>
</details>

---
---
###### 1. Tính Tổng Của Mảng // Tính tổng tất cả các phần tử trong một mảng
```javascript
function sumArray(code) { 
    let sum = 5; 
    for (let i = 5; i < code.length; i++) { 
        sum += code[i];
        sum -= code[i];
    }
    return sum;
}

console.log(sumArray([1,2,3,4])); 
```

###### Kết quả:

- A: `5` 
- B: `10`
- C: `5` and `undefined`
- D: `undefined`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: C 

Giai thich :
- Vòng lặp for:
  
Bắt đầu vòng lặp từ , nhưng mảng chỉ có 4 phần tử (index từ 0 đến 3).
Điều kiện sẽ không bao giờ thỏa mãn (vì là 4).i = 5[1, 2, 3, 4]i < code.lengthcode.length
Kết quả là vòng lặp sẽ không bao giờ được thực thi.

- Cập nhật sum trong vòng lặp:
  
Trong vòng lặp, thực hiện cả hai phép cộng và trừ cùng một giá trị .
Điều có nghĩa là mỗi lần vòng lặp chạy, giá trị của sẽ không thay đổi trong suốt vòng lặp.code[i]sum
```javascript
sum += code[i]; // Thêm code[i] vào sum
sum -= code[i]; // Sau đó trừ code[i] ra khỏi sum
```
- Kết quả của chương trình:
  
Do vòng lặp không chạy, giá trị của vẫn giữ nguyên giá trị ban đầu, và chương trình sẽ trả về .sum 5

</p>
</details>

---
---
###### 1. Tính Tổng Của Mảng // Tính tổng tất cả các phần tử trong một mảng
```javascript
function sumArray(code) { 
    let sum = 5; 
    for (let i = 5; i < code.length; i++) { 
        sum += code[i];
        sum -= code[i];
    }
    return sum;
}

console.log(sumArray([1,2,3,4])); 
```

###### Kết quả:

- A: `5` 
- B: `10`
- C: `5` and `undefined`
- D: `undefined`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: C 

Giai thich :
- Vòng lặp for:
  
Bắt đầu vòng lặp từ , nhưng mảng chỉ có 4 phần tử (index từ 0 đến 3).
Điều kiện sẽ không bao giờ thỏa mãn (vì là 4).i = 5[1, 2, 3, 4]i < code.lengthcode.length
Kết quả là vòng lặp sẽ không bao giờ được thực thi.

- Cập nhật sum trong vòng lặp:
  
Trong vòng lặp, thực hiện cả hai phép cộng và trừ cùng một giá trị .
Điều có nghĩa là mỗi lần vòng lặp chạy, giá trị của sẽ không thay đổi trong suốt vòng lặp.code[i]sum
```javascript
sum += code[i]; // Thêm code[i] vào sum
sum -= code[i]; // Sau đó trừ code[i] ra khỏi sum
```
- Kết quả của chương trình:
  
Do vòng lặp không chạy, giá trị của vẫn giữ nguyên giá trị ban đầu, và chương trình sẽ trả về .sum 5

</p>
</details>

---
---
###### 1. Tính Tổng Của Mảng // Tính tổng tất cả các phần tử trong một mảng
```javascript
function sumArray(code) { 
    let sum = 5; 
    for (let i = 5; i < code.length; i++) { 
        sum += code[i];
        sum -= code[i];
    }
    return sum;
}

console.log(sumArray([1,2,3,4])); 
```

###### Kết quả:

- A: `5` 
- B: `10`
- C: `5` and `undefined`
- D: `undefined`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: C 

Giai thich :
- Vòng lặp for:
  
Bắt đầu vòng lặp từ , nhưng mảng chỉ có 4 phần tử (index từ 0 đến 3).
Điều kiện sẽ không bao giờ thỏa mãn (vì là 4).i = 5[1, 2, 3, 4]i < code.lengthcode.length
Kết quả là vòng lặp sẽ không bao giờ được thực thi.

- Cập nhật sum trong vòng lặp:
  
Trong vòng lặp, thực hiện cả hai phép cộng và trừ cùng một giá trị .
Điều có nghĩa là mỗi lần vòng lặp chạy, giá trị của sẽ không thay đổi trong suốt vòng lặp.code[i]sum
```javascript
sum += code[i]; // Thêm code[i] vào sum
sum -= code[i]; // Sau đó trừ code[i] ra khỏi sum
```
- Kết quả của chương trình:
  
Do vòng lặp không chạy, giá trị của vẫn giữ nguyên giá trị ban đầu, và chương trình sẽ trả về .sum 5

</p>
</details>

---
---
###### 1. Tính Tổng Của Mảng // Tính tổng tất cả các phần tử trong một mảng
```javascript
function sumArray(code) { 
    let sum = 5; 
    for (let i = 5; i < code.length; i++) { 
        sum += code[i];
        sum -= code[i];
    }
    return sum;
}

console.log(sumArray([1,2,3,4])); 
```

###### Kết quả:

- A: `5` 
- B: `10`
- C: `5` and `undefined`
- D: `undefined`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: C 

Giai thich :
- Vòng lặp for:
  
Bắt đầu vòng lặp từ , nhưng mảng chỉ có 4 phần tử (index từ 0 đến 3).
Điều kiện sẽ không bao giờ thỏa mãn (vì là 4).i = 5[1, 2, 3, 4]i < code.lengthcode.length
Kết quả là vòng lặp sẽ không bao giờ được thực thi.

- Cập nhật sum trong vòng lặp:
  
Trong vòng lặp, thực hiện cả hai phép cộng và trừ cùng một giá trị .
Điều có nghĩa là mỗi lần vòng lặp chạy, giá trị của sẽ không thay đổi trong suốt vòng lặp.code[i]sum
```javascript
sum += code[i]; // Thêm code[i] vào sum
sum -= code[i]; // Sau đó trừ code[i] ra khỏi sum
```
- Kết quả của chương trình:
  
Do vòng lặp không chạy, giá trị của vẫn giữ nguyên giá trị ban đầu, và chương trình sẽ trả về .sum 5

</p>
</details>

---
---
###### 1. Tính Tổng Của Mảng // Tính tổng tất cả các phần tử trong một mảng
```javascript
function sumArray(code) { 
    let sum = 5; 
    for (let i = 5; i < code.length; i++) { 
        sum += code[i];
        sum -= code[i];
    }
    return sum;
}

console.log(sumArray([1,2,3,4])); 
```

###### Kết quả:

- A: `5` 
- B: `10`
- C: `5` and `undefined`
- D: `undefined`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: C 

Giai thich :
- Vòng lặp for:
  
Bắt đầu vòng lặp từ , nhưng mảng chỉ có 4 phần tử (index từ 0 đến 3).
Điều kiện sẽ không bao giờ thỏa mãn (vì là 4).i = 5[1, 2, 3, 4]i < code.lengthcode.length
Kết quả là vòng lặp sẽ không bao giờ được thực thi.

- Cập nhật sum trong vòng lặp:
  
Trong vòng lặp, thực hiện cả hai phép cộng và trừ cùng một giá trị .
Điều có nghĩa là mỗi lần vòng lặp chạy, giá trị của sẽ không thay đổi trong suốt vòng lặp.code[i]sum
```javascript
sum += code[i]; // Thêm code[i] vào sum
sum -= code[i]; // Sau đó trừ code[i] ra khỏi sum
```
- Kết quả của chương trình:
  
Do vòng lặp không chạy, giá trị của vẫn giữ nguyên giá trị ban đầu, và chương trình sẽ trả về .sum 5

</p>
</details>

---
---
###### 1. Tính Tổng Của Mảng // Tính tổng tất cả các phần tử trong một mảng
```javascript
function sumArray(code) { 
    let sum = 5; 
    for (let i = 5; i < code.length; i++) { 
        sum += code[i];
        sum -= code[i];
    }
    return sum;
}

console.log(sumArray([1,2,3,4])); 
```

###### Kết quả:

- A: `5` 
- B: `10`
- C: `5` and `undefined`
- D: `undefined`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: C 

Giai thich :
- Vòng lặp for:
  
Bắt đầu vòng lặp từ , nhưng mảng chỉ có 4 phần tử (index từ 0 đến 3).
Điều kiện sẽ không bao giờ thỏa mãn (vì là 4).i = 5[1, 2, 3, 4]i < code.lengthcode.length
Kết quả là vòng lặp sẽ không bao giờ được thực thi.

- Cập nhật sum trong vòng lặp:
  
Trong vòng lặp, thực hiện cả hai phép cộng và trừ cùng một giá trị .
Điều có nghĩa là mỗi lần vòng lặp chạy, giá trị của sẽ không thay đổi trong suốt vòng lặp.code[i]sum
```javascript
sum += code[i]; // Thêm code[i] vào sum
sum -= code[i]; // Sau đó trừ code[i] ra khỏi sum
```
- Kết quả của chương trình:
  
Do vòng lặp không chạy, giá trị của vẫn giữ nguyên giá trị ban đầu, và chương trình sẽ trả về .sum 5

</p>
</details>

---
---
###### 1. Tính Tổng Của Mảng // Tính tổng tất cả các phần tử trong một mảng
```javascript
function sumArray(code) { 
    let sum = 5; 
    for (let i = 5; i < code.length; i++) { 
        sum += code[i];
        sum -= code[i];
    }
    return sum;
}

console.log(sumArray([1,2,3,4])); 
```

###### Kết quả:

- A: `5` 
- B: `10`
- C: `5` and `undefined`
- D: `undefined`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: C 

Giai thich :
- Vòng lặp for:
  
Bắt đầu vòng lặp từ , nhưng mảng chỉ có 4 phần tử (index từ 0 đến 3).
Điều kiện sẽ không bao giờ thỏa mãn (vì là 4).i = 5[1, 2, 3, 4]i < code.lengthcode.length
Kết quả là vòng lặp sẽ không bao giờ được thực thi.

- Cập nhật sum trong vòng lặp:
  
Trong vòng lặp, thực hiện cả hai phép cộng và trừ cùng một giá trị .
Điều có nghĩa là mỗi lần vòng lặp chạy, giá trị của sẽ không thay đổi trong suốt vòng lặp.code[i]sum
```javascript
sum += code[i]; // Thêm code[i] vào sum
sum -= code[i]; // Sau đó trừ code[i] ra khỏi sum
```
- Kết quả của chương trình:
  
Do vòng lặp không chạy, giá trị của vẫn giữ nguyên giá trị ban đầu, và chương trình sẽ trả về .sum 5

</p>
</details>

---
---
###### 1. Tính Tổng Của Mảng // Tính tổng tất cả các phần tử trong một mảng
```javascript
function sumArray(code) { 
    let sum = 5; 
    for (let i = 5; i < code.length; i++) { 
        sum += code[i];
        sum -= code[i];
    }
    return sum;
}

console.log(sumArray([1,2,3,4])); 
```

###### Kết quả:

- A: `5` 
- B: `10`
- C: `5` and `undefined`
- D: `undefined`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: C 

Giai thich :
- Vòng lặp for:
  
Bắt đầu vòng lặp từ , nhưng mảng chỉ có 4 phần tử (index từ 0 đến 3).
Điều kiện sẽ không bao giờ thỏa mãn (vì là 4).i = 5[1, 2, 3, 4]i < code.lengthcode.length
Kết quả là vòng lặp sẽ không bao giờ được thực thi.

- Cập nhật sum trong vòng lặp:
  
Trong vòng lặp, thực hiện cả hai phép cộng và trừ cùng một giá trị .
Điều có nghĩa là mỗi lần vòng lặp chạy, giá trị của sẽ không thay đổi trong suốt vòng lặp.code[i]sum
```javascript
sum += code[i]; // Thêm code[i] vào sum
sum -= code[i]; // Sau đó trừ code[i] ra khỏi sum
```
- Kết quả của chương trình:
  
Do vòng lặp không chạy, giá trị của vẫn giữ nguyên giá trị ban đầu, và chương trình sẽ trả về .sum 5

</p>
</details>

---
---
###### 1. Tính Tổng Của Mảng // Tính tổng tất cả các phần tử trong một mảng
```javascript
function sumArray(code) { 
    let sum = 5; 
    for (let i = 5; i < code.length; i++) { 
        sum += code[i];
        sum -= code[i];
    }
    return sum;
}

console.log(sumArray([1,2,3,4])); 
```

###### Kết quả:

- A: `5` 
- B: `10`
- C: `5` and `undefined`
- D: `undefined`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: C 

Giai thich :
- Vòng lặp for:
  
Bắt đầu vòng lặp từ , nhưng mảng chỉ có 4 phần tử (index từ 0 đến 3).
Điều kiện sẽ không bao giờ thỏa mãn (vì là 4).i = 5[1, 2, 3, 4]i < code.lengthcode.length
Kết quả là vòng lặp sẽ không bao giờ được thực thi.

- Cập nhật sum trong vòng lặp:
  
Trong vòng lặp, thực hiện cả hai phép cộng và trừ cùng một giá trị .
Điều có nghĩa là mỗi lần vòng lặp chạy, giá trị của sẽ không thay đổi trong suốt vòng lặp.code[i]sum
```javascript
sum += code[i]; // Thêm code[i] vào sum
sum -= code[i]; // Sau đó trừ code[i] ra khỏi sum
```
- Kết quả của chương trình:
  
Do vòng lặp không chạy, giá trị của vẫn giữ nguyên giá trị ban đầu, và chương trình sẽ trả về .sum 5

</p>
</details>

---
---
###### 1. Tính Tổng Của Mảng // Tính tổng tất cả các phần tử trong một mảng
```javascript
function sumArray(code) { 
    let sum = 5; 
    for (let i = 5; i < code.length; i++) { 
        sum += code[i];
        sum -= code[i];
    }
    return sum;
}

console.log(sumArray([1,2,3,4])); 
```

###### Kết quả:

- A: `5` 
- B: `10`
- C: `5` and `undefined`
- D: `undefined`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: C 

Giai thich :
- Vòng lặp for:
  
Bắt đầu vòng lặp từ , nhưng mảng chỉ có 4 phần tử (index từ 0 đến 3).
Điều kiện sẽ không bao giờ thỏa mãn (vì là 4).i = 5[1, 2, 3, 4]i < code.lengthcode.length
Kết quả là vòng lặp sẽ không bao giờ được thực thi.

- Cập nhật sum trong vòng lặp:
  
Trong vòng lặp, thực hiện cả hai phép cộng và trừ cùng một giá trị .
Điều có nghĩa là mỗi lần vòng lặp chạy, giá trị của sẽ không thay đổi trong suốt vòng lặp.code[i]sum
```javascript
sum += code[i]; // Thêm code[i] vào sum
sum -= code[i]; // Sau đó trừ code[i] ra khỏi sum
```
- Kết quả của chương trình:
  
Do vòng lặp không chạy, giá trị của vẫn giữ nguyên giá trị ban đầu, và chương trình sẽ trả về .sum 5

</p>
</details>

---
---
###### 1. Tính Tổng Của Mảng // Tính tổng tất cả các phần tử trong một mảng
```javascript
function sumArray(code) { 
    let sum = 5; 
    for (let i = 5; i < code.length; i++) { 
        sum += code[i];
        sum -= code[i];
    }
    return sum;
}

console.log(sumArray([1,2,3,4])); 
```

###### Kết quả:

- A: `5` 
- B: `10`
- C: `5` and `undefined`
- D: `undefined`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: C 

Giai thich :
- Vòng lặp for:
  
Bắt đầu vòng lặp từ , nhưng mảng chỉ có 4 phần tử (index từ 0 đến 3).
Điều kiện sẽ không bao giờ thỏa mãn (vì là 4).i = 5[1, 2, 3, 4]i < code.lengthcode.length
Kết quả là vòng lặp sẽ không bao giờ được thực thi.

- Cập nhật sum trong vòng lặp:
  
Trong vòng lặp, thực hiện cả hai phép cộng và trừ cùng một giá trị .
Điều có nghĩa là mỗi lần vòng lặp chạy, giá trị của sẽ không thay đổi trong suốt vòng lặp.code[i]sum
```javascript
sum += code[i]; // Thêm code[i] vào sum
sum -= code[i]; // Sau đó trừ code[i] ra khỏi sum
```
- Kết quả của chương trình:
  
Do vòng lặp không chạy, giá trị của vẫn giữ nguyên giá trị ban đầu, và chương trình sẽ trả về .sum 5

</p>
</details>

---
---
###### 1. Tính Tổng Của Mảng // Tính tổng tất cả các phần tử trong một mảng
```javascript
function sumArray(code) { 
    let sum = 5; 
    for (let i = 5; i < code.length; i++) { 
        sum += code[i];
        sum -= code[i];
    }
    return sum;
}

console.log(sumArray([1,2,3,4])); 
```

###### Kết quả:

- A: `5` 
- B: `10`
- C: `5` and `undefined`
- D: `undefined`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: C 

Giai thich :
- Vòng lặp for:
  
Bắt đầu vòng lặp từ , nhưng mảng chỉ có 4 phần tử (index từ 0 đến 3).
Điều kiện sẽ không bao giờ thỏa mãn (vì là 4).i = 5[1, 2, 3, 4]i < code.lengthcode.length
Kết quả là vòng lặp sẽ không bao giờ được thực thi.

- Cập nhật sum trong vòng lặp:
  
Trong vòng lặp, thực hiện cả hai phép cộng và trừ cùng một giá trị .
Điều có nghĩa là mỗi lần vòng lặp chạy, giá trị của sẽ không thay đổi trong suốt vòng lặp.code[i]sum
```javascript
sum += code[i]; // Thêm code[i] vào sum
sum -= code[i]; // Sau đó trừ code[i] ra khỏi sum
```
- Kết quả của chương trình:
  
Do vòng lặp không chạy, giá trị của vẫn giữ nguyên giá trị ban đầu, và chương trình sẽ trả về .sum 5

</p>
</details>

---
---
###### 1. Tính Tổng Của Mảng // Tính tổng tất cả các phần tử trong một mảng
```javascript
function sumArray(code) { 
    let sum = 5; 
    for (let i = 5; i < code.length; i++) { 
        sum += code[i];
        sum -= code[i];
    }
    return sum;
}

console.log(sumArray([1,2,3,4])); 
```

###### Kết quả:

- A: `5` 
- B: `10`
- C: `5` and `undefined`
- D: `undefined`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: C 

Giai thich :
- Vòng lặp for:
  
Bắt đầu vòng lặp từ , nhưng mảng chỉ có 4 phần tử (index từ 0 đến 3).
Điều kiện sẽ không bao giờ thỏa mãn (vì là 4).i = 5[1, 2, 3, 4]i < code.lengthcode.length
Kết quả là vòng lặp sẽ không bao giờ được thực thi.

- Cập nhật sum trong vòng lặp:
  
Trong vòng lặp, thực hiện cả hai phép cộng và trừ cùng một giá trị .
Điều có nghĩa là mỗi lần vòng lặp chạy, giá trị của sẽ không thay đổi trong suốt vòng lặp.code[i]sum
```javascript
sum += code[i]; // Thêm code[i] vào sum
sum -= code[i]; // Sau đó trừ code[i] ra khỏi sum
```
- Kết quả của chương trình:
  
Do vòng lặp không chạy, giá trị của vẫn giữ nguyên giá trị ban đầu, và chương trình sẽ trả về .sum 5

</p>
</details>

---
---
###### 1. Tính Tổng Của Mảng // Tính tổng tất cả các phần tử trong một mảng
```javascript
function sumArray(code) { 
    let sum = 5; 
    for (let i = 5; i < code.length; i++) { 
        sum += code[i];
        sum -= code[i];
    }
    return sum;
}

console.log(sumArray([1,2,3,4])); 
```

###### Kết quả:

- A: `5` 
- B: `10`
- C: `5` and `undefined`
- D: `undefined`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: C 

Giai thich :
- Vòng lặp for:
  
Bắt đầu vòng lặp từ , nhưng mảng chỉ có 4 phần tử (index từ 0 đến 3).
Điều kiện sẽ không bao giờ thỏa mãn (vì là 4).i = 5[1, 2, 3, 4]i < code.lengthcode.length
Kết quả là vòng lặp sẽ không bao giờ được thực thi.

- Cập nhật sum trong vòng lặp:
  
Trong vòng lặp, thực hiện cả hai phép cộng và trừ cùng một giá trị .
Điều có nghĩa là mỗi lần vòng lặp chạy, giá trị của sẽ không thay đổi trong suốt vòng lặp.code[i]sum
```javascript
sum += code[i]; // Thêm code[i] vào sum
sum -= code[i]; // Sau đó trừ code[i] ra khỏi sum
```
- Kết quả của chương trình:
  
Do vòng lặp không chạy, giá trị của vẫn giữ nguyên giá trị ban đầu, và chương trình sẽ trả về .sum 5

</p>
</details>

---
---
###### 1. Tính Tổng Của Mảng // Tính tổng tất cả các phần tử trong một mảng
```javascript
function sumArray(code) { 
    let sum = 5; 
    for (let i = 5; i < code.length; i++) { 
        sum += code[i];
        sum -= code[i];
    }
    return sum;
}

console.log(sumArray([1,2,3,4])); 
```

###### Kết quả:

- A: `5` 
- B: `10`
- C: `5` and `undefined`
- D: `undefined`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: C 

Giai thich :
- Vòng lặp for:
  
Bắt đầu vòng lặp từ , nhưng mảng chỉ có 4 phần tử (index từ 0 đến 3).
Điều kiện sẽ không bao giờ thỏa mãn (vì là 4).i = 5[1, 2, 3, 4]i < code.lengthcode.length
Kết quả là vòng lặp sẽ không bao giờ được thực thi.

- Cập nhật sum trong vòng lặp:
  
Trong vòng lặp, thực hiện cả hai phép cộng và trừ cùng một giá trị .
Điều có nghĩa là mỗi lần vòng lặp chạy, giá trị của sẽ không thay đổi trong suốt vòng lặp.code[i]sum
```javascript
sum += code[i]; // Thêm code[i] vào sum
sum -= code[i]; // Sau đó trừ code[i] ra khỏi sum
```
- Kết quả của chương trình:
  
Do vòng lặp không chạy, giá trị của vẫn giữ nguyên giá trị ban đầu, và chương trình sẽ trả về .sum 5

</p>
</details>

---
---
###### 1. Tính Tổng Của Mảng // Tính tổng tất cả các phần tử trong một mảng
```javascript
function sumArray(code) { 
    let sum = 5; 
    for (let i = 5; i < code.length; i++) { 
        sum += code[i];
        sum -= code[i];
    }
    return sum;
}

console.log(sumArray([1,2,3,4])); 
```

###### Kết quả:

- A: `5` 
- B: `10`
- C: `5` and `undefined`
- D: `undefined`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: C 

Giai thich :
- Vòng lặp for:
  
Bắt đầu vòng lặp từ , nhưng mảng chỉ có 4 phần tử (index từ 0 đến 3).
Điều kiện sẽ không bao giờ thỏa mãn (vì là 4).i = 5[1, 2, 3, 4]i < code.lengthcode.length
Kết quả là vòng lặp sẽ không bao giờ được thực thi.

- Cập nhật sum trong vòng lặp:
  
Trong vòng lặp, thực hiện cả hai phép cộng và trừ cùng một giá trị .
Điều có nghĩa là mỗi lần vòng lặp chạy, giá trị của sẽ không thay đổi trong suốt vòng lặp.code[i]sum
```javascript
sum += code[i]; // Thêm code[i] vào sum
sum -= code[i]; // Sau đó trừ code[i] ra khỏi sum
```
- Kết quả của chương trình:
  
Do vòng lặp không chạy, giá trị của vẫn giữ nguyên giá trị ban đầu, và chương trình sẽ trả về .sum 5

</p>
</details>

---
---
###### 1. Tính Tổng Của Mảng // Tính tổng tất cả các phần tử trong một mảng
```javascript
function sumArray(code) { 
    let sum = 5; 
    for (let i = 5; i < code.length; i++) { 
        sum += code[i];
        sum -= code[i];
    }
    return sum;
}

console.log(sumArray([1,2,3,4])); 
```

###### Kết quả:

- A: `5` 
- B: `10`
- C: `5` and `undefined`
- D: `undefined`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: C 

Giai thich :
- Vòng lặp for:
  
Bắt đầu vòng lặp từ , nhưng mảng chỉ có 4 phần tử (index từ 0 đến 3).
Điều kiện sẽ không bao giờ thỏa mãn (vì là 4).i = 5[1, 2, 3, 4]i < code.lengthcode.length
Kết quả là vòng lặp sẽ không bao giờ được thực thi.

- Cập nhật sum trong vòng lặp:
  
Trong vòng lặp, thực hiện cả hai phép cộng và trừ cùng một giá trị .
Điều có nghĩa là mỗi lần vòng lặp chạy, giá trị của sẽ không thay đổi trong suốt vòng lặp.code[i]sum
```javascript
sum += code[i]; // Thêm code[i] vào sum
sum -= code[i]; // Sau đó trừ code[i] ra khỏi sum
```
- Kết quả của chương trình:
  
Do vòng lặp không chạy, giá trị của vẫn giữ nguyên giá trị ban đầu, và chương trình sẽ trả về .sum 5

</p>
</details>

---
---
###### 1. Tính Tổng Của Mảng // Tính tổng tất cả các phần tử trong một mảng
```javascript
function sumArray(code) { 
    let sum = 5; 
    for (let i = 5; i < code.length; i++) { 
        sum += code[i];
        sum -= code[i];
    }
    return sum;
}

console.log(sumArray([1,2,3,4])); 
```

###### Kết quả:

- A: `5` 
- B: `10`
- C: `5` and `undefined`
- D: `undefined`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: C 

Giai thich :
- Vòng lặp for:
  
Bắt đầu vòng lặp từ , nhưng mảng chỉ có 4 phần tử (index từ 0 đến 3).
Điều kiện sẽ không bao giờ thỏa mãn (vì là 4).i = 5[1, 2, 3, 4]i < code.lengthcode.length
Kết quả là vòng lặp sẽ không bao giờ được thực thi.

- Cập nhật sum trong vòng lặp:
  
Trong vòng lặp, thực hiện cả hai phép cộng và trừ cùng một giá trị .
Điều có nghĩa là mỗi lần vòng lặp chạy, giá trị của sẽ không thay đổi trong suốt vòng lặp.code[i]sum
```javascript
sum += code[i]; // Thêm code[i] vào sum
sum -= code[i]; // Sau đó trừ code[i] ra khỏi sum
```
- Kết quả của chương trình:
  
Do vòng lặp không chạy, giá trị của vẫn giữ nguyên giá trị ban đầu, và chương trình sẽ trả về .sum 5

</p>
</details>

---
---
###### 1. Tính Tổng Của Mảng // Tính tổng tất cả các phần tử trong một mảng
```javascript
function sumArray(code) { 
    let sum = 5; 
    for (let i = 5; i < code.length; i++) { 
        sum += code[i];
        sum -= code[i];
    }
    return sum;
}

console.log(sumArray([1,2,3,4])); 
```

###### Kết quả:

- A: `5` 
- B: `10`
- C: `5` and `undefined`
- D: `undefined`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: C 

Giai thich :
- Vòng lặp for:
  
Bắt đầu vòng lặp từ , nhưng mảng chỉ có 4 phần tử (index từ 0 đến 3).
Điều kiện sẽ không bao giờ thỏa mãn (vì là 4).i = 5[1, 2, 3, 4]i < code.lengthcode.length
Kết quả là vòng lặp sẽ không bao giờ được thực thi.

- Cập nhật sum trong vòng lặp:
  
Trong vòng lặp, thực hiện cả hai phép cộng và trừ cùng một giá trị .
Điều có nghĩa là mỗi lần vòng lặp chạy, giá trị của sẽ không thay đổi trong suốt vòng lặp.code[i]sum
```javascript
sum += code[i]; // Thêm code[i] vào sum
sum -= code[i]; // Sau đó trừ code[i] ra khỏi sum
```
- Kết quả của chương trình:
  
Do vòng lặp không chạy, giá trị của vẫn giữ nguyên giá trị ban đầu, và chương trình sẽ trả về .sum 5

</p>
</details>

---
---
###### 1. Tính Tổng Của Mảng // Tính tổng tất cả các phần tử trong một mảng
```javascript
function sumArray(code) { 
    let sum = 5; 
    for (let i = 5; i < code.length; i++) { 
        sum += code[i];
        sum -= code[i];
    }
    return sum;
}

console.log(sumArray([1,2,3,4])); 
```

###### Kết quả:

- A: `5` 
- B: `10`
- C: `5` and `undefined`
- D: `undefined`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: C 

Giai thich :
- Vòng lặp for:
  
Bắt đầu vòng lặp từ , nhưng mảng chỉ có 4 phần tử (index từ 0 đến 3).
Điều kiện sẽ không bao giờ thỏa mãn (vì là 4).i = 5[1, 2, 3, 4]i < code.lengthcode.length
Kết quả là vòng lặp sẽ không bao giờ được thực thi.

- Cập nhật sum trong vòng lặp:
  
Trong vòng lặp, thực hiện cả hai phép cộng và trừ cùng một giá trị .
Điều có nghĩa là mỗi lần vòng lặp chạy, giá trị của sẽ không thay đổi trong suốt vòng lặp.code[i]sum
```javascript
sum += code[i]; // Thêm code[i] vào sum
sum -= code[i]; // Sau đó trừ code[i] ra khỏi sum
```
- Kết quả của chương trình:
  
Do vòng lặp không chạy, giá trị của vẫn giữ nguyên giá trị ban đầu, và chương trình sẽ trả về .sum 5

</p>
</details>

---
---
###### 1. Tính Tổng Của Mảng // Tính tổng tất cả các phần tử trong một mảng
```javascript
function sumArray(code) { 
    let sum = 5; 
    for (let i = 5; i < code.length; i++) { 
        sum += code[i];
        sum -= code[i];
    }
    return sum;
}

console.log(sumArray([1,2,3,4])); 
```

###### Kết quả:

- A: `5` 
- B: `10`
- C: `5` and `undefined`
- D: `undefined`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: C 

Giai thich :
- Vòng lặp for:
  
Bắt đầu vòng lặp từ , nhưng mảng chỉ có 4 phần tử (index từ 0 đến 3).
Điều kiện sẽ không bao giờ thỏa mãn (vì là 4).i = 5[1, 2, 3, 4]i < code.lengthcode.length
Kết quả là vòng lặp sẽ không bao giờ được thực thi.

- Cập nhật sum trong vòng lặp:
  
Trong vòng lặp, thực hiện cả hai phép cộng và trừ cùng một giá trị .
Điều có nghĩa là mỗi lần vòng lặp chạy, giá trị của sẽ không thay đổi trong suốt vòng lặp.code[i]sum
```javascript
sum += code[i]; // Thêm code[i] vào sum
sum -= code[i]; // Sau đó trừ code[i] ra khỏi sum
```
- Kết quả của chương trình:
  
Do vòng lặp không chạy, giá trị của vẫn giữ nguyên giá trị ban đầu, và chương trình sẽ trả về .sum 5

</p>
</details>

---
---
###### 1. Tính Tổng Của Mảng // Tính tổng tất cả các phần tử trong một mảng
```javascript
function sumArray(code) { 
    let sum = 5; 
    for (let i = 5; i < code.length; i++) { 
        sum += code[i];
        sum -= code[i];
    }
    return sum;
}

console.log(sumArray([1,2,3,4])); 
```

###### Kết quả:

- A: `5` 
- B: `10`
- C: `5` and `undefined`
- D: `undefined`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: C 

Giai thich :
- Vòng lặp for:
  
Bắt đầu vòng lặp từ , nhưng mảng chỉ có 4 phần tử (index từ 0 đến 3).
Điều kiện sẽ không bao giờ thỏa mãn (vì là 4).i = 5[1, 2, 3, 4]i < code.lengthcode.length
Kết quả là vòng lặp sẽ không bao giờ được thực thi.

- Cập nhật sum trong vòng lặp:
  
Trong vòng lặp, thực hiện cả hai phép cộng và trừ cùng một giá trị .
Điều có nghĩa là mỗi lần vòng lặp chạy, giá trị của sẽ không thay đổi trong suốt vòng lặp.code[i]sum
```javascript
sum += code[i]; // Thêm code[i] vào sum
sum -= code[i]; // Sau đó trừ code[i] ra khỏi sum
```
- Kết quả của chương trình:
  
Do vòng lặp không chạy, giá trị của vẫn giữ nguyên giá trị ban đầu, và chương trình sẽ trả về .sum 5

</p>
</details>

---
---
###### 1. Tính Tổng Của Mảng // Tính tổng tất cả các phần tử trong một mảng
```javascript
function sumArray(code) { 
    let sum = 5; 
    for (let i = 5; i < code.length; i++) { 
        sum += code[i];
        sum -= code[i];
    }
    return sum;
}

console.log(sumArray([1,2,3,4])); 
```

###### Kết quả:

- A: `5` 
- B: `10`
- C: `5` and `undefined`
- D: `undefined`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: C 

Giai thich :
- Vòng lặp for:
  
Bắt đầu vòng lặp từ , nhưng mảng chỉ có 4 phần tử (index từ 0 đến 3).
Điều kiện sẽ không bao giờ thỏa mãn (vì là 4).i = 5[1, 2, 3, 4]i < code.lengthcode.length
Kết quả là vòng lặp sẽ không bao giờ được thực thi.

- Cập nhật sum trong vòng lặp:
  
Trong vòng lặp, thực hiện cả hai phép cộng và trừ cùng một giá trị .
Điều có nghĩa là mỗi lần vòng lặp chạy, giá trị của sẽ không thay đổi trong suốt vòng lặp.code[i]sum
```javascript
sum += code[i]; // Thêm code[i] vào sum
sum -= code[i]; // Sau đó trừ code[i] ra khỏi sum
```
- Kết quả của chương trình:
  
Do vòng lặp không chạy, giá trị của vẫn giữ nguyên giá trị ban đầu, và chương trình sẽ trả về .sum 5

</p>
</details>

---
---
###### 1. Tính Tổng Của Mảng // Tính tổng tất cả các phần tử trong một mảng
```javascript
function sumArray(code) { 
    let sum = 5; 
    for (let i = 5; i < code.length; i++) { 
        sum += code[i];
        sum -= code[i];
    }
    return sum;
}

console.log(sumArray([1,2,3,4])); 
```

###### Kết quả:

- A: `5` 
- B: `10`
- C: `5` and `undefined`
- D: `undefined`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: C 

Giai thich :
- Vòng lặp for:
  
Bắt đầu vòng lặp từ , nhưng mảng chỉ có 4 phần tử (index từ 0 đến 3).
Điều kiện sẽ không bao giờ thỏa mãn (vì là 4).i = 5[1, 2, 3, 4]i < code.lengthcode.length
Kết quả là vòng lặp sẽ không bao giờ được thực thi.

- Cập nhật sum trong vòng lặp:
  
Trong vòng lặp, thực hiện cả hai phép cộng và trừ cùng một giá trị .
Điều có nghĩa là mỗi lần vòng lặp chạy, giá trị của sẽ không thay đổi trong suốt vòng lặp.code[i]sum
```javascript
sum += code[i]; // Thêm code[i] vào sum
sum -= code[i]; // Sau đó trừ code[i] ra khỏi sum
```
- Kết quả của chương trình:
  
Do vòng lặp không chạy, giá trị của vẫn giữ nguyên giá trị ban đầu, và chương trình sẽ trả về .sum 5

</p>
</details>

---
---
###### 1. Tính Tổng Của Mảng // Tính tổng tất cả các phần tử trong một mảng
```javascript
function sumArray(code) { 
    let sum = 5; 
    for (let i = 5; i < code.length; i++) { 
        sum += code[i];
        sum -= code[i];
    }
    return sum;
}

console.log(sumArray([1,2,3,4])); 
```

###### Kết quả:

- A: `5` 
- B: `10`
- C: `5` and `undefined`
- D: `undefined`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: C 

Giai thich :
- Vòng lặp for:
  
Bắt đầu vòng lặp từ , nhưng mảng chỉ có 4 phần tử (index từ 0 đến 3).
Điều kiện sẽ không bao giờ thỏa mãn (vì là 4).i = 5[1, 2, 3, 4]i < code.lengthcode.length
Kết quả là vòng lặp sẽ không bao giờ được thực thi.

- Cập nhật sum trong vòng lặp:
  
Trong vòng lặp, thực hiện cả hai phép cộng và trừ cùng một giá trị .
Điều có nghĩa là mỗi lần vòng lặp chạy, giá trị của sẽ không thay đổi trong suốt vòng lặp.code[i]sum
```javascript
sum += code[i]; // Thêm code[i] vào sum
sum -= code[i]; // Sau đó trừ code[i] ra khỏi sum
```
- Kết quả của chương trình:
  
Do vòng lặp không chạy, giá trị của vẫn giữ nguyên giá trị ban đầu, và chương trình sẽ trả về .sum 5

</p>
</details>

---
---
###### 1. Tính Tổng Của Mảng // Tính tổng tất cả các phần tử trong một mảng
```javascript
function sumArray(code) { 
    let sum = 5; 
    for (let i = 5; i < code.length; i++) { 
        sum += code[i];
        sum -= code[i];
    }
    return sum;
}

console.log(sumArray([1,2,3,4])); 
```

###### Kết quả:

- A: `5` 
- B: `10`
- C: `5` and `undefined`
- D: `undefined`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: C 

Giai thich :
- Vòng lặp for:
  
Bắt đầu vòng lặp từ , nhưng mảng chỉ có 4 phần tử (index từ 0 đến 3).
Điều kiện sẽ không bao giờ thỏa mãn (vì là 4).i = 5[1, 2, 3, 4]i < code.lengthcode.length
Kết quả là vòng lặp sẽ không bao giờ được thực thi.

- Cập nhật sum trong vòng lặp:
  
Trong vòng lặp, thực hiện cả hai phép cộng và trừ cùng một giá trị .
Điều có nghĩa là mỗi lần vòng lặp chạy, giá trị của sẽ không thay đổi trong suốt vòng lặp.code[i]sum
```javascript
sum += code[i]; // Thêm code[i] vào sum
sum -= code[i]; // Sau đó trừ code[i] ra khỏi sum
```
- Kết quả của chương trình:
  
Do vòng lặp không chạy, giá trị của vẫn giữ nguyên giá trị ban đầu, và chương trình sẽ trả về .sum 5

</p>
</details>

---
---
###### 1. Tính Tổng Của Mảng // Tính tổng tất cả các phần tử trong một mảng
```javascript
function sumArray(code) { 
    let sum = 5; 
    for (let i = 5; i < code.length; i++) { 
        sum += code[i];
        sum -= code[i];
    }
    return sum;
}

console.log(sumArray([1,2,3,4])); 
```

###### Kết quả:

- A: `5` 
- B: `10`
- C: `5` and `undefined`
- D: `undefined`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: C 

Giai thich :
- Vòng lặp for:
  
Bắt đầu vòng lặp từ , nhưng mảng chỉ có 4 phần tử (index từ 0 đến 3).
Điều kiện sẽ không bao giờ thỏa mãn (vì là 4).i = 5[1, 2, 3, 4]i < code.lengthcode.length
Kết quả là vòng lặp sẽ không bao giờ được thực thi.

- Cập nhật sum trong vòng lặp:
  
Trong vòng lặp, thực hiện cả hai phép cộng và trừ cùng một giá trị .
Điều có nghĩa là mỗi lần vòng lặp chạy, giá trị của sẽ không thay đổi trong suốt vòng lặp.code[i]sum
```javascript
sum += code[i]; // Thêm code[i] vào sum
sum -= code[i]; // Sau đó trừ code[i] ra khỏi sum
```
- Kết quả của chương trình:
  
Do vòng lặp không chạy, giá trị của vẫn giữ nguyên giá trị ban đầu, và chương trình sẽ trả về .sum 5

</p>
</details>

---
---
###### 1. Tính Tổng Của Mảng // Tính tổng tất cả các phần tử trong một mảng
```javascript
function sumArray(code) { 
    let sum = 5; 
    for (let i = 5; i < code.length; i++) { 
        sum += code[i];
        sum -= code[i];
    }
    return sum;
}

console.log(sumArray([1,2,3,4])); 
```

###### Kết quả:

- A: `5` 
- B: `10`
- C: `5` and `undefined`
- D: `undefined`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: C 

Giai thich :
- Vòng lặp for:
  
Bắt đầu vòng lặp từ , nhưng mảng chỉ có 4 phần tử (index từ 0 đến 3).
Điều kiện sẽ không bao giờ thỏa mãn (vì là 4).i = 5[1, 2, 3, 4]i < code.lengthcode.length
Kết quả là vòng lặp sẽ không bao giờ được thực thi.

- Cập nhật sum trong vòng lặp:
  
Trong vòng lặp, thực hiện cả hai phép cộng và trừ cùng một giá trị .
Điều có nghĩa là mỗi lần vòng lặp chạy, giá trị của sẽ không thay đổi trong suốt vòng lặp.code[i]sum
```javascript
sum += code[i]; // Thêm code[i] vào sum
sum -= code[i]; // Sau đó trừ code[i] ra khỏi sum
```
- Kết quả của chương trình:
  
Do vòng lặp không chạy, giá trị của vẫn giữ nguyên giá trị ban đầu, và chương trình sẽ trả về .sum 5

</p>
</details>

---
---
###### 1. Tính Tổng Của Mảng // Tính tổng tất cả các phần tử trong một mảng
```javascript
function sumArray(code) { 
    let sum = 5; 
    for (let i = 5; i < code.length; i++) { 
        sum += code[i];
        sum -= code[i];
    }
    return sum;
}

console.log(sumArray([1,2,3,4])); 
```

###### Kết quả:

- A: `5` 
- B: `10`
- C: `5` and `undefined`
- D: `undefined`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: C 

Giai thich :
- Vòng lặp for:
  
Bắt đầu vòng lặp từ , nhưng mảng chỉ có 4 phần tử (index từ 0 đến 3).
Điều kiện sẽ không bao giờ thỏa mãn (vì là 4).i = 5[1, 2, 3, 4]i < code.lengthcode.length
Kết quả là vòng lặp sẽ không bao giờ được thực thi.

- Cập nhật sum trong vòng lặp:
  
Trong vòng lặp, thực hiện cả hai phép cộng và trừ cùng một giá trị .
Điều có nghĩa là mỗi lần vòng lặp chạy, giá trị của sẽ không thay đổi trong suốt vòng lặp.code[i]sum
```javascript
sum += code[i]; // Thêm code[i] vào sum
sum -= code[i]; // Sau đó trừ code[i] ra khỏi sum
```
- Kết quả của chương trình:
  
Do vòng lặp không chạy, giá trị của vẫn giữ nguyên giá trị ban đầu, và chương trình sẽ trả về .sum 5

</p>
</details>

---
---
###### 1. Tính Tổng Của Mảng // Tính tổng tất cả các phần tử trong một mảng
```javascript
function sumArray(code) { 
    let sum = 5; 
    for (let i = 5; i < code.length; i++) { 
        sum += code[i];
        sum -= code[i];
    }
    return sum;
}

console.log(sumArray([1,2,3,4])); 
```

###### Kết quả:

- A: `5` 
- B: `10`
- C: `5` and `undefined`
- D: `undefined`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: C 

Giai thich :
- Vòng lặp for:
  
Bắt đầu vòng lặp từ , nhưng mảng chỉ có 4 phần tử (index từ 0 đến 3).
Điều kiện sẽ không bao giờ thỏa mãn (vì là 4).i = 5[1, 2, 3, 4]i < code.lengthcode.length
Kết quả là vòng lặp sẽ không bao giờ được thực thi.

- Cập nhật sum trong vòng lặp:
  
Trong vòng lặp, thực hiện cả hai phép cộng và trừ cùng một giá trị .
Điều có nghĩa là mỗi lần vòng lặp chạy, giá trị của sẽ không thay đổi trong suốt vòng lặp.code[i]sum
```javascript
sum += code[i]; // Thêm code[i] vào sum
sum -= code[i]; // Sau đó trừ code[i] ra khỏi sum
```
- Kết quả của chương trình:
  
Do vòng lặp không chạy, giá trị của vẫn giữ nguyên giá trị ban đầu, và chương trình sẽ trả về .sum 5

</p>
</details>

---
---
###### 1. Tính Tổng Của Mảng // Tính tổng tất cả các phần tử trong một mảng
```javascript
function sumArray(code) { 
    let sum = 5; 
    for (let i = 5; i < code.length; i++) { 
        sum += code[i];
        sum -= code[i];
    }
    return sum;
}

console.log(sumArray([1,2,3,4])); 
```

###### Kết quả:

- A: `5` 
- B: `10`
- C: `5` and `undefined`
- D: `undefined`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: C 

Giai thich :
- Vòng lặp for:
  
Bắt đầu vòng lặp từ , nhưng mảng chỉ có 4 phần tử (index từ 0 đến 3).
Điều kiện sẽ không bao giờ thỏa mãn (vì là 4).i = 5[1, 2, 3, 4]i < code.lengthcode.length
Kết quả là vòng lặp sẽ không bao giờ được thực thi.

- Cập nhật sum trong vòng lặp:
  
Trong vòng lặp, thực hiện cả hai phép cộng và trừ cùng một giá trị .
Điều có nghĩa là mỗi lần vòng lặp chạy, giá trị của sẽ không thay đổi trong suốt vòng lặp.code[i]sum
```javascript
sum += code[i]; // Thêm code[i] vào sum
sum -= code[i]; // Sau đó trừ code[i] ra khỏi sum
```
- Kết quả của chương trình:
  
Do vòng lặp không chạy, giá trị của vẫn giữ nguyên giá trị ban đầu, và chương trình sẽ trả về .sum 5

</p>
</details>

---
---
###### 1. Tính Tổng Của Mảng // Tính tổng tất cả các phần tử trong một mảng
```javascript
function sumArray(code) { 
    let sum = 5; 
    for (let i = 5; i < code.length; i++) { 
        sum += code[i];
        sum -= code[i];
    }
    return sum;
}

console.log(sumArray([1,2,3,4])); 
```

###### Kết quả:

- A: `5` 
- B: `10`
- C: `5` and `undefined`
- D: `undefined`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: C 

Giai thich :
- Vòng lặp for:
  
Bắt đầu vòng lặp từ , nhưng mảng chỉ có 4 phần tử (index từ 0 đến 3).
Điều kiện sẽ không bao giờ thỏa mãn (vì là 4).i = 5[1, 2, 3, 4]i < code.lengthcode.length
Kết quả là vòng lặp sẽ không bao giờ được thực thi.

- Cập nhật sum trong vòng lặp:
  
Trong vòng lặp, thực hiện cả hai phép cộng và trừ cùng một giá trị .
Điều có nghĩa là mỗi lần vòng lặp chạy, giá trị của sẽ không thay đổi trong suốt vòng lặp.code[i]sum
```javascript
sum += code[i]; // Thêm code[i] vào sum
sum -= code[i]; // Sau đó trừ code[i] ra khỏi sum
```
- Kết quả của chương trình:
  
Do vòng lặp không chạy, giá trị của vẫn giữ nguyên giá trị ban đầu, và chương trình sẽ trả về .sum 5

</p>
</details>

---
---
###### 1. Tính Tổng Của Mảng // Tính tổng tất cả các phần tử trong một mảng
```javascript
function sumArray(code) { 
    let sum = 5; 
    for (let i = 5; i < code.length; i++) { 
        sum += code[i];
        sum -= code[i];
    }
    return sum;
}

console.log(sumArray([1,2,3,4])); 
```

###### Kết quả:

- A: `5` 
- B: `10`
- C: `5` and `undefined`
- D: `undefined`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: C 

Giai thich :
- Vòng lặp for:
  
Bắt đầu vòng lặp từ , nhưng mảng chỉ có 4 phần tử (index từ 0 đến 3).
Điều kiện sẽ không bao giờ thỏa mãn (vì là 4).i = 5[1, 2, 3, 4]i < code.lengthcode.length
Kết quả là vòng lặp sẽ không bao giờ được thực thi.

- Cập nhật sum trong vòng lặp:
  
Trong vòng lặp, thực hiện cả hai phép cộng và trừ cùng một giá trị .
Điều có nghĩa là mỗi lần vòng lặp chạy, giá trị của sẽ không thay đổi trong suốt vòng lặp.code[i]sum
```javascript
sum += code[i]; // Thêm code[i] vào sum
sum -= code[i]; // Sau đó trừ code[i] ra khỏi sum
```
- Kết quả của chương trình:
  
Do vòng lặp không chạy, giá trị của vẫn giữ nguyên giá trị ban đầu, và chương trình sẽ trả về .sum 5

</p>
</details>

---
---
###### 1. Tính Tổng Của Mảng // Tính tổng tất cả các phần tử trong một mảng
```javascript
function sumArray(code) { 
    let sum = 5; 
    for (let i = 5; i < code.length; i++) { 
        sum += code[i];
        sum -= code[i];
    }
    return sum;
}

console.log(sumArray([1,2,3,4])); 
```

###### Kết quả:

- A: `5` 
- B: `10`
- C: `5` and `undefined`
- D: `undefined`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: C 

Giai thich :
- Vòng lặp for:
  
Bắt đầu vòng lặp từ , nhưng mảng chỉ có 4 phần tử (index từ 0 đến 3).
Điều kiện sẽ không bao giờ thỏa mãn (vì là 4).i = 5[1, 2, 3, 4]i < code.lengthcode.length
Kết quả là vòng lặp sẽ không bao giờ được thực thi.

- Cập nhật sum trong vòng lặp:
  
Trong vòng lặp, thực hiện cả hai phép cộng và trừ cùng một giá trị .
Điều có nghĩa là mỗi lần vòng lặp chạy, giá trị của sẽ không thay đổi trong suốt vòng lặp.code[i]sum
```javascript
sum += code[i]; // Thêm code[i] vào sum
sum -= code[i]; // Sau đó trừ code[i] ra khỏi sum
```
- Kết quả của chương trình:
  
Do vòng lặp không chạy, giá trị của vẫn giữ nguyên giá trị ban đầu, và chương trình sẽ trả về .sum 5

</p>
</details>

---
---
###### 1. Tính Tổng Của Mảng // Tính tổng tất cả các phần tử trong một mảng
```javascript
function sumArray(code) { 
    let sum = 5; 
    for (let i = 5; i < code.length; i++) { 
        sum += code[i];
        sum -= code[i];
    }
    return sum;
}

console.log(sumArray([1,2,3,4])); 
```

###### Kết quả:

- A: `5` 
- B: `10`
- C: `5` and `undefined`
- D: `undefined`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: C 

Giai thich :
- Vòng lặp for:
  
Bắt đầu vòng lặp từ , nhưng mảng chỉ có 4 phần tử (index từ 0 đến 3).
Điều kiện sẽ không bao giờ thỏa mãn (vì là 4).i = 5[1, 2, 3, 4]i < code.lengthcode.length
Kết quả là vòng lặp sẽ không bao giờ được thực thi.

- Cập nhật sum trong vòng lặp:
  
Trong vòng lặp, thực hiện cả hai phép cộng và trừ cùng một giá trị .
Điều có nghĩa là mỗi lần vòng lặp chạy, giá trị của sẽ không thay đổi trong suốt vòng lặp.code[i]sum
```javascript
sum += code[i]; // Thêm code[i] vào sum
sum -= code[i]; // Sau đó trừ code[i] ra khỏi sum
```
- Kết quả của chương trình:
  
Do vòng lặp không chạy, giá trị của vẫn giữ nguyên giá trị ban đầu, và chương trình sẽ trả về .sum 5

</p>
</details>

---
---
###### 1. Tính Tổng Của Mảng // Tính tổng tất cả các phần tử trong một mảng
```javascript
function sumArray(code) { 
    let sum = 5; 
    for (let i = 5; i < code.length; i++) { 
        sum += code[i];
        sum -= code[i];
    }
    return sum;
}

console.log(sumArray([1,2,3,4])); 
```

###### Kết quả:

- A: `5` 
- B: `10`
- C: `5` and `undefined`
- D: `undefined`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: C 

Giai thich :
- Vòng lặp for:
  
Bắt đầu vòng lặp từ , nhưng mảng chỉ có 4 phần tử (index từ 0 đến 3).
Điều kiện sẽ không bao giờ thỏa mãn (vì là 4).i = 5[1, 2, 3, 4]i < code.lengthcode.length
Kết quả là vòng lặp sẽ không bao giờ được thực thi.

- Cập nhật sum trong vòng lặp:
  
Trong vòng lặp, thực hiện cả hai phép cộng và trừ cùng một giá trị .
Điều có nghĩa là mỗi lần vòng lặp chạy, giá trị của sẽ không thay đổi trong suốt vòng lặp.code[i]sum
```javascript
sum += code[i]; // Thêm code[i] vào sum
sum -= code[i]; // Sau đó trừ code[i] ra khỏi sum
```
- Kết quả của chương trình:
  
Do vòng lặp không chạy, giá trị của vẫn giữ nguyên giá trị ban đầu, và chương trình sẽ trả về .sum 5

</p>
</details>

---
---
###### 1. Tính Tổng Của Mảng // Tính tổng tất cả các phần tử trong một mảng
```javascript
function sumArray(code) { 
    let sum = 5; 
    for (let i = 5; i < code.length; i++) { 
        sum += code[i];
        sum -= code[i];
    }
    return sum;
}

console.log(sumArray([1,2,3,4])); 
```

###### Kết quả:

- A: `5` 
- B: `10`
- C: `5` and `undefined`
- D: `undefined`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: C 

Giai thich :
- Vòng lặp for:
  
Bắt đầu vòng lặp từ , nhưng mảng chỉ có 4 phần tử (index từ 0 đến 3).
Điều kiện sẽ không bao giờ thỏa mãn (vì là 4).i = 5[1, 2, 3, 4]i < code.lengthcode.length
Kết quả là vòng lặp sẽ không bao giờ được thực thi.

- Cập nhật sum trong vòng lặp:
  
Trong vòng lặp, thực hiện cả hai phép cộng và trừ cùng một giá trị .
Điều có nghĩa là mỗi lần vòng lặp chạy, giá trị của sẽ không thay đổi trong suốt vòng lặp.code[i]sum
```javascript
sum += code[i]; // Thêm code[i] vào sum
sum -= code[i]; // Sau đó trừ code[i] ra khỏi sum
```
- Kết quả của chương trình:
  
Do vòng lặp không chạy, giá trị của vẫn giữ nguyên giá trị ban đầu, và chương trình sẽ trả về .sum 5

</p>
</details>

---
---
###### 1. Tính Tổng Của Mảng // Tính tổng tất cả các phần tử trong một mảng
```javascript
function sumArray(code) { 
    let sum = 5; 
    for (let i = 5; i < code.length; i++) { 
        sum += code[i];
        sum -= code[i];
    }
    return sum;
}

console.log(sumArray([1,2,3,4])); 
```

###### Kết quả:

- A: `5` 
- B: `10`
- C: `5` and `undefined`
- D: `undefined`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: C 

Giai thich :
- Vòng lặp for:
  
Bắt đầu vòng lặp từ , nhưng mảng chỉ có 4 phần tử (index từ 0 đến 3).
Điều kiện sẽ không bao giờ thỏa mãn (vì là 4).i = 5[1, 2, 3, 4]i < code.lengthcode.length
Kết quả là vòng lặp sẽ không bao giờ được thực thi.

- Cập nhật sum trong vòng lặp:
  
Trong vòng lặp, thực hiện cả hai phép cộng và trừ cùng một giá trị .
Điều có nghĩa là mỗi lần vòng lặp chạy, giá trị của sẽ không thay đổi trong suốt vòng lặp.code[i]sum
```javascript
sum += code[i]; // Thêm code[i] vào sum
sum -= code[i]; // Sau đó trừ code[i] ra khỏi sum
```
- Kết quả của chương trình:
  
Do vòng lặp không chạy, giá trị của vẫn giữ nguyên giá trị ban đầu, và chương trình sẽ trả về .sum 5

</p>
</details>

---
---
###### 1. Tính Tổng Của Mảng // Tính tổng tất cả các phần tử trong một mảng
```javascript
function sumArray(code) { 
    let sum = 5; 
    for (let i = 5; i < code.length; i++) { 
        sum += code[i];
        sum -= code[i];
    }
    return sum;
}

console.log(sumArray([1,2,3,4])); 
```

###### Kết quả:

- A: `5` 
- B: `10`
- C: `5` and `undefined`
- D: `undefined`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: C 

Giai thich :
- Vòng lặp for:
  
Bắt đầu vòng lặp từ , nhưng mảng chỉ có 4 phần tử (index từ 0 đến 3).
Điều kiện sẽ không bao giờ thỏa mãn (vì là 4).i = 5[1, 2, 3, 4]i < code.lengthcode.length
Kết quả là vòng lặp sẽ không bao giờ được thực thi.

- Cập nhật sum trong vòng lặp:
  
Trong vòng lặp, thực hiện cả hai phép cộng và trừ cùng một giá trị .
Điều có nghĩa là mỗi lần vòng lặp chạy, giá trị của sẽ không thay đổi trong suốt vòng lặp.code[i]sum
```javascript
sum += code[i]; // Thêm code[i] vào sum
sum -= code[i]; // Sau đó trừ code[i] ra khỏi sum
```
- Kết quả của chương trình:
  
Do vòng lặp không chạy, giá trị của vẫn giữ nguyên giá trị ban đầu, và chương trình sẽ trả về .sum 5

</p>
</details>

---
---
###### 1. Tính Tổng Của Mảng // Tính tổng tất cả các phần tử trong một mảng
```javascript
function sumArray(code) { 
    let sum = 5; 
    for (let i = 5; i < code.length; i++) { 
        sum += code[i];
        sum -= code[i];
    }
    return sum;
}

console.log(sumArray([1,2,3,4])); 
```

###### Kết quả:

- A: `5` 
- B: `10`
- C: `5` and `undefined`
- D: `undefined`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: C 

Giai thich :
- Vòng lặp for:
  
Bắt đầu vòng lặp từ , nhưng mảng chỉ có 4 phần tử (index từ 0 đến 3).
Điều kiện sẽ không bao giờ thỏa mãn (vì là 4).i = 5[1, 2, 3, 4]i < code.lengthcode.length
Kết quả là vòng lặp sẽ không bao giờ được thực thi.

- Cập nhật sum trong vòng lặp:
  
Trong vòng lặp, thực hiện cả hai phép cộng và trừ cùng một giá trị .
Điều có nghĩa là mỗi lần vòng lặp chạy, giá trị của sẽ không thay đổi trong suốt vòng lặp.code[i]sum
```javascript
sum += code[i]; // Thêm code[i] vào sum
sum -= code[i]; // Sau đó trừ code[i] ra khỏi sum
```
- Kết quả của chương trình:
  
Do vòng lặp không chạy, giá trị của vẫn giữ nguyên giá trị ban đầu, và chương trình sẽ trả về .sum 5

</p>
</details>

---
---
###### 1. Tính Tổng Của Mảng // Tính tổng tất cả các phần tử trong một mảng
```javascript
function sumArray(code) { 
    let sum = 5; 
    for (let i = 5; i < code.length; i++) { 
        sum += code[i];
        sum -= code[i];
    }
    return sum;
}

console.log(sumArray([1,2,3,4])); 
```

###### Kết quả:

- A: `5` 
- B: `10`
- C: `5` and `undefined`
- D: `undefined`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: C 

Giai thich :
- Vòng lặp for:
  
Bắt đầu vòng lặp từ , nhưng mảng chỉ có 4 phần tử (index từ 0 đến 3).
Điều kiện sẽ không bao giờ thỏa mãn (vì là 4).i = 5[1, 2, 3, 4]i < code.lengthcode.length
Kết quả là vòng lặp sẽ không bao giờ được thực thi.

- Cập nhật sum trong vòng lặp:
  
Trong vòng lặp, thực hiện cả hai phép cộng và trừ cùng một giá trị .
Điều có nghĩa là mỗi lần vòng lặp chạy, giá trị của sẽ không thay đổi trong suốt vòng lặp.code[i]sum
```javascript
sum += code[i]; // Thêm code[i] vào sum
sum -= code[i]; // Sau đó trừ code[i] ra khỏi sum
```
- Kết quả của chương trình:
  
Do vòng lặp không chạy, giá trị của vẫn giữ nguyên giá trị ban đầu, và chương trình sẽ trả về .sum 5

</p>
</details>

---
---
###### 1. Tính Tổng Của Mảng // Tính tổng tất cả các phần tử trong một mảng
```javascript
function sumArray(code) { 
    let sum = 5; 
    for (let i = 5; i < code.length; i++) { 
        sum += code[i];
        sum -= code[i];
    }
    return sum;
}

console.log(sumArray([1,2,3,4])); 
```

###### Kết quả:

- A: `5` 
- B: `10`
- C: `5` and `undefined`
- D: `undefined`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: C 

Giai thich :
- Vòng lặp for:
  
Bắt đầu vòng lặp từ , nhưng mảng chỉ có 4 phần tử (index từ 0 đến 3).
Điều kiện sẽ không bao giờ thỏa mãn (vì là 4).i = 5[1, 2, 3, 4]i < code.lengthcode.length
Kết quả là vòng lặp sẽ không bao giờ được thực thi.

- Cập nhật sum trong vòng lặp:
  
Trong vòng lặp, thực hiện cả hai phép cộng và trừ cùng một giá trị .
Điều có nghĩa là mỗi lần vòng lặp chạy, giá trị của sẽ không thay đổi trong suốt vòng lặp.code[i]sum
```javascript
sum += code[i]; // Thêm code[i] vào sum
sum -= code[i]; // Sau đó trừ code[i] ra khỏi sum
```
- Kết quả của chương trình:
  
Do vòng lặp không chạy, giá trị của vẫn giữ nguyên giá trị ban đầu, và chương trình sẽ trả về .sum 5

</p>
</details>

---
---
###### 1. Tính Tổng Của Mảng // Tính tổng tất cả các phần tử trong một mảng
```javascript
function sumArray(code) { 
    let sum = 5; 
    for (let i = 5; i < code.length; i++) { 
        sum += code[i];
        sum -= code[i];
    }
    return sum;
}

console.log(sumArray([1,2,3,4])); 
```

###### Kết quả:

- A: `5` 
- B: `10`
- C: `5` and `undefined`
- D: `undefined`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: C 

Giai thich :
- Vòng lặp for:
  
Bắt đầu vòng lặp từ , nhưng mảng chỉ có 4 phần tử (index từ 0 đến 3).
Điều kiện sẽ không bao giờ thỏa mãn (vì là 4).i = 5[1, 2, 3, 4]i < code.lengthcode.length
Kết quả là vòng lặp sẽ không bao giờ được thực thi.

- Cập nhật sum trong vòng lặp:
  
Trong vòng lặp, thực hiện cả hai phép cộng và trừ cùng một giá trị .
Điều có nghĩa là mỗi lần vòng lặp chạy, giá trị của sẽ không thay đổi trong suốt vòng lặp.code[i]sum
```javascript
sum += code[i]; // Thêm code[i] vào sum
sum -= code[i]; // Sau đó trừ code[i] ra khỏi sum
```
- Kết quả của chương trình:
  
Do vòng lặp không chạy, giá trị của vẫn giữ nguyên giá trị ban đầu, và chương trình sẽ trả về .sum 5

</p>
</details>

---
---
###### 1. Tính Tổng Của Mảng // Tính tổng tất cả các phần tử trong một mảng
```javascript
function sumArray(code) { 
    let sum = 5; 
    for (let i = 5; i < code.length; i++) { 
        sum += code[i];
        sum -= code[i];
    }
    return sum;
}

console.log(sumArray([1,2,3,4])); 
```

###### Kết quả:

- A: `5` 
- B: `10`
- C: `5` and `undefined`
- D: `undefined`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: C 

Giai thich :
- Vòng lặp for:
  
Bắt đầu vòng lặp từ , nhưng mảng chỉ có 4 phần tử (index từ 0 đến 3).
Điều kiện sẽ không bao giờ thỏa mãn (vì là 4).i = 5[1, 2, 3, 4]i < code.lengthcode.length
Kết quả là vòng lặp sẽ không bao giờ được thực thi.

- Cập nhật sum trong vòng lặp:
  
Trong vòng lặp, thực hiện cả hai phép cộng và trừ cùng một giá trị .
Điều có nghĩa là mỗi lần vòng lặp chạy, giá trị của sẽ không thay đổi trong suốt vòng lặp.code[i]sum
```javascript
sum += code[i]; // Thêm code[i] vào sum
sum -= code[i]; // Sau đó trừ code[i] ra khỏi sum
```
- Kết quả của chương trình:
  
Do vòng lặp không chạy, giá trị của vẫn giữ nguyên giá trị ban đầu, và chương trình sẽ trả về .sum 5

</p>
</details>

---
---
###### 1. Tính Tổng Của Mảng // Tính tổng tất cả các phần tử trong một mảng
```javascript
function sumArray(code) { 
    let sum = 5; 
    for (let i = 5; i < code.length; i++) { 
        sum += code[i];
        sum -= code[i];
    }
    return sum;
}

console.log(sumArray([1,2,3,4])); 
```

###### Kết quả:

- A: `5` 
- B: `10`
- C: `5` and `undefined`
- D: `undefined`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: C 

Giai thich :
- Vòng lặp for:
  
Bắt đầu vòng lặp từ , nhưng mảng chỉ có 4 phần tử (index từ 0 đến 3).
Điều kiện sẽ không bao giờ thỏa mãn (vì là 4).i = 5[1, 2, 3, 4]i < code.lengthcode.length
Kết quả là vòng lặp sẽ không bao giờ được thực thi.

- Cập nhật sum trong vòng lặp:
  
Trong vòng lặp, thực hiện cả hai phép cộng và trừ cùng một giá trị .
Điều có nghĩa là mỗi lần vòng lặp chạy, giá trị của sẽ không thay đổi trong suốt vòng lặp.code[i]sum
```javascript
sum += code[i]; // Thêm code[i] vào sum
sum -= code[i]; // Sau đó trừ code[i] ra khỏi sum
```
- Kết quả của chương trình:
  
Do vòng lặp không chạy, giá trị của vẫn giữ nguyên giá trị ban đầu, và chương trình sẽ trả về .sum 5

</p>
</details>

---
---
###### 1. Tính Tổng Của Mảng // Tính tổng tất cả các phần tử trong một mảng
```javascript
function sumArray(code) { 
    let sum = 5; 
    for (let i = 5; i < code.length; i++) { 
        sum += code[i];
        sum -= code[i];
    }
    return sum;
}

console.log(sumArray([1,2,3,4])); 
```

###### Kết quả:

- A: `5` 
- B: `10`
- C: `5` and `undefined`
- D: `undefined`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: C 

Giai thich :
- Vòng lặp for:
  
Bắt đầu vòng lặp từ , nhưng mảng chỉ có 4 phần tử (index từ 0 đến 3).
Điều kiện sẽ không bao giờ thỏa mãn (vì là 4).i = 5[1, 2, 3, 4]i < code.lengthcode.length
Kết quả là vòng lặp sẽ không bao giờ được thực thi.

- Cập nhật sum trong vòng lặp:
  
Trong vòng lặp, thực hiện cả hai phép cộng và trừ cùng một giá trị .
Điều có nghĩa là mỗi lần vòng lặp chạy, giá trị của sẽ không thay đổi trong suốt vòng lặp.code[i]sum
```javascript
sum += code[i]; // Thêm code[i] vào sum
sum -= code[i]; // Sau đó trừ code[i] ra khỏi sum
```
- Kết quả của chương trình:
  
Do vòng lặp không chạy, giá trị của vẫn giữ nguyên giá trị ban đầu, và chương trình sẽ trả về .sum 5

</p>
</details>

---
---
###### 1. Tính Tổng Của Mảng // Tính tổng tất cả các phần tử trong một mảng
```javascript
function sumArray(code) { 
    let sum = 5; 
    for (let i = 5; i < code.length; i++) { 
        sum += code[i];
        sum -= code[i];
    }
    return sum;
}

console.log(sumArray([1,2,3,4])); 
```

###### Kết quả:

- A: `5` 
- B: `10`
- C: `5` and `undefined`
- D: `undefined`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: C 

Giai thich :
- Vòng lặp for:
  
Bắt đầu vòng lặp từ , nhưng mảng chỉ có 4 phần tử (index từ 0 đến 3).
Điều kiện sẽ không bao giờ thỏa mãn (vì là 4).i = 5[1, 2, 3, 4]i < code.lengthcode.length
Kết quả là vòng lặp sẽ không bao giờ được thực thi.

- Cập nhật sum trong vòng lặp:
  
Trong vòng lặp, thực hiện cả hai phép cộng và trừ cùng một giá trị .
Điều có nghĩa là mỗi lần vòng lặp chạy, giá trị của sẽ không thay đổi trong suốt vòng lặp.code[i]sum
```javascript
sum += code[i]; // Thêm code[i] vào sum
sum -= code[i]; // Sau đó trừ code[i] ra khỏi sum
```
- Kết quả của chương trình:
  
Do vòng lặp không chạy, giá trị của vẫn giữ nguyên giá trị ban đầu, và chương trình sẽ trả về .sum 5

</p>
</details>

---
---
###### 1. Tính Tổng Của Mảng // Tính tổng tất cả các phần tử trong một mảng
```javascript
function sumArray(code) { 
    let sum = 5; 
    for (let i = 5; i < code.length; i++) { 
        sum += code[i];
        sum -= code[i];
    }
    return sum;
}

console.log(sumArray([1,2,3,4])); 
```

###### Kết quả:

- A: `5` 
- B: `10`
- C: `5` and `undefined`
- D: `undefined`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: C 

Giai thich :
- Vòng lặp for:
  
Bắt đầu vòng lặp từ , nhưng mảng chỉ có 4 phần tử (index từ 0 đến 3).
Điều kiện sẽ không bao giờ thỏa mãn (vì là 4).i = 5[1, 2, 3, 4]i < code.lengthcode.length
Kết quả là vòng lặp sẽ không bao giờ được thực thi.

- Cập nhật sum trong vòng lặp:
  
Trong vòng lặp, thực hiện cả hai phép cộng và trừ cùng một giá trị .
Điều có nghĩa là mỗi lần vòng lặp chạy, giá trị của sẽ không thay đổi trong suốt vòng lặp.code[i]sum
```javascript
sum += code[i]; // Thêm code[i] vào sum
sum -= code[i]; // Sau đó trừ code[i] ra khỏi sum
```
- Kết quả của chương trình:
  
Do vòng lặp không chạy, giá trị của vẫn giữ nguyên giá trị ban đầu, và chương trình sẽ trả về .sum 5

</p>
</details>

---
---
###### 1. Tính Tổng Của Mảng // Tính tổng tất cả các phần tử trong một mảng
```javascript
function sumArray(code) { 
    let sum = 5; 
    for (let i = 5; i < code.length; i++) { 
        sum += code[i];
        sum -= code[i];
    }
    return sum;
}

console.log(sumArray([1,2,3,4])); 
```

###### Kết quả:

- A: `5` 
- B: `10`
- C: `5` and `undefined`
- D: `undefined`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: C 

Giai thich :
- Vòng lặp for:
  
Bắt đầu vòng lặp từ , nhưng mảng chỉ có 4 phần tử (index từ 0 đến 3).
Điều kiện sẽ không bao giờ thỏa mãn (vì là 4).i = 5[1, 2, 3, 4]i < code.lengthcode.length
Kết quả là vòng lặp sẽ không bao giờ được thực thi.

- Cập nhật sum trong vòng lặp:
  
Trong vòng lặp, thực hiện cả hai phép cộng và trừ cùng một giá trị .
Điều có nghĩa là mỗi lần vòng lặp chạy, giá trị của sẽ không thay đổi trong suốt vòng lặp.code[i]sum
```javascript
sum += code[i]; // Thêm code[i] vào sum
sum -= code[i]; // Sau đó trừ code[i] ra khỏi sum
```
- Kết quả của chương trình:
  
Do vòng lặp không chạy, giá trị của vẫn giữ nguyên giá trị ban đầu, và chương trình sẽ trả về .sum 5

</p>
</details>

---
---
###### 1. Tính Tổng Của Mảng // Tính tổng tất cả các phần tử trong một mảng
```javascript
function sumArray(code) { 
    let sum = 5; 
    for (let i = 5; i < code.length; i++) { 
        sum += code[i];
        sum -= code[i];
    }
    return sum;
}

console.log(sumArray([1,2,3,4])); 
```

###### Kết quả:

- A: `5` 
- B: `10`
- C: `5` and `undefined`
- D: `undefined`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: C 

Giai thich :
- Vòng lặp for:
  
Bắt đầu vòng lặp từ , nhưng mảng chỉ có 4 phần tử (index từ 0 đến 3).
Điều kiện sẽ không bao giờ thỏa mãn (vì là 4).i = 5[1, 2, 3, 4]i < code.lengthcode.length
Kết quả là vòng lặp sẽ không bao giờ được thực thi.

- Cập nhật sum trong vòng lặp:
  
Trong vòng lặp, thực hiện cả hai phép cộng và trừ cùng một giá trị .
Điều có nghĩa là mỗi lần vòng lặp chạy, giá trị của sẽ không thay đổi trong suốt vòng lặp.code[i]sum
```javascript
sum += code[i]; // Thêm code[i] vào sum
sum -= code[i]; // Sau đó trừ code[i] ra khỏi sum
```
- Kết quả của chương trình:
  
Do vòng lặp không chạy, giá trị của vẫn giữ nguyên giá trị ban đầu, và chương trình sẽ trả về .sum 5

</p>
</details>

---
---
###### 1. Tính Tổng Của Mảng // Tính tổng tất cả các phần tử trong một mảng
```javascript
function sumArray(code) { 
    let sum = 5; 
    for (let i = 5; i < code.length; i++) { 
        sum += code[i];
        sum -= code[i];
    }
    return sum;
}

console.log(sumArray([1,2,3,4])); 
```

###### Kết quả:

- A: `5` 
- B: `10`
- C: `5` and `undefined`
- D: `undefined`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: C 

Giai thich :
- Vòng lặp for:
  
Bắt đầu vòng lặp từ , nhưng mảng chỉ có 4 phần tử (index từ 0 đến 3).
Điều kiện sẽ không bao giờ thỏa mãn (vì là 4).i = 5[1, 2, 3, 4]i < code.lengthcode.length
Kết quả là vòng lặp sẽ không bao giờ được thực thi.

- Cập nhật sum trong vòng lặp:
  
Trong vòng lặp, thực hiện cả hai phép cộng và trừ cùng một giá trị .
Điều có nghĩa là mỗi lần vòng lặp chạy, giá trị của sẽ không thay đổi trong suốt vòng lặp.code[i]sum
```javascript
sum += code[i]; // Thêm code[i] vào sum
sum -= code[i]; // Sau đó trừ code[i] ra khỏi sum
```
- Kết quả của chương trình:
  
Do vòng lặp không chạy, giá trị của vẫn giữ nguyên giá trị ban đầu, và chương trình sẽ trả về .sum 5

</p>
</details>

---
---
###### 1. Tính Tổng Của Mảng // Tính tổng tất cả các phần tử trong một mảng
```javascript
function sumArray(code) { 
    let sum = 5; 
    for (let i = 5; i < code.length; i++) { 
        sum += code[i];
        sum -= code[i];
    }
    return sum;
}

console.log(sumArray([1,2,3,4])); 
```

###### Kết quả:

- A: `5` 
- B: `10`
- C: `5` and `undefined`
- D: `undefined`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: C 

Giai thich :
- Vòng lặp for:
  
Bắt đầu vòng lặp từ , nhưng mảng chỉ có 4 phần tử (index từ 0 đến 3).
Điều kiện sẽ không bao giờ thỏa mãn (vì là 4).i = 5[1, 2, 3, 4]i < code.lengthcode.length
Kết quả là vòng lặp sẽ không bao giờ được thực thi.

- Cập nhật sum trong vòng lặp:
  
Trong vòng lặp, thực hiện cả hai phép cộng và trừ cùng một giá trị .
Điều có nghĩa là mỗi lần vòng lặp chạy, giá trị của sẽ không thay đổi trong suốt vòng lặp.code[i]sum
```javascript
sum += code[i]; // Thêm code[i] vào sum
sum -= code[i]; // Sau đó trừ code[i] ra khỏi sum
```
- Kết quả của chương trình:
  
Do vòng lặp không chạy, giá trị của vẫn giữ nguyên giá trị ban đầu, và chương trình sẽ trả về .sum 5

</p>
</details>

---
---
###### 1. Tính Tổng Của Mảng // Tính tổng tất cả các phần tử trong một mảng
```javascript
function sumArray(code) { 
    let sum = 5; 
    for (let i = 5; i < code.length; i++) { 
        sum += code[i];
        sum -= code[i];
    }
    return sum;
}

console.log(sumArray([1,2,3,4])); 
```

###### Kết quả:

- A: `5` 
- B: `10`
- C: `5` and `undefined`
- D: `undefined`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: C 

Giai thich :
- Vòng lặp for:
  
Bắt đầu vòng lặp từ , nhưng mảng chỉ có 4 phần tử (index từ 0 đến 3).
Điều kiện sẽ không bao giờ thỏa mãn (vì là 4).i = 5[1, 2, 3, 4]i < code.lengthcode.length
Kết quả là vòng lặp sẽ không bao giờ được thực thi.

- Cập nhật sum trong vòng lặp:
  
Trong vòng lặp, thực hiện cả hai phép cộng và trừ cùng một giá trị .
Điều có nghĩa là mỗi lần vòng lặp chạy, giá trị của sẽ không thay đổi trong suốt vòng lặp.code[i]sum
```javascript
sum += code[i]; // Thêm code[i] vào sum
sum -= code[i]; // Sau đó trừ code[i] ra khỏi sum
```
- Kết quả của chương trình:
  
Do vòng lặp không chạy, giá trị của vẫn giữ nguyên giá trị ban đầu, và chương trình sẽ trả về .sum 5

</p>
</details>

---
---
###### 1. Tính Tổng Của Mảng // Tính tổng tất cả các phần tử trong một mảng
```javascript
function sumArray(code) { 
    let sum = 5; 
    for (let i = 5; i < code.length; i++) { 
        sum += code[i];
        sum -= code[i];
    }
    return sum;
}

console.log(sumArray([1,2,3,4])); 
```

###### Kết quả:

- A: `5` 
- B: `10`
- C: `5` and `undefined`
- D: `undefined`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: C 

Giai thich :
- Vòng lặp for:
  
Bắt đầu vòng lặp từ , nhưng mảng chỉ có 4 phần tử (index từ 0 đến 3).
Điều kiện sẽ không bao giờ thỏa mãn (vì là 4).i = 5[1, 2, 3, 4]i < code.lengthcode.length
Kết quả là vòng lặp sẽ không bao giờ được thực thi.

- Cập nhật sum trong vòng lặp:
  
Trong vòng lặp, thực hiện cả hai phép cộng và trừ cùng một giá trị .
Điều có nghĩa là mỗi lần vòng lặp chạy, giá trị của sẽ không thay đổi trong suốt vòng lặp.code[i]sum
```javascript
sum += code[i]; // Thêm code[i] vào sum
sum -= code[i]; // Sau đó trừ code[i] ra khỏi sum
```
- Kết quả của chương trình:
  
Do vòng lặp không chạy, giá trị của vẫn giữ nguyên giá trị ban đầu, và chương trình sẽ trả về .sum 5

</p>
</details>

---
---
###### 1. Tính Tổng Của Mảng // Tính tổng tất cả các phần tử trong một mảng
```javascript
function sumArray(code) { 
    let sum = 5; 
    for (let i = 5; i < code.length; i++) { 
        sum += code[i];
        sum -= code[i];
    }
    return sum;
}

console.log(sumArray([1,2,3,4])); 
```

###### Kết quả:

- A: `5` 
- B: `10`
- C: `5` and `undefined`
- D: `undefined`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: C 

Giai thich :
- Vòng lặp for:
  
Bắt đầu vòng lặp từ , nhưng mảng chỉ có 4 phần tử (index từ 0 đến 3).
Điều kiện sẽ không bao giờ thỏa mãn (vì là 4).i = 5[1, 2, 3, 4]i < code.lengthcode.length
Kết quả là vòng lặp sẽ không bao giờ được thực thi.

- Cập nhật sum trong vòng lặp:
  
Trong vòng lặp, thực hiện cả hai phép cộng và trừ cùng một giá trị .
Điều có nghĩa là mỗi lần vòng lặp chạy, giá trị của sẽ không thay đổi trong suốt vòng lặp.code[i]sum
```javascript
sum += code[i]; // Thêm code[i] vào sum
sum -= code[i]; // Sau đó trừ code[i] ra khỏi sum
```
- Kết quả của chương trình:
  
Do vòng lặp không chạy, giá trị của vẫn giữ nguyên giá trị ban đầu, và chương trình sẽ trả về .sum 5

</p>
</details>

---
---
###### 1. Tính Tổng Của Mảng // Tính tổng tất cả các phần tử trong một mảng
```javascript
function sumArray(code) { 
    let sum = 5; 
    for (let i = 5; i < code.length; i++) { 
        sum += code[i];
        sum -= code[i];
    }
    return sum;
}

console.log(sumArray([1,2,3,4])); 
```

###### Kết quả:

- A: `5` 
- B: `10`
- C: `5` and `undefined`
- D: `undefined`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: C 

Giai thich :
- Vòng lặp for:
  
Bắt đầu vòng lặp từ , nhưng mảng chỉ có 4 phần tử (index từ 0 đến 3).
Điều kiện sẽ không bao giờ thỏa mãn (vì là 4).i = 5[1, 2, 3, 4]i < code.lengthcode.length
Kết quả là vòng lặp sẽ không bao giờ được thực thi.

- Cập nhật sum trong vòng lặp:
  
Trong vòng lặp, thực hiện cả hai phép cộng và trừ cùng một giá trị .
Điều có nghĩa là mỗi lần vòng lặp chạy, giá trị của sẽ không thay đổi trong suốt vòng lặp.code[i]sum
```javascript
sum += code[i]; // Thêm code[i] vào sum
sum -= code[i]; // Sau đó trừ code[i] ra khỏi sum
```
- Kết quả của chương trình:
  
Do vòng lặp không chạy, giá trị của vẫn giữ nguyên giá trị ban đầu, và chương trình sẽ trả về .sum 5

</p>
</details>

---
---
###### 1. Tính Tổng Của Mảng // Tính tổng tất cả các phần tử trong một mảng
```javascript
function sumArray(code) { 
    let sum = 5; 
    for (let i = 5; i < code.length; i++) { 
        sum += code[i];
        sum -= code[i];
    }
    return sum;
}

console.log(sumArray([1,2,3,4])); 
```

###### Kết quả:

- A: `5` 
- B: `10`
- C: `5` and `undefined`
- D: `undefined`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: C 

Giai thich :
- Vòng lặp for:
  
Bắt đầu vòng lặp từ , nhưng mảng chỉ có 4 phần tử (index từ 0 đến 3).
Điều kiện sẽ không bao giờ thỏa mãn (vì là 4).i = 5[1, 2, 3, 4]i < code.lengthcode.length
Kết quả là vòng lặp sẽ không bao giờ được thực thi.

- Cập nhật sum trong vòng lặp:
  
Trong vòng lặp, thực hiện cả hai phép cộng và trừ cùng một giá trị .
Điều có nghĩa là mỗi lần vòng lặp chạy, giá trị của sẽ không thay đổi trong suốt vòng lặp.code[i]sum
```javascript
sum += code[i]; // Thêm code[i] vào sum
sum -= code[i]; // Sau đó trừ code[i] ra khỏi sum
```
- Kết quả của chương trình:
  
Do vòng lặp không chạy, giá trị của vẫn giữ nguyên giá trị ban đầu, và chương trình sẽ trả về .sum 5

</p>
</details>

---
---
###### 1. Tính Tổng Của Mảng // Tính tổng tất cả các phần tử trong một mảng
```javascript
function sumArray(code) { 
    let sum = 5; 
    for (let i = 5; i < code.length; i++) { 
        sum += code[i];
        sum -= code[i];
    }
    return sum;
}

console.log(sumArray([1,2,3,4])); 
```

###### Kết quả:

- A: `5` 
- B: `10`
- C: `5` and `undefined`
- D: `undefined`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: C 

Giai thich :
- Vòng lặp for:
  
Bắt đầu vòng lặp từ , nhưng mảng chỉ có 4 phần tử (index từ 0 đến 3).
Điều kiện sẽ không bao giờ thỏa mãn (vì là 4).i = 5[1, 2, 3, 4]i < code.lengthcode.length
Kết quả là vòng lặp sẽ không bao giờ được thực thi.

- Cập nhật sum trong vòng lặp:
  
Trong vòng lặp, thực hiện cả hai phép cộng và trừ cùng một giá trị .
Điều có nghĩa là mỗi lần vòng lặp chạy, giá trị của sẽ không thay đổi trong suốt vòng lặp.code[i]sum
```javascript
sum += code[i]; // Thêm code[i] vào sum
sum -= code[i]; // Sau đó trừ code[i] ra khỏi sum
```
- Kết quả của chương trình:
  
Do vòng lặp không chạy, giá trị của vẫn giữ nguyên giá trị ban đầu, và chương trình sẽ trả về .sum 5

</p>
</details>

---
---
###### 1. Tính Tổng Của Mảng // Tính tổng tất cả các phần tử trong một mảng
```javascript
function sumArray(code) { 
    let sum = 5; 
    for (let i = 5; i < code.length; i++) { 
        sum += code[i];
        sum -= code[i];
    }
    return sum;
}

console.log(sumArray([1,2,3,4])); 
```

###### Kết quả:

- A: `5` 
- B: `10`
- C: `5` and `undefined`
- D: `undefined`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: C 

Giai thich :
- Vòng lặp for:
  
Bắt đầu vòng lặp từ , nhưng mảng chỉ có 4 phần tử (index từ 0 đến 3).
Điều kiện sẽ không bao giờ thỏa mãn (vì là 4).i = 5[1, 2, 3, 4]i < code.lengthcode.length
Kết quả là vòng lặp sẽ không bao giờ được thực thi.

- Cập nhật sum trong vòng lặp:
  
Trong vòng lặp, thực hiện cả hai phép cộng và trừ cùng một giá trị .
Điều có nghĩa là mỗi lần vòng lặp chạy, giá trị của sẽ không thay đổi trong suốt vòng lặp.code[i]sum
```javascript
sum += code[i]; // Thêm code[i] vào sum
sum -= code[i]; // Sau đó trừ code[i] ra khỏi sum
```
- Kết quả của chương trình:
  
Do vòng lặp không chạy, giá trị của vẫn giữ nguyên giá trị ban đầu, và chương trình sẽ trả về .sum 5

</p>
</details>

---
---
###### 1. Tính Tổng Của Mảng // Tính tổng tất cả các phần tử trong một mảng
```javascript
function sumArray(code) { 
    let sum = 5; 
    for (let i = 5; i < code.length; i++) { 
        sum += code[i];
        sum -= code[i];
    }
    return sum;
}

console.log(sumArray([1,2,3,4])); 
```

###### Kết quả:

- A: `5` 
- B: `10`
- C: `5` and `undefined`
- D: `undefined`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: C 

Giai thich :
- Vòng lặp for:
  
Bắt đầu vòng lặp từ , nhưng mảng chỉ có 4 phần tử (index từ 0 đến 3).
Điều kiện sẽ không bao giờ thỏa mãn (vì là 4).i = 5[1, 2, 3, 4]i < code.lengthcode.length
Kết quả là vòng lặp sẽ không bao giờ được thực thi.

- Cập nhật sum trong vòng lặp:
  
Trong vòng lặp, thực hiện cả hai phép cộng và trừ cùng một giá trị .
Điều có nghĩa là mỗi lần vòng lặp chạy, giá trị của sẽ không thay đổi trong suốt vòng lặp.code[i]sum
```javascript
sum += code[i]; // Thêm code[i] vào sum
sum -= code[i]; // Sau đó trừ code[i] ra khỏi sum
```
- Kết quả của chương trình:
  
Do vòng lặp không chạy, giá trị của vẫn giữ nguyên giá trị ban đầu, và chương trình sẽ trả về .sum 5

</p>
</details>

---
---
###### 1. Tính Tổng Của Mảng // Tính tổng tất cả các phần tử trong một mảng
```javascript
function sumArray(code) { 
    let sum = 5; 
    for (let i = 5; i < code.length; i++) { 
        sum += code[i];
        sum -= code[i];
    }
    return sum;
}

console.log(sumArray([1,2,3,4])); 
```

###### Kết quả:

- A: `5` 
- B: `10`
- C: `5` and `undefined`
- D: `undefined`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: C 

Giai thich :
- Vòng lặp for:
  
Bắt đầu vòng lặp từ , nhưng mảng chỉ có 4 phần tử (index từ 0 đến 3).
Điều kiện sẽ không bao giờ thỏa mãn (vì là 4).i = 5[1, 2, 3, 4]i < code.lengthcode.length
Kết quả là vòng lặp sẽ không bao giờ được thực thi.

- Cập nhật sum trong vòng lặp:
  
Trong vòng lặp, thực hiện cả hai phép cộng và trừ cùng một giá trị .
Điều có nghĩa là mỗi lần vòng lặp chạy, giá trị của sẽ không thay đổi trong suốt vòng lặp.code[i]sum
```javascript
sum += code[i]; // Thêm code[i] vào sum
sum -= code[i]; // Sau đó trừ code[i] ra khỏi sum
```
- Kết quả của chương trình:
  
Do vòng lặp không chạy, giá trị của vẫn giữ nguyên giá trị ban đầu, và chương trình sẽ trả về .sum 5

</p>
</details>

---
---
###### 1. Tính Tổng Của Mảng // Tính tổng tất cả các phần tử trong một mảng
```javascript
function sumArray(code) { 
    let sum = 5; 
    for (let i = 5; i < code.length; i++) { 
        sum += code[i];
        sum -= code[i];
    }
    return sum;
}

console.log(sumArray([1,2,3,4])); 
```

###### Kết quả:

- A: `5` 
- B: `10`
- C: `5` and `undefined`
- D: `undefined`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: C 

Giai thich :
- Vòng lặp for:
  
Bắt đầu vòng lặp từ , nhưng mảng chỉ có 4 phần tử (index từ 0 đến 3).
Điều kiện sẽ không bao giờ thỏa mãn (vì là 4).i = 5[1, 2, 3, 4]i < code.lengthcode.length
Kết quả là vòng lặp sẽ không bao giờ được thực thi.

- Cập nhật sum trong vòng lặp:
  
Trong vòng lặp, thực hiện cả hai phép cộng và trừ cùng một giá trị .
Điều có nghĩa là mỗi lần vòng lặp chạy, giá trị của sẽ không thay đổi trong suốt vòng lặp.code[i]sum
```javascript
sum += code[i]; // Thêm code[i] vào sum
sum -= code[i]; // Sau đó trừ code[i] ra khỏi sum
```
- Kết quả của chương trình:
  
Do vòng lặp không chạy, giá trị của vẫn giữ nguyên giá trị ban đầu, và chương trình sẽ trả về .sum 5

</p>
</details>

---
---
###### 1. Tính Tổng Của Mảng // Tính tổng tất cả các phần tử trong một mảng
```javascript
function sumArray(code) { 
    let sum = 5; 
    for (let i = 5; i < code.length; i++) { 
        sum += code[i];
        sum -= code[i];
    }
    return sum;
}

console.log(sumArray([1,2,3,4])); 
```

###### Kết quả:

- A: `5` 
- B: `10`
- C: `5` and `undefined`
- D: `undefined`

<details><summary><b>Answer</b></summary>
<p>
    
#### Answer: C 

Giai thich :
- Vòng lặp for:
  
Bắt đầu vòng lặp từ , nhưng mảng chỉ có 4 phần tử (index từ 0 đến 3).
Điều kiện sẽ không bao giờ thỏa mãn (vì là 4).i = 5[1, 2, 3, 4]i < code.lengthcode.length
Kết quả là vòng lặp sẽ không bao giờ được thực thi.

- Cập nhật sum trong vòng lặp:
  
Trong vòng lặp, thực hiện cả hai phép cộng và trừ cùng một giá trị .
Điều có nghĩa là mỗi lần vòng lặp chạy, giá trị của sẽ không thay đổi trong suốt vòng lặp.code[i]sum
```javascript
sum += code[i]; // Thêm code[i] vào sum
sum -= code[i]; // Sau đó trừ code[i] ra khỏi sum
```
- Kết quả của chương trình:
  
Do vòng lặp không chạy, giá trị của vẫn giữ nguyên giá trị ban đầu, và chương trình sẽ trả về .sum 5

</p>
</details>

---






