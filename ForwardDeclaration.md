```cpp
typedef struct Rect {
    int w, h;
    void (*set)(struct Rect*, int, int);  // <- Chú ý ở đây
    int (*area)(struct Rect*);
    void (*show)(struct Rect*);
} Rect;
```
- Việc gọi một Rect trong chính struct React được gọi là **Forward Declaration** là một tính năng vô cùng quan trọng trong C nó giúp có thể thực hiện những cấu trúc dữ liệu phức tạp như linked list hay tree.
- Pointer không cần quan tâm trong Rect của hàm set có gì nó chỉ cần biết là Rect này được khai báo hợp lệ và có địa chỉ của nó là OK.
- Rect trong set có thể truy cập mọi thứ trong struct Rect thông qua dấu **->** vì trong C không có khai niệm public hay private như C++ nên điều này khá thoải mái.

