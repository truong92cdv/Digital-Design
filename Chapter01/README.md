# Digital Systems and Binary Numbers

## 1.1. Digital Systems
* Hệ thống số làm việc với các đại lượng rời rạc.
* Các hệ thống số thường gặp: Hệ nhị phân (Binary - 2), hệ bát phân (Octal - 8), hệ thập lục phân (Hex - 16), hệ thập phân (Decimal - 10).

## 1.2. Binary Numbers
* Hệ thống số nhị phân được sử dụng trong máy tính và mạch số bởi sự thuận tiện của nó.
* Hệ nhị phân gồm 2 chữ số 0 (logic LOW) và 1 (logic HIGH).
* Một số được biểu diễn ở hệ cơ số (base - radix) r dưới dạng:
  * **(a<sub>n</sub>a<sub>n-1</sub>a<sub>n-2</sub>...a<sub>1</sub>a<sub>0</sub>.a<sub>-1</sub>a<sub>-2</sub>...a<sub>-m</sub>)<sub>r</sub>**
* Biểu diễn trên có giá trị tương đương trong hệ thập phân là:
  * **a<sub>n</sub>.r<sup>n</sup> + a<sub>n-1</sub>.r<sup>n-1</sup> + ... + a<sub>1</sub>.r + a<sub>0</sub> + a<sub>-1</sub>.r<sup>-1</sup> + a<sub>-2</sub>.r<sup>-2</sup> + a<sub>-m</sub>.r<sup>-m</sup>**
* Hệ cơ số 8 sử dụng các chữ số từ 0 - 7 để biểu diễn số. Ex:
  * **(127.4)<sub>8</sub> = 1 x 8<sup>2</sup> + 2 x 8<sup>1</sup> + 7 x 8<sup>0</sup> + 4 x 8<sup>-1</sup> = (87.5)<sub>10</sbp>**
* Hệ cơ số 16 sử dụng các chữ số từ 0 - F (0123456789ABCDEF) để biểu diễn số. Ex:
  * **(B65F)<sub>16</sub> = 11 x 16<sup>3</sup> + 6 x 16<sup>2</sup> + 5 x 16<sup>1</sup> + 15 x 16<sup>0</sup> = (46,687)<sub>10</sub>**
  * Hệ Hex rất thuận tiện để lưu trữ chuỗi số nhị phân. 1 chữ số hệ hex tương đương 4 chữ số hệ binary, 2 chữ số hệ hex tương đương 8 chữ số hệ binary = 1 byte.
* 2<sup>10</sup> = 1K (kilo). 2<sup>20</sup> = 1M (mega). 2<sup>30</sup> = 1G (giga). 2<sup>40</sup> = 1T (tetra). 

## 1.3. Number-Base Conversions
* Chuyển đổi hệ cơ số khác sang hệ thập phân: Triển khai biểu diễn như phần 1.2 bên trên.
* Chuyển đổi hệ thập phân -> hệ cơ số r: Chia ra 2 phần (phần nguyên và phần sau dấu chấm).
### Phần nguyên
* Chia số đó cho cơ số r, được thương và phần dư. Tiếp tục lấy thương chia cho r đến khi thương = 0. Viết các số dư theo thứ tự ngược lại.
* Ex: Chuyển số (41)<sub>10</sub> sang hệ nhị phân: **(41)<sub>10</sub> = (101001)<sub>2</sub>**
  ![pic01](pic01.png)
* Ex: Chuyển số (153)<sub>10</sub> sang hệ octal: **(153)<sub>10</sub> = (231)<sub>8</sub>**
  ![pic02](pic02.png)
### Phần thập phân
* Lấy phần thập phân nhân với cơ số r, được phần nguyên và phần thập phân mới. Tiếp tục lấy phần thập phân mới nhân với r đến khi phần thập phân mới = 0. Viết các phần nguyên theo thứ tự sẽ được biểu diễn tương đương trong hệ cơ số r.
* Ex: Chuyển số (0.6875)<sub>10</sub> sang hệ nhị phân: **(0.6875)<sub>10</sub> = (0.a<sub>-1</sub>a<sub>-2</sub>a<sub>-3</sub>a<sub>4</sub>)<sub>2</sub> = (0.1011)<sub>2</sub>**
  ![pic03](pic03.png)
* Ex: Chuyển số (0.513)<sub>10</sub> sang hệ octal: **(0.513)<sub>10</sub> = (0.406517...)<sub>8</sub>**
  ![pic04](pic04.png)
* Lưu ý: Nếu phần thập phân mới không bao giờ = 0, ta sẽ thu được một biểu diễn tương tự số vô tỉ trong hệ decimal. Ngừng phép nhân khi đã đạt đủ độ chính xác cần thiết sau dấu chấm. 1 số hữu tỉ trong hệ decimal có thể là 1 số vô tỉ trong hệ cơ số khác và ngược lại.
### Biểu diễn đầy đủ
* Sau khi chuyển đổi phần nguyên và phần thập phân, ta kết hợp lại sẽ có biểu diễn đầy đủ:
  * **(41.6875)<sub>10</sub> = (101001.1011)<sub>2</sub>**
  * **(153.513)<sub>10</sub> = (231.406517...)<sub>8</sub>**

