# 2. BOOLEAN ALGEBRA AND LOGIC GATES

# 2.1. Giới thiệu
* Chi phí để thực thi mạch số là yếu tố quan trọng.
* Ta sẽ học các phương pháp toán học gọi là Đại số Boolean để đơn giản hóa cũng như tối ưu hóa các mạch số.

# 2.1. Định nghĩa
* Cho 1 tập S gồm 1 số phần tử xác định. Xét 1 toán tử nhị phân "*".
* Đại số Boolean được xây dựng dựa trên 6 tiên đề cơ sở:
  1. **Tính bao đóng**:  Tập S là *bao đóng* đối với 1 toán tử nhị phân, nếu với mỗi cặp phần tử thuộc S, toán tử sẽ cho kết quả là 1 phần tử xác định thuộc S. Ví dụ, với tập số tự nhiên N = {1, 2, 3, ...} là *bao đóng* với toán tử "+", vì với mọi a, b thuộc N, luôn tìm được số c = a + b cũng thuộc N. Tuy nhiên tập N là không bao đóng với toán tử "-".
  2. **Luật kết hợp**: ***(x * y) * z = x * (y * z)*** với mọi x,y,z thuộc S.
  3. **Luật giao hoán**: ***x * y = y * x***
