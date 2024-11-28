##### Quiz-code
- In JS we trust - The best way to learn is by building/coding and teaching. I create the challenges to help my friends learn JavaScript and in return it helps me embrace the language in much deeper level. Feel free to clone, fork and pull.

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