## 1.4. Octal and Hexadecimal Numbers
* Sự chuyển đổi giữa các hệ số binary, octal và hexa rất thường gặp.
* 1 chữ số hệ octal = 3 chữ số hệ binary. 1 chữ số hệ hexa = 4 chữ số hệ binary.
* Chuyển từ binary -> octal: nhóm từng bộ 3 chữ số binary lại, rồi chuyển từng bộ số.
  * Ex: **(10110001101011.111100000110)<sub>2</sub> = (10 110 001 101 011 . 111 100 000 110)<sub>2</sub> = (26153.7406)<sub>8</sub>**
* Chuyển từ binary -> hexa: nhóm từng bộ 4 chữ số binary lại, rồi chuyển từng bộ số.
  * Ex: **(10110001101011.111100000110)<sub>2</sub> = (10 1100 0110 1011 . 1111 0000 0110)<sub>2</sub> = (2C6B.F26)<sub>16</sub>**
* Chuyển từ octal hoặc hexa sang binary: làm ngược lại. Chuyển từng chữ số sang binary. Padding thêm 0 phía trước cho đủ bộ số.
  * Ex: **(306.D)<sub>16</sub> = (0011 0000 0110 . 1101)<sub>2</sub>**
* Hệ hexa rất hữu ích để lưu trữ, vì sự dễ dàng chuyển đổi sang binary và sự ngắn gọn trong biểu diễn số.

## 1.5. Complements of Numbers
* Biểu diễn số dạng phần bù: hữu ích khi cần thực hiện các phép toán với số âm, hoặc phép toán trừ, giúp đơn giản hóa thiết kế mạch số cũng như tiết kiệm chi phí khi thực thi mạch số.
* Có 2 loại phần bù: **Bù cơ số** - **Bù r** (radix complement) và **Bù cơ số giản lược** - **Bù (r-1)** (deminished radix complement).
* Ex: Với hệ binary: **Bù 2** và **Bù 1**. Với hệ decimal: **Bù 10** và **Bù 9**.
### Bù (r-1) (Deminished Radix Complement)
* Định nghĩa: Cho 1 số N có n chữ số trong hệ cơ số r. **Bù (r-1) của N = (r<sup>n</sup> - 1) - N**.
* Với hệ decimal:
  * N = 10 nên (10<sup>n</sup> - 1) sẽ là 1 số có n chữ số 9. Ex: n = 4 => 10<sup>4</sup> = 10,000 và (10<sup>4</sup> - 1 = 9,999).
  * Như vậy, **để tìm Bù 9 của 1 số decimal, chỉ cần trừ 9 cho mỗi chữ số của nó**.
  * Ex: Bù 9 của 546700 = 999999 - 546700 = 453299.
* Tương tự, với hệ binary:
  * N = 2 nên (2<sup>n</sup> - 1) sẽ là 1 số có n chữ số 1. Ex: n = 4 => 2<sup>4</sup> = 10000 và (2<sup>4</sup> - 1 = 1111).
  * Vì 1-0=1 và 1-1=0. **Để tìm Bù 1 của 1 số binary, chỉ cần thay đổi mỗi chữ số 0 thành 1, 1 thành 0**.
  * Ex: Bù 1 của 1011000 = 0100111.
### Bù r (Radix Complement)
* Định nghĩa: Cho 1 số N có n chữ số trong hệ cơ số r. **Bù r của N = r<sup>n</sup> - N nếu N # 0 và bằng 0 với N = 0**.
* So sánh với dạng **Bù (r-1)**, ta thấy rằng **Bù r = Bù (r-1) + 1** => Muốn tìm **Bù r**, ta tìm **Bù (r-1)** rồi + thêm 1 vào kết quả.
* Mẹo tính nhanh **Bù 10** trong hệ decimal: Tính từ phải qua, giữ nguyên các chữ số 0 liên tục. Với chữ số # 0 đầu tiên, lấy 10 trừ chữ số đó. Các chữ số còn lại bên trái, lấy 9 trừ đi chữ số đó.
  * Ex: Tìm **Bù 10** của 246700: giữ nguyên 2 chữ số 0 cuối cùng. Lấy 10 - 7 được 3. Lấy 999 - 246 được 753. Kết quả: **753300**.
 * Mẹo tính nhanh **Bù 2** trong hệ binary: Tính từ phải qua, giữ nguyên các chữ số 0 liên tục và chữ số 1 đầu tiên. Các chữ số còn lại bên trái, thay 1 thành 0, thay 0 thành 1.
   * Ex: Tìm **Bù 2** của 1101100: giữ nguyên ...100. Thay 1101... thành 0010... Kết quả: **0010100**.
 * Đối với số có dấu chấm thập phân, tạm thời loại bỏ dấu chấm, tìm phần bù tương ứng rồi thêm dấu chấm vào đúng vị trí cũ.
 * Phần bù của phần bù = số ban đầu.
