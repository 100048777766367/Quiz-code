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



1. Tìm số lớn nhất trong mảng
Tìm số lớn nhất trong một mảng số nguyên.

javascript
Sao chép
Chỉnh sửa
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
Kết quả:
A: 9
B: 5
C: undefined
D: 1
<details><summary><b>Answer</b></summary> <p>
Đáp án đúng: C

Giải thích:

Trong vòng lặp, thay vì sử dụng max = arr[i], mã nguồn lại viết max == arr[i], đây là toán tử so sánh chứ không phải gán.
Do đó, max không bao giờ thay đổi giá trị ban đầu, nên kết quả trả về là undefined.
</p> </details>
2. Kiểm tra số nguyên tố
Kiểm tra xem một số nguyên có phải là số nguyên tố hay không.

javascript
Sao chép
Chỉnh sửa
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
Kết quả:
A: true
B: false
C: undefined
D: null
<details><summary><b>Answer</b></summary> <p>
Đáp án đúng: B

Giải thích:

Điều kiện vòng lặp i < Math.sqrt(n) là sai, phải là i <= Math.sqrt(n).
Do đó, nó có thể bỏ sót một số số chia hết, gây ra kết quả sai.
</p> </details>
3. Đảo ngược chuỗi
Viết hàm đảo ngược một chuỗi.

javascript
Sao chép
Chỉnh sửa
function reverseString(str) {
    return str.split("").reverse().join;
}

console.log(reverseString("hello"));
Kết quả:
A: "olleh"
B: "hello"
C: function join() { [native code] }
D: TypeError
<details><summary><b>Answer</b></summary> <p>
Đáp án đúng: C

Giải thích:

join phải được gọi với () như join().
Nếu không, nó trả về chính hàm join, không phải chuỗi đảo ngược.
</p> </details>
4. Tính giai thừa
Tính giai thừa của một số nguyên.

javascript
Sao chép
Chỉnh sửa
function factorial(n) {
    if (n === 0) return 1;
    return n * factorial(n--);
}

console.log(factorial(5));
Kết quả:
A: 120
B: Error
C: NaN
D: Infinity
<details><summary><b>Answer</b></summary> <p>
Đáp án đúng: B

Giải thích:

n-- không làm thay đổi giá trị của n trong lời gọi đệ quy.
Phải viết là factorial(n - 1).
</p> </details>
5. Tìm phần tử xuất hiện nhiều nhất trong mảng
Tìm phần tử xuất hiện nhiều nhất trong mảng.

javascript
Sao chép
Chỉnh sửa
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
Kết quả:
A: 3
B: undefined
C: null
D: Error
<details><summary><b>Answer</b></summary> <p>
Đáp án đúng: D

Giải thích:

freqMap.num sai, phải là freqMap[num].
Dẫn đến lỗi undefined khi truy cập.
</p> </details>
6. Tìm số Fibonacci thứ N
javascript
Sao chép
Chỉnh sửa
function fibonacci(n) {
    if (n <= 1) return n;
    return fibonacci(n - 1) + fibonacci(n - 2);
}

console.log(fibonacci(6));
Kết quả:
A: 8
B: 13
C: 6
D: NaN
<details><summary><b>Answer</b></summary> <p>
Đáp án đúng: A

Giải thích:

Hàm tính đúng số Fibonacci thứ N.
</p> </details>
7. Tính tổng các số lẻ trong mảng
javascript
Sao chép
Chỉnh sửa
function sumOdd(arr) {
    return arr.filter(x => x % 2 === 1).reduce((a, b) => a + b);
}

console.log(sumOdd([1, 2, 3, 4, 5]));
Kết quả:
A: 9
B: 8
C: NaN
D: 10
<details><summary><b>Answer</b></summary> <p>
Đáp án đúng: C

Giải thích:

.reduce((a, b) => a + b) lỗi nếu mảng rỗng (do filter có thể trả về []).
Phải dùng .reduce((a, b) => a + b, 0).
</p> </details>
8. Xóa phần tử trùng trong mảng
javascript
Sao chép
Chỉnh sửa
function removeDuplicates(arr) {
    return [...new Set(arr)];
}

console.log(removeDuplicates([1, 2, 2, 3, 4, 4, 5]));
Kết quả:
A: [1,2,3,4,5]
B: [1,2,2,3,4,4,5]
C: [5,4,3,2,1]
D: Error
<details><summary><b>Answer</b></summary> <p>
Đáp án đúng: A

Giải thích:

new Set(arr) loại bỏ trùng lặp.
</p> </details>
9. Tính trung bình cộng
javascript
Sao chép
Chỉnh sửa
function average(arr) {
    return arr.reduce((a, b) => a + b) / arr.length;
}

console.log(average([]));
Kết quả:
A: 0
B: NaN
C: undefined
D: Error
<details><summary><b>Answer</b></summary> <p>
Đáp án đúng: B

Giải thích:

.reduce() lỗi nếu mảng rỗng, gây NaN.
</p> </details>
10. Chuẩn hóa tên (viết hoa chữ cái đầu)
javascript
Sao chép
Chỉnh sửa
function capitalize(str) {
    return str.charAt(0).toUpperCase + str.slice(1);
}

console.log(capitalize("hello"));
Kết quả:
A: "Hello"
B: "hello"
C: Error
D: undefined
<details><summary><b>Answer</b></summary> <p>
Đáp án đúng: D

Giải thích:

.toUpperCase sai, phải là .toUpperCase().
</p> </details>





