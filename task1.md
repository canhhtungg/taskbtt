# Kiểu dữ liệu
Kiểu dữ liệu là khái niệm biểu thị loại giấ trị mà một biến có thể lưu trữ và thao tác. Các kiểu dữ liệu cung cấp cách để máy tính hiểu cách lưu trữ, quản lý và xử lý thông tin.

# Các kiểu dữ liệu nguyên thủy
- **số nguyên(int)**: lưu trữ cá gtri nguyên, không có phần thập phân
-- độ lớn: 1byte(8bit)->8byte(64bit)
-- đặc tả: gồm kiểu có dấu(int) và kiểu không có dấu(unsigned int) 
- **số thực(double)**: lưu trữ các giá trị số thập phân
-- độ lớn: float(32bit) lưu trữ ~6 chữ số thập phân, double(64bit) lưu trữ ~15 chữ số thập phân
- **kí tự(char)**: lưu trữ kí tự đơn
-- đặc tả: dùng mã ASCII hoặc Unicode
-- độ lớn: 1->2byte
- **logic(bool)**: lưu trữ giá trị đúng sai
-- đặc tả: 0(false)/1(true)
-- độ lớn: 1bit->1byte

# Biểu diễn kiểu dữ liệu có dấu và không có dấu
- Kiểu dữ liệu có dấu (signed) dùng bit đầu tiên để biểu thị dấu (0 cho dương, 1 cho âm)
- Kiểu không có dấu (unsigned) dùng toàn bộ các bit để biểu diễn giá trị.
- Ví dụ với 8-bit số nguyên biểu diễn được phạm vi:
-- Có dấu: -128 đến 127.
-- Không dấu: 0 đến 255.
![Screenshot 2025-03-09 153519](https://hackmd.io/_uploads/rJq1XAqsyl.png)

# Ép kiểu
**Ép kiểu là quá trình chuyển đổi gtri từ kiểu dữ liệu này sang kiểu dự liệu khác.**

**ví dụ:**
- cho 2 số a,b có kiểu dữ liệu số nguyên int nhưng khi thực hiện phép toán nhân thì có thể tràn dữ liệu gây ra kết quả không chính xác thì có thể ép kiểu trong khi thực hiện phép toán
`x=(longlong)a*(longlong)b;`
- tương tự với phép chia nếu kết quả là một số thực
`y=(double)a/b;`
- khi X là một biến kiểu dữ liệu char biểu diễn kí tự 'a' ta có thể ép kiểu để lấy mã ascil của 'a' 
```
char X='a';
z=(int)X;      
```
-> z=97

**Địa chỉ của biến là vị trí trong bộ nhớ nơi giá trị của biến được lưu trữ.
Giá trị của biến là dữ liệu được lưu trữ bên trong biến.**
![Screenshot 2025-03-09 154332](https://hackmd.io/_uploads/rkop409oke.png)

output:
![Screenshot 2025-03-09 162151](https://hackmd.io/_uploads/ry8p6RqjJx.png)

Trình biên dịch thường căn chỉnh (alignment) biến trên bộ nhớ để tối ưu hóa hiệu suất. Điều này dẫn đến sự chênh lệch địa chỉ giữa các biến (thường là bội số của kích thước biến).

# Biến toàn cục, biến cục bộ
Biến toàn cục(thường khai báo ở đầu chương trình) có thể gọi và dùng cho cả chương trình.

Biến cục bộ(thường khai báo trong hàm hoặc trong khối lệnh) chỉ có thể gọi và dùng trong một hàm hay chương trình con đã khai báo.
