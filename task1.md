# Kiểu dữ liệu
Kiểu dữ liệu là khái niệm biểu thị loại giá trị mà một biến có thể lưu trữ và thao tác. Các kiểu dữ liệu cung cấp cách để máy tính hiểu cách lưu trữ, quản lý và xử lý thông tin.

# Các kiểu dữ liệu nguyên thủy
| Kiểu dữ liệu | Đặc tính biểu diễn | Độ lớn | Đặc tả | 
| ------------ | ------------------ | ------ | ------ |
| int | Số nguyên | 4 byte | %d |
| float | Số thực | 4 byte | %f |
| char | Ký tự | 1 byte | %c | 
| bool | Giá trị logic | 1 byte | true/false |

  - fload biểu diễn chính xác 6-7 chữ số tp có nghĩa

  - double biểu diễn chính xác 14-15 chữ số tp có nghĩa
```
#include <stdio.h>
#include <stdlib.h>
int main()
{
    float b=12.4567890123456789;
    double c=12.4567890123456789123456;
    printf("%.20f\n",b);
    printf("%.20lf\n",c);
    return 0;
}
```
output: ![Screenshot 2025-03-12 210301](https://hackmd.io/_uploads/HkK74MJnyx.png)


# Biểu diễn kiểu dữ liệu có dấu và không có dấu
- Kiểu dữ liệu có dấu (signed) dùng bit đầu tiên để biểu thị dấu (0 cho dương, 1 cho âm)
- Kiểu không có dấu (unsigned) dùng toàn bộ các bit để biểu diễn giá trị.
- Ví dụ với 8-bit số nguyên biểu diễn được phạm vi:
-- Có dấu: -128 đến 127.
-- Không dấu: 0 đến 255.
```
#include <stdio.h>
#include <stdlib.h>

int main()
{
    int a=-12;
    float b=12.4;
    char c='T';
    printf("so nguyen: %d\n",a);
    printf("so thuc: %f\n",b);
    printf("ki tu: %c\n",c);
    return 0;
}
```
output:
![Screenshot 2025-03-12 200839](https://hackmd.io/_uploads/H18ODbk21l.png)

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
-> z=96

  - **Địa chỉ của biến là vị trí trong bộ nhớ nơi giá trị của biến được lưu trữ.**
  - **Giá trị của biến là dữ liệu được lưu trữ bên trong biến.**
```
#include <stdio.h>
#include <stdlib.h>

int main()
{
    char a='T';
    float b=12.4;
    double c=12.45678;
    short d=124;
    unsigned int e=12;
    int f=-12;
    long g=12345;
    long long h=12345678901234;
    printf("% *c %p\n",15,a,&a);
    printf("% *f %p\n",15,b,&b);
    printf("% *lf %p\n",15,c,&c);
    printf("% *d %p\n",15,d,&d);
    printf("% *u %p\n",15,e,&e);
    printf("% *d %p\n",15,f,&f);
    printf("% *ld %p\n",15,g,&g);
    printf("% *lld %p\n",15,h,&h);

    printf("a->b: %d\n", (int)&a - (int)&b);
    printf("b->c: %d\n", (int)&b - (int)&c);
    printf("c->d: %d\n", (int)&c - (int)&d);
    printf("d->e: %d\n", (int)&d - (int)&e);
    printf("e->f: %d\n", (int)&e - (int)&f);
    printf("f->g: %d\n", (int)&f - (int)&g);
    printf("g->h: %d\n", (int)&g - (int)&h);
    return 0;
}
```
output:
![Screenshot 2025-03-12 203320](https://hackmd.io/_uploads/rkgL6bJhyx.png)

Các biến khi được khai báo đều được cấp phát địa chỉ vùng bộ nhớ và vì các biến là các kiểu dữ liệu khác nhau nên chúng chiếm các vùng bộ nhớ khác nhau nên chênh lệch địa chỉ không đồng đều.  

# Biến toàn cục, biến cục bộ
  - Biến toàn cục(thường khai báo ở đầu chương trình) có thể gọi và dùng cho cả chương trình(sau vị trí khai báo).

  - Biến cục bộ(thường khai báo trong hàm hoặc trong khối lệnh) chỉ có thể gọi và dùng trong một hàm hay chương trình con đã khai báo.
