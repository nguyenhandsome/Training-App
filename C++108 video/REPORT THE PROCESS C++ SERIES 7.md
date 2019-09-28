# REPORT THE PROCESS C++ SERIES 7

## VIDEO 1 BAI 77 CAC BAI TAP TU REN LUYEN

**NOI DUNG**

*Đề:*

1. Viết hàm tính giá trị đa thức

2. Dùng con trỏ để nhập 2 vector có N chiều

   - p(p1,p2,..,pn)
   - q(q1,q2,..,qn)

   Tính khoảng cách 2 vector theo công thức euclid

3. Viết chương trình tính tích phân của f(x) trên đoạn (a,b) bằng công thức hình thang

   - Theo đó, tích phân của f(x) trên [a,b] bằng:h*s . Trong đó
     - h: là độ dài khoảng phân hoạch đoạn [a,b] thành n khoảng
     - s: là tổng tất cả các f(a+i*h) với i từ 1 đến n.
   - Sử dụng hàm trên để tính tích phân trong đoạn [-1;4] của: f(x)=(e^x-2sin(x^2))/(1+x^4). Ngiên cứu cách đưa con trỏ vào giải quyết bài toán

4. Dùng con trỏ cấp 2 để xử lý mãng 2 chiều

- Khai báo, cấp phát con trỏ cấp 2
- Nhập dữ liệu cho mãng 2 chiều
- xuất dữ liệu mãng 2 chiều
- Xuất đường chéo chính
- Xuất đường chéo phụ
- Tính tổng giá trị mạng 2 chiều

1. 

```
#include<iostream>
#include<time.h>
#include<stdlib.h>
#include<math.h>
using namespace std;
//de cau 1
void inputA(double *&a,int n);
void outputA(double *&a,int n);
double dt(double x,int n,double *a,int m);
int main(int argv, char** argc)
{
    int n;
    double *a;
    double x;
    do
    {
        cout<<"nhap n"<<endl;
        cin>>n;
        if(n<=0)
            cout<<"nhap lai"<<endl;
    }while(n<=0);
    int m=n;
    inputA(a,n);
    cout<<"mang sau khi nhap"<<endl;
    outputA(a,n);
    cout<<"nhap gia tri x bat ki"<<endl;
    cin>>x;
    double kq=dt(x,n,a,m);
    cout<<"gia tri da thuc la:"<<endl;
    cout<<kq<<endl;
    return 0;
}

//ham tinh da thuc
double dt(double x,int n,double *a,int m)
{
    double p;
    for(int i=0;i<=n;i++)
    {
        p+=a[i]*pow(x,m);
        m--;
    }
    return p;
}

//nhap mang
void inputA(double *&a,int n)
{
    srand(time_t(NULL));
    a=new double[n];
    for(int i=0;i<=n;i++)
    {
        cout<<"a["<<i<<"]= ";
        cin>>*(a+i);
    }
    
}

//xuat mang
void outputA(double *&a,int n)
{
    for(int i=0;i<=n;i++)
    {
        cout<<*(a+i)<<"\t";
    }
    cout<<endl;
}

```

2. 

```
#include<iostream>
#include<math.h>
#include<time.h>
#include<stdlib.h>
using namespace std;
//de 2
int *cbn(int n);
void random(int *a,int *b,int n);
void inputA(int *&a,int n);
void outputA(int *a,int n);
double sum(int *&a,int *&b,int n);
int main(int argv, char** argc)
{
    srand((int)time(0));
    int n;
    do
    {
        cout<<"nhap so chieu cua 2 vector"<<endl;
        cin>>n;
        if(n<=0)
            cout<<"nhap lai"<<endl;
    }while(n<=0);
    int *a=cbn(n);
    int *b=cbn(n);
    inputA(a,n);
    inputA(b,n);
    cout<<"vector p";
    outputA(a,n);
    cout<<"vector q";
    outputA(b,n);
    double kq=sum(a,b,n);
    cout<<"Khoang cach 2 vector la"<<endl;
    cout<<kq<<endl;
    return 0;
}

//so chieu
int *cbn(int n)
{
    int *p=new int[n];
    return p;
}


//toa do vector
void inputA(int *&a,int n)
{
    for(int i=0;i<n;i++)
    {
        *(a+i)=rand()%11;
    }
}

//xuat cac toa do vector
void outputA(int *a,int n)
{
    cout<<"(";
    for(int i=0;i<n;i++)
    {
        cout<<a[i];
        if(i<n-1)
            cout<<",";
    }
    cout<<")"<<endl;
}

//Khoang cach 2 vector
double sum(int *&a,int *&b,int n)
{
    double p=0;
    for(int i=0;i<n;i++)
    {
        p+=pow((a[i]-b[i]),2);
    }
    p=sqrt(p);
    return p;
}

```

