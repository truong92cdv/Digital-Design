# CHAPTER 3 - GATE-LEVEL MINIMIZATION

# 3.1. Introduction

# 3.2. The Map Method
* Phương pháp bìa Karnaugh hay K-map giúp đơn giản hóa hàm Boolean 1 cách hệ thống, đảm bảo thu được hàm tối thiểu giúp tiết kiệm chi phí thiết kế.
* K-map là phương pháp trực quan, rất hữu ích với hàm <= 4 biến. Với hàm > 4 biến, phương pháp trở nên phức tạp và không trực quan.

## K-map 2 biến
![pic301.png](pic301.png)

## K-map 3 biến
![pic302.png](pic302.png)

## K-map 4 biến
![pic303.png](pic303.png)
* Các minterms được sắp xếp theo Gray code, nhằm đảm bảo 2 minterm liền kề chỉ khác nhau 1 bit.
* 2 minterm cùng hàng ở cạnh trái và cạnh phải được xem là liền kề. 2 minterm cùng cột ở cạnh trên và cạnh dưới được xem là liền kề. 4 minterm ở 4 góc cũng được xem là liền kề.
* Hàm phải được viết ở dạng **sum of products**.
* Các minterms liền kề (tạo thành hình chữ nhật) khi kết hợp sẽ giúp loại bỏ bớt biến trong biểu diễn cuối cùng:
  * 1 ô -> term có 4 biến.
  * 2 ô liền kề -> term có 3 biến.
  * 4 ô liền kề -> term có 2 biến.
  * 8 ô liền kề -> term có 1 biến.
  * 16 ô liền kề -> hàm có giá trị = 1.
* Ưu tiên gom thành các nhóm lớn trước, nhóm nhỏ sau. Các ô có thể được gom nhóm nhiều lần.
* Ex: Đơn giản hóa hàm $F(w, x, y, z) = \sum(0, 1, 2, 4, 5, 6, 8, 9, 12, 13, 14) = y' + w'z' + xz'$.
![pic304.png](pic304.png)
* Ex: Đơn giản hóa hàm $F = A'B'C' + B'CD' + A'BCD' + AB'C' = B'D' + B'C' + A'CD'$.
![pic305.png](pic305.png)

## Prime Implicants
* Mỗi product term là 1 implicant.
* 1 implicant là prime implicant nếu nó là implicant lớn nhất, không thể chứa trong các implicant lớn hơn. Ex: 4 ô liền kề hình thành 1 prime implicant nếu không có implicant 8 ô nào chứa nó.
* 1 prime implicant là essential nếu nó có chứa ít nhất 1 ô mà ô này chỉ có thể bao phủ bởi prime implicant đó. Essential prime implicant bắt buộc xuất hiện trong biểu thức cuối cùng.
* Ex: Đơn giản hóa hàm $F(A, B, C, D) = \sum(0, 2, 3, 5, 7, 8, 9, 10, 11, 13, 15)$.
![pic306.png](pic306.png)
* Hình (a) vẽ 2 essential prime implicants BD và B'D'.
  * BD là essential vì nó là prime implicant 4 ô duy nhất chứa ô $m_5$.
  * B'D' là essential vì nó là prime implicant 4 ô duy nhất chứa ô $m_0$.
* Hình (b) vẽ 4 prime implicants CD, B'C, AD, AB'. Chúng không phải là essential vì:
  * $m_3$ có thể được phủ trong prime implicant CD hoặc B'C.
  * $m_9$ có thể được phủ trong prime implicant AD hoặc AB'.
  * $m_{11}$ có thể được phủ trong cả 4 prime implicant này.
* Buổi thức cuối cùng sẽ là sự kết hợp của 2 essential implicant và các tổ hợp prime implicant bao phủ 3 ô $m_3, m_9, m_{11}$:
  * $F = BD + B'D' + CD  + AD$.
  * $F = BD + B'D' + CD  + AB'$.
  * $F = BD + B'D' + B'C + AD$.
  * $F = BD + B'D' + B'C + AB'$.

# 3.4. Đơn giản hóa hàm dạng Product of Sums
* Ta cũng có thể đơn giản hàm thành dạng **product of sums**.
* Ex: Đơn giản hóa hàm $F(A, B, C, D) = \sum(0, 1, 2, 5, 8, 9, 10)$ theo 2 dạng **sum of products** và **product of sums**.
![pic307.png](pic307.png)
* Áp dụng phương pháp K-map với các ô giá trị "1", ta có được: $F  = B'D' + B'C' + A'C'D$.
* Áp dụng phương pháp K-map với các ô giá trị "0", ta có được: $F' = AB + CD + BD'$.
* Áp dụng định lý DeMorgan ta được: $F = (F')' = (A' + B')(C' + D')(B' + D)$.
* 2 dạng biểu diễn trên khi thực thi mạch số sẽ được dạng thực thi cổng logic 2 mức:
![pic308.png](pic308.png)

# 3.5. Don't care condition
* Trong các ví dụ trên, mỗi ô trong bảng chân trị có giá trị xác định "1" hoặc "0".
* Tuy nhiên trong ứng dụng thực tế, một số hàm sẽ có kết quả không xác định (hoặc không quan trọng - don't care) đối với 1 số tổ hợp inputs.
* Minterm nào là don't care sẽ được ký hiệu là "X". Khi áp dụng K-map để đơn giản hóa hàm, ta có thể tùy ý chọn giá trị "1" hoặc "0" cho "X" sao cho đạt được biểu thức cuối cùng tối giản nhất.
* Ex: Đơn giản hóa hàm $F(w, x, y, z) = \sum(1, 3, 7, 11, 15)$ có các minterms don't care sau: $d(w, x, y, z) = \sum(0, 2, 5)$.
![pic309.png](pic309.png)
* Trên hình ta thấy có 2 cách tối giản: $F = yz + w'x'$ hoặc $F = yz + w'z$.
* Ngoài ra để tối giản hàm theo dạng *product of sums*, ta xét các ô "0" và được $F' = z' + wy'$ và $F = z(w' + y)$ (định lý deMorgan).

# 3.6. Cổng NAND và NOR
