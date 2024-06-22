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
* Ex: Chuyển số 41<sub>10</sub> sang hệ nhị phân: **(41)<sub>10</sub> = (101001)<sub>2</sub>**
  ![pic01](pic01.png)
* Ex: Chuyển số 153<sub>10</sub> sang hệ octal: **(153)<sub>10</sub> = (231)<sub>8</sub>**
  ![pic02](pic02.png)
### Phần thập phân
* Lấy phần thập phân nhân với cơ số r, được phần nguyên và phần thập phân mới. Tiếp tục lấy phần thập phân mới nhân với r đến khi phần nguyên = 0. Viết các phần nguyên theo thứ tự sẽ được biểu diễn tương đương trong hệ cơ số r.
* Ex: Chuyển số 0.6875<sub>10</sub> sang hệ nhị phân: **(0.6875)<sub>10</sub> = (0.a<sub>-1</sub>a<sub>-2</sub>a<sub>-3</sub>a<sub>4</sub>)<sub>2</sub> = (0.1011)<sub>2</sub>**
  ![pic03](pic03.png)