3. 

```
#include<iostream>
#include<time.h>
#include<stdlib.h>
using namespace std;
//de con tro 4
void inputM(int **&a,int n);
void outputM(int **a,int n);
int **sum(int **&a,int **&b,int n);
int main(int argv, char** argc)
{
    srand(time_t(NULL));
    int **a;
    int **b;
    int n;
    do
    {
        cout<<"nhap so luong phan tu"<<endl;
        cin>>n;
        if(n<=0)
            cout<<"nhap lai"<<endl;
    }while(n<=0);
    inputM(a,n);
    inputM(b,n);
    cout<<"mang a:"<<endl;
    outputM(a,n);
    cout<<"mang b:"<<endl;
    outputM(b,n);
    int **kq=sum(a,b,n);
    cout<<"tong 2 ma tran la"<<endl;
    outputM(kq,n);
    
    
    return 0;
}

//nhap mang
void inputM(int **&a,int n)
{
    srand(time_t(NULL));
    a=new int*[n];
    for(int i=0;i<n;i++)
        *(a+i)=new int[n];
    for(int i=0;i<n;i++)
    {
        for(int j=0;j<n;j++)
        {
            *(*(a+i)+j)=rand()%11;
        }
    }
}


//xuat mang
void outputM(int **a,int n)
{
    for(int i=0;i<n;i++)
    {
        for(int j=0;j<n;j++)
        {
            cout<<*(*(a+i)+j)<<"\t";
        }
        cout<<endl;
    }
}

//tong 2 mang
int **sum(int **&a,int **&b,int n)
{
    int **c;
    c=new int*[n];
    for(int i=0;i<n;i++)
    {
        *(c+i)=new int [n];
    }
    for(int i=0;i<n;i++)
    {
        for(int j=0;j<n;j++)
        {
            *(*(c+i)+j)=a[i][j]+b[i][j];
        }
    }
    return c;
}
```



4. 

```
#include<iostream>
using namespace std;
//de so 4
int **cbn(int n);
void inputM(int **&a,int n);
void outputM(int **a,int n);
void md (int **&a,int n);
void ad (int **&a,int n);
int sum (int **&a,int n);
int main(int argv, char** argc)
{
    int n;
    do
       {
           cout<<"nhap n phan tu cho ma tran cap nxn"<<endl;
           cin>>n;
           if(n<=0)
               cout<<"nhap lai"<<endl;
       }while(n<=0);
    int **a;
    a=cbn(n);
    inputM(a,n);
    cout<<"mang sau khi nhap la:"<<endl;
    outputM(a,n);
    cout<<"duong cheo chinh:"<<endl;
    md(a,n);
    cout<<"duong cheo phu"<<endl;
    ad(a,n);
    cout<<"tong gia tri ma tran la:"<<endl;
    int kq=sum(a,n);
    cout<<kq<<endl;
    return 0;
}

//cap phat bo nho
int **cbn(int n)
{
    int **p;
    p = new int*[n];
    for (int i=0;i<n;i++)
        *(p+i)=new int [n];
    return p;
}

//nhap mang
void inputM(int**&a,int n)
{
    for(int i=0;i<n;i++)
    {
        for(int j=0;j<n;j++)
        {
            cout<<"a["<<i<<"]["<<j<<"]=";
            cin>>*(*(a+i)+j);
        }
    }
}

//xuat mang
void outputM(int **a,int n)
{
    for(int i=0;i<n;i++)
    {
        for(int j=0;j<n;j++)
        {
            cout<<*(*(a+i)+j)<<"\t";
        }
        cout<<endl;
    }
}

//xuat duong cheo chinh
void md (int **&a,int n)
{
    for(int i=0;i<n;i++)
    {
        for (int j=0;j<n;j++)
        {
            if(i==j)
                cout<<a[i][j]<<"\t";
        }
    }
}

//xuat duong cheo phu
void ad (int **&a,int n)
{
    for(int i=0;i<n;i++)
    {
        for (int j=0;j<n;j++)
        {
            if(i+j==n-1)
                cout<<a[i][j]<<"\t";
        }
    }
}

//sum 2 ma tran
int sum (int **&a,int n)
{
    int s=0;
    for(int i=0;i<n;i++)
    {
        for(int j=0;j<n;j++)
        {
            s+=a[i][i];
        }
    }
    return s;
}

```

