# C
## C String
### String trong C là một chuỗi ký tự kết thúc bằng '\0'. Khác với một mảng ký tự là một mảng lưu từng phần tử riêng biệt là mỗi ký tự độc lập.
![image](https://github.com/user-attachments/assets/af4f146d-fc3a-42a1-8a0b-fb316e16cd7f)
### Có nhiều cách khởi tạo chuỗi:
```cpp
char str[] = "Hello";
```
Chuỗi ký tự thì không cần gán kích thước trước cho nó.

Nhưng ta cũng có thể gán kích thước trước cũng không sao.
```cpp
char str[15]={'a','b','c','e'};
```
Before diving in string. We must differate between single quoted '' and double quoted " "

Single quoted is used to declare or display single character. Example:
```cpp
char str[]={'a','b','c'};
for(int i=0;i<3;i++)
{
 printf("%c\n",str);
}
```
In contra, Double quoted is used to delcare or display full string. We don't need the loop when using double quoted. Example:
```cpp
char str[]="Lucifer";
printf("%s",str);
```


### Đọc chuỗi từ bàn phím
```cpp
char str[50];
scanf("%s",str);
printf("This is string %s",str);
```
Có thể thấy ta chỉ dùng hàm scanf và str không cần dấu "&" là vì tên của mảng cũng chính là địa chỉ cơ sở(địa chỉ của phần tử đầu tiên). Và nó cứ như vậy ghi vào 
tiếp theo từ phần tử này đến phần tử tiếp theo do mảng là một tập hợp các biến có cùng kiểu dữ liệu được sắp xếp liên tiếp nhau.

### Một hạn chế cực lớn của scanf đó là nó chỉ có thể đọc được tới dấu khoảng trắng??? Vì mảng chuỗi kết thúc bằng '\0' mà scanf chỉ đọc được tới đó thì nó ngưng.
### Câu hỏi đặt ra làm cách nào để đọc một chuỗi được phân tách bằng dấu khoảng trắng???
Có nhiều phương pháp để làm điều này những phổ biến nhất:
- Sử dụng hàm **fgets()** để đọc một dòng chuỗi và dùng **gets()** để đọc từng ký tự cho đến khi gặp ký tự xuống dòng hoặc kết thúc tệp **EOF** là một hàm thuộc stdio.
- Có thể quét các ký tự bên trong hàm scanf().
```cpp
char str[50];
fgets(str,sizeof(str),stdin);
printf("String %s",str);
```
This is example code for using **fgets** function:
```cpp
#include <stdio.h>
int main() {
    char str[50];
    printf("Please enter your string: ");
    fgets(str,sizeof(str),stdin);
    printf("This is your string %s",str);
    puts(str);//Displaying string using puts
    return 0;
}
```
This is example code for using **scanset**:
```cpp
#include<stdio.h>
int main()
{
  char str[50];
  printf("Please type your string!!: ");
  scanf("%[^\n]s",str);//read until endline
  printf("This is your string: %s",str);
  return 0;
}
```
### C String length
The length of string is the number of characters present in the string except for the NULL character. We can easily find the length of the string using the loop to count the character from the start till the NULL character is found.
- Passing String in the Function: As string are  character arrrays, we can pass strings to functions in the same way we pass an array to a function. Below is a sample code:
```cpp
#include<stdio.h>
void passString(char str[])
{
    printf("This is your string: %s\n",str);
    str = "World Hello";
    printf("Strings Are Modified by Function: %s\n",str);
}
int main()
{
  char str[]="Hello World";
  passString(str);
  printf("This string in the Main: %s",str);
  return 0;
}
```
![image](https://github.com/user-attachments/assets/75a2c50e-8b97-489b-89cd-f5928c0941dc)
### String actually like an Array so Have Any relatve with Pointer???
- In Arrays, the variable name point to the address of the first element.
- Below is the memory representation of the string str = "Greek".
![image](https://github.com/user-attachments/assets/fd353f31-fe3d-416d-8ed3-09d6ba7ecf87)
Similar to arrays, In C, We can create a character pointer to string that point to the string address of the string which is the first character of the string. The string can be accessed with the help of pointers.
Below is example code:
```cpp
#include<stdio.h>
int main()
{
    char str[] = "Lucifer Ryan";
    char *ptr=str;
    while(*ptr!='\0')
    {
        printf("%c",*ptr);
        ptr++;
    }

  return 0;
}
```
Some Stadard function in string.h useful.

|Funcion name| Description|
|------------|------------|
|strlen()|return the length of string|
|strcpy(s1,s2)|copy the content of s2 to s1|
|strcmp(s1,s2)|compare the s1 with s2. If strings are same it return 0.|
|strcat(s1,s2)|concat s1 with s2 and the result is stored in the s1|
|strlwr()|convert string to lowercase|
|strlupr()|conver string to uppercase|
|strstr(s1,s2)|find the first occurrence of s2 in s1|









