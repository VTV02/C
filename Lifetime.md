1. Những cái bị mất khi kết thúc hàm
Các biến được khai báo cục bộ trong một hàm sẽ bị hủy khi hàm đó kết thúc. Những biến này bao gồm:

a. Biến cục bộ (Local Variables)
Định nghĩa: Biến được khai báo bên trong một hàm hoặc một khối lệnh {}.
Bộ nhớ: Các biến cục bộ được lưu trên stack (ngăn xếp).
Tồn tại: Biến cục bộ sẽ bị mất ngay khi thoát khỏi phạm vi của hàm hoặc khối lệnh nơi nó được khai báo.
Ví dụ:
```cpp
void myFunction() {
    int x = 10; // Biến cục bộ
    printf("%d\n", x);
} // Khi hàm myFunction kết thúc, biến x sẽ bị mất
```
b. Tham số hàm (Function Parameters)
Định nghĩa: Tham số của một hàm cũng được xem như biến cục bộ của hàm đó.
Bộ nhớ: Được lưu trên stack.
Tồn tại: Tham số chỉ tồn tại trong thời gian hàm đang chạy và sẽ bị mất khi hàm kết thúc.
Ví dụ:
```cpp
void myFunction(int y) { // Tham số y
    printf("%d\n", y);
} // y sẽ bị mất khi hàm myFunction kết thúc
```
2. Những cái tồn tại trong suốt chương trình
Dưới đây là các biến và dữ liệu tồn tại trong toàn bộ thời gian chương trình chạy:

a. Biến toàn cục (Global Variables)
Định nghĩa: Biến được khai báo bên ngoài mọi hàm.
Bộ nhớ: Lưu trữ trong bộ nhớ toàn cục (data segment).
Tồn tại: Biến toàn cục tồn tại từ khi chương trình bắt đầu cho đến khi chương trình kết thúc.
Ví dụ:
```cpp
int globalVar = 100; // Biến toàn cục
void myFunction() {
    printf("%d\n", globalVar);
}
```
b. Biến tĩnh (Static Variables)
Định nghĩa: Biến được khai báo với từ khóa static, có thể là:
Static cục bộ: Biến được khai báo bên trong một hàm nhưng sử dụng từ khóa static.
Static toàn cục: Biến toàn cục khai báo với từ khóa static để giới hạn phạm vi sử dụng trong file hiện tại.
Bộ nhớ: Lưu trong bộ nhớ toàn cục (data segment).
Tồn tại: Biến tĩnh được tạo ra khi chương trình bắt đầu và chỉ bị hủy khi chương trình kết thúc, dù nó chỉ có thể được truy cập trong phạm vi mà nó được khai báo.
ví dụ:
```cpp
void myFunction() {
    static int count = 0; // Biến tĩnh cục bộ
    count++;
    printf("%d\n", count);
}
// Biến count giữ giá trị giữa các lần gọi myFunction()
```
c. Bộ nhớ cấp phát động (Dynamic Memory Allocation)
Định nghĩa: Bộ nhớ được cấp phát động bằng cách sử dụng các hàm như malloc, calloc, hoặc realloc.
Bộ nhớ: Lưu trong heap (vùng nhớ tự do).
Tồn tại: Bộ nhớ này tồn tại cho đến khi:
Nó được giải phóng bằng free.
Chương trình kết thúc.
Lưu ý: Nếu không giải phóng bộ nhớ động, sẽ gây ra rò rỉ bộ nhớ (memory leak).
```cpp
int* ptr = (int*)malloc(sizeof(int)); // Cấp phát động
*ptr = 5;
printf("%d\n", *ptr);
free(ptr); // Giải phóng bộ nhớ
```
d. Hằng số (Constants)
Định nghĩa: Các giá trị hằng số (như số nguyên, ký tự, hoặc chuỗi) được lưu trữ trong vùng nhớ tĩnh.
Bộ nhớ: Lưu trong read-only memory (hoặc vùng code).
Tồn tại: Hằng số tồn tại trong suốt thời gian chạy chương trình.
Ví dụ:
```cpp
const int constantVar = 10; // Hằng số
printf("%d\n", constantVar);
```
```
Loại biến/dữ liệu	Bộ nhớ lưu trữ	Thời gian tồn tại
Biến cục bộ	Stack	Trong phạm vi hàm hoặc khối lệnh
Tham số hàm	Stack	Trong phạm vi hàm
Biến toàn cục	Data Segment	Suốt chương trình
Biến tĩnh (static)	Data Segment	Suốt chương trình
Bộ nhớ cấp phát động (heap)	Heap	Tồn tại đến khi được free
Hằng số (constants)	Read-only memory	Suốt chương trình
```