**End**

## VIDEO 2 BAI 78 KHAI NIEM VA CAU TRUC CHUOI

**NOI DUNG**

- Chuỗi là một mảng ký tự được kết thúc bằng ký tự `null('\0'`);

- Ký tự `null('\0');` là chuỗi được bao quanh bởi cặp dấu nháy đôi. VD:"Hello"

- Vd: để khai báo một mảng str chứa chuỗi có độ dài 20 ký tự, ta khai báo:

  ` char str[21];`

- Có thể dùng con trỏ để khai báo :

`char*str;`

- Có 2 cách khai báo và khởi tạo chuỗi

**C1: Dùng mảng một chiều**

`Char <Tên biến> [Chiều dài tối đa];`

- VD: `char str[12];`

**VD: `char str[25];`

- Ý nghĩa: khai báo một mảng kiểu ký tự tên là str có 25 phần tử (như vậy tối đa ta có thể nhập 24 ký tự vì phần tử thứ 25 đã chứa kí tự kết thúc chuỗi `'\0`')

  ***Lưu ý: Chuỗi ký tự được kết thúc bằng ký tự '\0'. Do đó khi khai báo độ dài của chuỗi luôn luôn khai báo dư 1 phần tử để chứa ký tự '\0'***

  **C2: Dùng con trỏ**

  `char *<Tên biến>`

  - VD: char *str;

    *Trong khai báo này, bộ nhớ sẽ dành 2 byte để lưu trữ địa chỉ của biến con trỏ str đang chỉ đến, chưa cung cấp nơi lưu trữ dữ liệu.*

    *Lưu ý: Trước khi sử dụng phải dùng từ khoá new để cấp phát vùng nhớ.*

  - VD: 

  ```
  char *str;
  str=new char[51];//cap phat 51 ki tu
  ```

- Chuỗi kí tự giống như mảng do đó để khởi tạo 1 chuỗi kí tự với những giá trị xác định ta có thể thực hiện tương tự như vậy với mảng.

`char <biến>[]=<"Hằng chuỗi">`

*VD:*

```
#include<iostream>
using namespace std;
//de
int main(int argv, char** argc)
{
    char *str="hello";
    cout<<str<<endl;
    char str1[]="obama";
    cout<<str1<<endl;
    char str2[]={'d','c','\0'};
    cout<<str2<<endl;
    char str4[10];
    str4[0]='P';
    str4[1]='b';
    str4[2]='\0';
    cout<<str4<<endl;
    
    return 0;
}

```

**End**

## VIDEO 3 BAI 79 CACH NHAP CHUOI-XUAT CHUOI

**NOI DUNG**

- Để nhập cho biến chuỗi, ta dùng hàm gets():

`char *gets(char*s);`

- Hàm gets() đọc các kí tự từ bàn phím vào trong mảng trỏ đến bởi s cho đến khi nhấn enter. Ký tự `NULL` sẽ được đặt sau ký tự cuối cùng cũa chuỗi nhập vào trong mảng

  *Lưu ý: khi dùng `cin>>` để nhập dữ liệu cho chuỗi, chương trình sẽ tự động ngắt khi gặp các ký tự khoảng trắng trong chuỗi. Do đó để chuỗi không bị ngắt khi gặp kí tự khoảng trắng,ta sẻ dùng hàm `gets()` hoặc cin.getline()

- *cin.getline(chuỗi, ký tự số tối đa)

**VD:**

- cher *str;
- str=new char [30];
- cin.getline(str,30);

```
#include<iostream>
#include<string.h>
using namespace std;
//de
int main(int argv, char** argc)
{
    char str[25];
    cout<<"moi ban nhao chuoi"<<endl;
    cin.getline(str,25);
    cout<<"chuoi sau khi ban nhap"<<endl;
    puts(str);
    
    char *str2=new char [25];
    cout<<"moi ban nhap chuoi"<<endl;
    cin.getline(str2,25);
    cout<<"chuoi sau khi ban nhao ka"<<endl;
    puts(str2);
    cout<<"kich thuoc that su ban nhap la "<<strlen(str2)<<endl;
    
    char str3[255];
    cout<<"moi ban nhap chuoi"<<endl;
    cin.getline(str3,255);
    cout<<"chuoi sau khi ban nhao la"<<endl;
    puts(str3);
    cout<<"kich thuoc that su ban nhap la "<<strlen(str3)<<endl;
    return 0;
}

```

**End**

## VIDEO 4 BAI 80 STRCPY,STRNCPY-SAO CHEP CHUOI

**NOI DUNG**

1. Hàm strcpy 

- Để sử dụng các hàm, ta phải khai báo dòng lệnh sau:

`#include<string.h>`

- Sao chép chuỗi nguồn vào chuỗi đích, nội dung của chuỗi đích sẽ bị xoá.

`strcpy(char*đích,char*nguồn);`

2. Hàm strncpy

- Chép n ký tự từ chuỗi nguồn sang chuỗi đích, nếu chiều dài nguồn <n thì hàm sẽ điền đủ khoảng trắng n vào đích 

`strncpy(char*dich,char*nguon,int n)`

**VD:**

```
#include<iostream>
#include<string.h>
using namespace std;
//de
int main(int argv, char** argc)
{
    char str1[25],str2[25];
    cout<<"nhap chuoi 1"<<endl;
    cin.getline(str1,25);
    strcpy(str2,str1);
    puts(str1);
    cout<<"chuoi 2"<<endl;
    puts(str2);
    
    char *str3=new char[25];
    strncpy(str3,str1,6);
    cout<<"chuoi 3 = "<<str3<<endl;
    return 0;
}

```

**End**

## VIDEO 5 BAI 81 STRCAT,STRNCAT-NOI CHUOI

**NOI DUNG**

1. Hàm strcat

- Nối chuỗi s2 vào chuỗi s1

`strcat(s1,s2)`

2. Hàm strncat

- Nối n ký tự đầu tiên cùa chuỗi s2 vào chuỗi s1

`strncat(chars1[],chars2[],int n)`

**VD:**

```
#include<iostream>
#include<string.h>
using namespace std;
//de
int main(int argv, char** argc)
{
    char str1[25],str2[25];
    strcpy(str1,"obama");
    strcpy(str2," an bun dau");
    strcat(str1,str2);
    puts(str1);
    
    char ho[25],ten[25],hovaten[50];
    cout<<"nhap ho"<<endl;
    cin.getline(ho,25);
    cout<<"nhap ten"<<endl;
    cin.getline(ten,25);
    strcat(hovaten,ho);
    strcat(hovaten," ");
    strcat(hovaten,ten);
    cout<<"ho va ten la"<<endl;
    puts(hovaten);
    
    //strncat
    char *str3=new char[25];
    char *str4=new char[25];
    strcpy(str3,"to be ");
    strcpy(str4, "or not to be");
    strncat(str3,str4,6);
    puts(str3);
    return 0;
    
}

```

**End**

## VIDEO 6 BAI 82 HAM STRCHR,STRSTR- TIM KY TU,CHUOI

**NOI DUNG**

1. Hàm strchr(s1,ch): Trả về con trỏ đến vị trí xuất hiện đầu tiên của ký tự ch trong chuỗi s1
2. Hàm strstr(s1,s2): Trả về con trỏ đến vị trí xuất hiện đầu tiên của chuỗi s2 trong s1

**VD:**

```\
#include<iostream>
#include<string.h>
using namespace std;
//de
int main(int argv, char** argc)
{
    char str1[25],str2[25];
    cout<<"nhap chuoi "<<endl;
    cin.getline(str1,25);
    strcpy(str2,str1);
    char *p=strchr(str2,'l');
    if (p!=NULL)
    {
        cout<<"vi tri cua 'l' trong mang la: "<<(p-str2)<<endl;
        
    }
    else
        cout<<"khong tim thay 'l' trong chuoi"<<endl;
    
    char str3[250];
    strcpy(str3,"quanh nam ban ca o mom song, ban ca o song");
    char *p2=strstr(str3,"song");
    if(p2!=NULL)
    {
        cout<<"tim thay 'song' o vi tri thu "<<(p2-str3)<<endl;
        
    }
    else
        cout<<"khong tim thay"<<endl;
    return 0;
}

```

**End**

## VIDEO 7 BAI 83 HAM STRCMP,STRNCMP-SO SANH CHUOI

**NOI DUNG**

1. Hàm strcmp

- So sánh 2 chuỗi s1 và s2 theo thứ tự từ điển. Phân biệt chữ hoa và chữ thường. Trả về:

  - 0: Nếu s1 bằng s2
  - `>` 0: Nếu s1 lớn hơn s2
  - `<` 0: Nếu s1 nhở hơn s2

  `strcmp(chars1[],chars2[]);`

2. Hàm strncmp 

`int strncmp(const char*str1,const char*str2,size_t n);`

- str1: chuỗi 1
- str2: chuỗi 2
- n ký tự đầu tiên

- 0: Nếu s1 bằng s2
- `>` 0: Nếu s1 lớn hơn s2 
- `<` 0: Nếu s1 nhở hơn s2

**VD:**

```
#include<iostream>
#include<string.h>
using namespace std;
//de
int main(int argv, char** argc)
{
    char str1[25],str2[25];
    cout<<"nhap 2 chuoi"<<endl;
    cin.getline(str1,25);
    cin.getline(str2,25);
    int kq=strcmp(str1,str2);
    cout<<"kq "<<kq<<endl;
    if(kq<0)
        cout<<"s1<s2"<<endl;
    else if(kq==0)
        cout<<"s1=s2"<<endl;
    else
        cout<<"s1>s2"<<endl;
    
    char str3[200];
    char str4[200];
    strcpy(str3,"cha me thoi doi an o bac");
    strcpy(str4,"co chong ho hung cung nhu khong");
    int kq2=strncmp(str3,str4,1);
    if(kq2<0)
           cout<<"s3<s4"<<endl;
       else if(kq2 ==0)
           cout<<"s3=s4"<<endl;
       else if(kq2>0)
           cout<<"s3>s4"<<endl;
    return 0;
}

```

**End**

## VIDEO 8 BAI 84 HAM toUPER,toLower-IN HOA,THUONG

**NOI DUNG**

1.Hàm toUper-toLower

- Chuyển ký tự thường sang ký tự hoa

`touper(int char);`

- Chuyển từ ký tự hoa sang ký tự thường

`tolower(int char);`

**VD:**

```
#include<iostream>
#include<string.h>
using namespace std;
//de
int main(int argv, char** argc)
{
    char str1[]="OBAMA hahaha alibaba";
    int n=strlen(str1);
    for(int i=0;i<n;i++)
    {
        char c=str1[i];
        putchar(toupper(c));
        
    }
    cout<<endl;
    char *str2=new char[200];
    strcpy(str2,str1);
    int n2=strlen(str2);
    for(int i=0;i<n;i++)
    {
        char c=str2[i];
        putchar(tolower(c));
    }
    cout<<endl;
    return 0;
}

```

**End**

## VIDEO 9 BTRL-CHUOI 1

*Đề: Viết chương trình nhập vào một chuỗi ký tự từ bàn phím, xuất ra màn hình mã ASCII của từng ký tự vừa nhập vào (gợi ý mỗi ký tự trên 1 dòng)*

```
#include<iostream>
#include<string.h>
using namespace std;
//de
void nc(char str[]);
void xc(char str[]);
void xASCII(char str[]);
int main(int argv, char** argc)
{
    char *str1=new char [25];
    cout<<"nhap chuoi"<<endl;
    nc(str1);
    cout<<"chuoi sau khi nhap la"<<endl;
    xc(str1);
    cout<<"ban ma ASCII cua chuoi la"<<endl;
    xASCII(str1);
    return 0;
}

//nhap chuoi
void nc(char str[])
{
    cin.getline(str,25);
}

//xuat chuoi
void xc(char str[])
{
    puts(str);
}

//xuat ma ASCII
void xASCII(char str[])
{
    int n=strlen(str);
    for (int i=0;i<n;i++)
    {
        char c=str[i];
        int ascii=(int)c;
        cout<<c<<"=>"<<ascii<<endl;
    }
}

```

**End**

## VIDEO 10 BTRL-CHUOI 2

*Đề:Viết chương trình nhập vào một chuỗi ký tự từ bàn phím, xuất ra màn hình đảo ngược của chuỗi đó*

```
#include<iostream>
#include<string.h>
using namespace std;
//de
void dc(char str[]);
int main(int argv, char** argc)
{
    char *str=new char[200];
    cout<<"nhap chuoi"<<endl;
    cin.getline(str,200);
    cout<<"chuoi sau khi nhap"<<endl;
    puts(str);
    cout<<"dao ki tu chuoi"<<endl;
    dc(str);
    puts(str);
}

//dao chuoi
void dc(char str[])
{
    int n=strlen(str);
    /*for(int i=n-1;i>=0;i--)
    {
        cout<<str[i];
    }*/
    int j=n-1;
    for(int i=0;i<n/2;i++)
    {
        char temp=str[i];
        str[i]=str[j];
        str[j]=temp;
        j--;
       
    }
}

```

**End**

## VIDEO 11 BTRL-CHUOI 3

*Đề: Viết chương trình nhập vào một chuỗi ký tự*

- In ra màn hình từ bên trái nhất và phần còn lại của chuỗi
- In ra màn hình từ bên phải nhất và phần còn lại của chuỗi

```
#include<iostream>
#include<string.h>
using namespace std;
//de
void ftl(char *strgoc,char *&strdau, char*&strsau);
void ftr(char *strgoc,char *&strcuoi, char*&strtruoc);
int main(int argv, char** argc)
{
    char *strgoc=new char[200];
    cout<<"nhap ho va ten"<<endl;
    cin.getline(strgoc,200);
    char *strdau=new char[200];
    char *strsau=new char[200];
    ftl(strgoc,strdau,strsau);
    cout<<"Ho:";
    puts(strdau);
    cout<<"Ten:";
    puts(strsau);
    
    char *strcuoi=new char[255];
    char *strtruoc=new char [255];
    ftr(strgoc,strcuoi,strtruoc);
    cout<<"Ho:";
    puts(strtruoc);
    cout<<"Ten:";
    puts(strcuoi);
    return 0;
}

//lay tu ben trai
void ftl(char *strgoc,char *&strdau, char*&strsau)
{
    char *p=strchr(strgoc,' ');
    //dam chi nguyen
    int lspace=p-strgoc;
    strncpy(strdau,strgoc,lspace);
    p=p+1;
    strsau=p;
}

//lay tu ben phai
void ftr(char *strgoc,char *&strcuoi, char*&strtruoc)
{
    int j=0;
    //cout<<strlen(strgoc)-1<<endl;
    for(int i=strlen(strgoc)-1;i>=0;i--)
    {
        if(strgoc[i]==' ')
        {
            //j=i+1;//' 'nguyen
            cout<<i<<endl;
            break;
        }
    }
    int i2=0;
    for(int i=j;i<strlen(strgoc);i++)
    {
        strcuoi[i2]=strgoc[i];
        i2++;
    }
    strncpy(strtruoc,strgoc,j-1);
    //cout<<j-1<<endl;
}

```

**End**

## VIDEO 12 BAI 88 BTRL-CHUOI 4

*Đề: Khai báo con trỏ cấp 2 để lưu danh sách 5 sinh viên minh hoạ trên, xuất danh sách 5 sinh viên theo 3 cột: mã tên giới tính, Đếm bao nhiêu nữ bao nhiêu nam*

```
#include<iostream>
#include<string.h>
using namespace std;
//de
bool hoinamhaynu(char *str)
{
    int j=0;
    for(int i=strlen(str);i>=0;i--)
    {
        if(str[i]==';')
        {
            j=i;
            break;
        }
    }
    int i2=0;
    char strgioitinh[5];
    for(int i=j+1;i<strlen(str);i++)
    {
        strgioitinh[i2]=str[i];
        i2++;
    }
    strgioitinh[i2]='\0';
    if(strcmp(strgioitinh,"MALE")==0)
        return false;
    return true;
}
int main(int argv, char** argc)
{
    char **dsSV=new char*[5];
    int sonam=0,sonu=0;
    for(int i=0;i<5;i++)
        *(dsSV+i)=new char [255];
    strcpy(*(dsSV+0),"SV1;OBAMA;MALE");
    strcpy(*(dsSV+1),"SV2;YANJIMA;FEMALE");
    strcpy(*(dsSV+2),"SV3;TRUMP;MALE");
    strcpy(*(dsSV+3),"SV4;PUTIN;MALE");
    strcpy(*(dsSV+4),"SV5;PEREIRA;FEMALE");
    for(int i=0;i<5;i++)
    {
        cout<<*(dsSV+i)<<endl;
        bool kq=hoinamhaynu(*(dsSV+i));
        if(kq==false)
            sonam++;
        else
            sonu++;
            
    }
    cout<<"co "<<sonam <<" sinh vien nam trong danh sach "<<endl;
    cout<<"co "<<sonu <<" sinh vien nu trong danh sach "<<endl;
}

```

