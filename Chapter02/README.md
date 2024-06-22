# 2. BOOLEAN ALGEBRA AND LOGIC GATES

# 2.1. Giới thiệu
* Chi phí để thực thi mạch số là yếu tố quan trọng.
* Ta sẽ học các phương pháp toán học gọi là Đại số Boolean để đơn giản hóa cũng như tối ưu hóa các mạch số.

# 2.2. Định nghĩa
* Cho 1 tập S gồm 1 số phần tử xác định. Xét 1 phép toán nhị phân "*".
* *Cấu trúc đại số* được xây dựng dựa trên 6 tiên đề cơ sở:
  * **Tính bao đóng**:  Tập S là *bao đóng* đối với phép toán "*", nếu với mỗi cặp phần tử thuộc S, phép toán sẽ cho kết quả là 1 phần tử xác định thuộc S. Ví dụ, với tập số tự nhiên N = {1, 2, 3, ...} là *bao đóng* với phép toán "+", vì với mọi a, b thuộc N, luôn tìm được số c = a + b cũng thuộc N. Tuy nhiên tập N là không bao đóng với phép toán "-".
  * **Luật kết hợp**: *(x * y) * z = x * (y * z)* với mọi x, y, z thuộc S.
  * **Luật giao hoán**: *x * y = y * x* với mọi x, y, z thuộc S.
  * **Luật phần tử đơn vị**: Tồn tại phần tử đơn vị *e* sao cho: *e * x = x * e* với mọi x thuộc S.
  * **Phép đảo**: Nếu e là phần tử đơn vị của S với phép toán "*". Với mọi x thuộc S, tồn tại phần tử y thuộc S sao cho: *x * y = e*.
  * **Luật phân phối**: Nếu "*" và "+" là 2 phép toán nhị phân trong S, "*" được gọi là có tính phân phối đối với "+" nếu: *x * (y + z) = x * y + x * z*.

# 2.3. Đại số Boolean
* **Đại số Boolean** là 1 cấu trúc đại số, gồm 1 tập B cùng 2 phép toán "+" và "*" thỏa mãn các tiên đề Huntington:
  * **Tính bao đóng**: với cả phép "+" và phép "*".
  * **Luật phần tử đơn vị**:
    (a) 0 là phần tử đơn vị của phép "+": *x + 0 = 0 + x = x*.
    (b) 1 là phần tử đơn vị của phép "*": *x * 1 = 1 * x = x*.
  * **Luật giao hoán**:
    (a) *x + y = y + x*.
    (b) *x * y = y * x*.
  * **Luật phân phối**:
    (a) của phép "*" đối với phép "+": *x * (y + z) = x * y + x * z*.
    (b) của phép "+" đối với phép "*": *x + y * z = (x + y) * (x + z)*.
  * **Phép đảo**: Với mọi x thuộc B, luôn tồn tại phần bù x' thuộc B thỏa mãn:
    (a) *x + x' = 1*
    (b) *x * x' = 0*
  * Có ít nhất 2 phần tử riêng biệt x, y thuộc B.
* Ở đây, ta chỉ quan tâm đến đại số Boolean 2 giá trị (tập B chỉ gồm 2 phần tử).

## Đại số Boolean 2 giá trị.
* Tập B = {0, 1} với 2 phép toán "*" (tương đương phép toán AND) và "+" (tương đương phép toán OR) và phép đảo (tương đương phép toán NOT) thỏa mãn 6 tiên đề Huntington.

# 2.4. Các định lý cơ bản và đặc điểm của Đại số Boolean
## Tính nhị nguyên
* Với 1 định lý cho trước, ta chỉ cần thay đổi OR - AND, đổi 0 - 1 sẽ được 1 định lý đúng khác.

## Các định lý cơ bản
* Có 6 định lý cơ bản, các định lý có thể chứng minh từ các tiên đề.
[pic201](pic201.png)
