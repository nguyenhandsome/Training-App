

# REPORT THE PROCESS C++ SERIES 6

## VIDEO 1 BAI 66 TOAN TU CON TRO

**NOI DUNG**

- Có 2 toán tử con trỏ là `*` và `&`
  1. Toán tử `&` là toán tử 1 ngôi mà trả về địa chỉ bộ nhớ của toán hạng của nó. (Toán tử 1 ngôi chỉ yêu cầu toán 1 hạng)

*VD:*

```
int count;
int *m;
m=&count;
```

- Lệnh `m=&count;` đặt địa chỉ bộ nhớ của biến count vào con trỏ m.
- Có thể phát biểu: "con trỏ m nhận địa chỉ của biến count"

2. Toán tử con trỏ là toán tử một ngôi trả về giá trị mà con trỏ trỏ đến

*VD:*

```
q=*m;
```

```
#include<iostream>
using namespace std;
//de
int main(int argv,char** argc)
{
    int count ;
    int *m;
    count=100;
    m=&count;
    int p=*m;
    cout<<m<<endl;
    cout<<p;
    return 0;
}

```

- Lấy giá trị tại địa chỉ mà con trỏ(m) trỏ đến và đặt vào biến q. Như vậy q sẽ có gía trị là 100

```
#include<iostream>
using namespace std;
//de
int main(int argv,char** argc)
{
    int count ;
    int *m;
    count=100;
    m=&count;
    cout<<"dia chi cua count la"<<&count<<endl;
    cout<<"gia tri cua count la"<<count<<endl;
    cout<<"dia chi bien m "<<m<<endl;
    cout<<"gia tri cua bien m"<<*m<<endl;
    
    int p=*m;
    cout<<"gia tri cua p la"<<p<<endl;
    int *x;
    x=m;
    cout<<"dia chi bien x la"<<x<<endl;
    cout<<"gia tri bien x la "<<*x<<endl;
    *x=9000;
     cout<<"gia tri cua bien m"<<*m<<endl;
     cout<<"gia tri cua count la"<<count<<endl;
    return 0;
}

```

**End**

## VIDEO 2 BAI 67 CAC THAO TAC TREN CON TRO

**NOI DUNG**

1. Lệnh gán con trỏ

- Ta có thể dùng một con trỏ ở bên phải của câu lệnh gán (=) để gán giá trị của 1 con trỏ cho một con trỏ khác

*VD:*

```
int x;
int *p1,*p2;
p1=&x;
p2=p1;

```

*sau khi đoạn lệnh được thực hiện , cả hai p1 và p2 cùng trỏ đến biến x*

2. Phép toán số học trên con trỏ

- Chỉ có 2 phép toán ta có thể dùng trong con trỏ đó là phép cộng và phép trừ. 
- Giả sử p1 là một con trỏ nguyên với giá trị hiện tại là 2000. Cũng gỉa sử rằng số nguyên chiếm 2 bytes bộ nhớ. Sau khi thực hiện lệnh `p1++;` thì p1 có giá trị là 2002 chứ không phải 2001. Tương tự, giả sử p1 là một con trỏ nguyên với giá trị hiện tại là 2000. Cũng giả sử rằng số nguyên chiếm 2 bytes bộ nhớ. Sau khi thực hiện lệnh` p1--; `thì p1 có giá trị là 1998 chứ không phải 1999.
- Tất cả con trỏ sẽ tăng hay giảm với đơn vị là kích thước của kiểu dữ liệu của nó
- Ngoài toán tứ (++) hay (--) ta có thể cộng hay trừ số nguyên với con trỏ(Tăng giảm địa chỉ không tăng giảm giá trị )

*VD:*

```
#include<iostream>
using namespace std;
//de
int main(int argv,char** argc)
{
    int a=20,b=15;
    int *p1;
    int *p2;
    p1=&a;
    p2=&b;
    int temp;
    temp=*p1;
    *p1=*p2;
    *p2=temp;
    
    cout<<a<<" "<<b<<endl;
    cout<<"dcp1"<<" "<<p1<<endl;
    p1++;
    cout<<"dcp1"<<" "<<p1<<endl;
    
    return 0;
}

```

**End**

## VIDEO 3 BAI 68 CON TRO VOID VA CON TRO NULL

**NOI DUNG**

- Kiểu dữ liệu khi khai báo biến con trỏ chính là kiểu dữ liệu mà con trỏ có thể trỏ đến. Địa chỉ đặt vào biến con trỏ phải cùng kiểu với kiểu của con trỏ

1. Con trỏ void

- Là một loại con trỏ đặc biệt mà có thể trỏ đến bất kì kiểu dữ liệu nào. Cú pháp:

` void *pointerVariable;`

- Tuy nhiên, tuỳ thuộc con trỏ void đang trỏ đến kiểu dữ liệu nào, ta phải ép về đúng kiểu tương ứng khi dùng trong các biểu thức 

*VD:*

- p đang trỏ đến biến nguyên a, để tăng giá trị của biến a lên 10, dùng lệnh

`(int*)*p+10;`

- Tương tự với biến thực f

`(float*)*p+10`

2. Con trỏ NULL

- Một con trỏ hiện hành không trỏ đến một địa chỉ bộ nhớ hợp lệ thì được gán giá trị NULL. Bởi qui ước, con trỏ NULL là con trỏ không trỏ đến đâu cả và không nên dùng
- Nếu chương trình vô tình dùng con trỏ NULL như dưới đây thì sẽ nhận lỗi khi thực thi chương trình (run time-error)

```
int *p;
cout<<"gia tri con tro p tro den la"<<*p;
```

*VD:*



```
#include<iostream>
using namespace std;
//de
int main(int argv,char** argc)
{
    int a=10;
    float b=2.5;
    int *p1=&a;
    float *p2=&b;
    void *p;
    p=&a;
    (*(int*)p)=5;
    cout<<"a="<<a<<endl;
    p=&b;
    (*(float*)p)=10.9;
    cout<<"b="<<b<<endl;
    
    int *y=new int;
    cout<<"dia chi cua y la "<<y<<endl;
    cout<<*y<<endl;
    
    return 0;
}

```

**End**

## VIDEO 4 BAI 69 CON TRO VA MANG

**NOI DUNG**

- Giữa con trỏ và mảng có một sự quan hệ gần

```
#include<iostream>
using namespace std;
//de
int main(int argv,char** argc)
{
    int a[]={2,3,4,5,6,9};
    for(int i=0;i<6;i++)
    {
        cout<<a[i]<<"\t";
    }
    cout<<endl;
    
    //con tro
    int *p=a;
    for(int i=0;i<5;i++)
    {
        cout<<*(p+i)<<"\t";
    }
    cout<<endl;
    
    //doi gia tri thi keo theo
    *(p+3)=100;
    for(int i=0;i<6;i++)
    {
        cout<<a[i]<<"\t";
    }
    cout<<endl;
    
    //cach khac
    for(int i=0;i<6;i++)
    {
        cout<<p[i]<<"\t";
    }
    cout<<endl;
    return 0;
}

```

**End**

## VIDEO 5 BAI 70 MANG CON TRO

**NOI DUNG**

- Mỗi biến con trỏ là một biến đơn. Ta có thể tạo mảng của các con trỏ. Mỗi phần tử của mảng là một con trỏ thông thương. Cú pháp:

`type*pointerArray[elements];`

*Trong đó*

- type: kiểu dữ liệu mà con trỏ phần tử trỏ đến
- pointerArray: Tên mảng con trỏ
- Elements: số phần tử của mảng con trỏ

*VD:*

`int *p[5];`

- Lệnh này khai báo mảng con trỏ p có 5 phần tử 
- `p[0]=&a;` gán địa chỉ của biến nguyên a cho con trỏ p[0]
- `p[2]=p[0];` sao chép địa chỉ có trong p[0] vào p[2]
- `b=*p[0];` gán giá trị tại địa chỉ p[0] trỏ đến biến b

```
#include<iostream>
using namespace std;
//de
int main(int argv,char** argc)
{
    int *p[10];
    for(int i=0;i<10;i++)
    {
        //quan trong
        p[i]=new int;
        *p[i]=i*2;
    }
    for(int i=0;i<10;i++)
    {
        cout<<p[i]<<"==>"<<*p[i]<<endl;
    }
    return 0;
}

```

**End**

## VIDEO 6 BAI 71 TUONG QUAN GIU MANG 2 CHIEU VA CON TRO CAP 2

**NOI DUNG**

```
#include<iostream>
using namespace std;
//de
int main(int argv,char** argc)
{
    int **p=new int *[7];
    for (int i=0;i<7;i++)
    {
        p[i]=new int [8];//*(p+i)=new int [8]
    }
    for (int i=0;i<7;i++)
    {
        for (int j=0;j<8;j++)
        {
            p[i][j]=i+j;//*(*(p+i)+j)=i+j;
        }
    }
    
    for (int i=0;i<7;i++)
    {
        for (int j=0;j<8;j++)
        {
            //cout<<*(*(p+i)+j)<<"\t";
            cout<<p[i][j]<<"\t";

        }
        cout<<endl;
    }
    
    //huy bo nho
    for(int i=0;i<7;i++)
    {
        delete *(p+i);
        *(p+i)=NULL;
    }
    delete p;
    p=NULL;
    
    
    return 0;
}

```

**End**

## VIDEO 8 BAI 72 BTRL-CON TRO 1

*Đề:  Viết hàm hoán vị hai biến thực a,b bằng cách sử dụng con trỏ(đối vào là 2 con trỏ). Viết chương trình chính nhập hai số thực a,b. Sử dụng hàm trên để đổi chỗ a,b*

```
#include<iostream>
#include<math.h>
using namespace std;
//de
void swap(double *&p1,double *&p2);
void output(double a,double b);
int main(int argv,char** argc)
{
    double a;
    double b;
    cout<<"nhap vao 2 gia tri a va b"<<endl;
    cin>>a>>b;
    swap(a,b);
    output(a,b);
    return 0;
    
    

    
}


//ham xuat
void output(double a,double b)
{
    cout<<"so sau khi hoan doi la "<<endl;
    cout<<"a="<<a<<endl;
    cout<<"b="<<b<<endl;
}

//ham doi
void swap(double *&p1,double *&p2)
{
    double temp=*p1;
    *p1=*p2;
    *p2=temp;
}

```

**End**

## VIDEO 9 BAI 73  BTRL-CON TRO 2

*Đề: Viết chương trình nhập vào một mảng a gồm n phần tử nguyên ngẫu nhiên [0...100]. Sắp xếp mảng theo chiều giảm dần (Lưu ý sử dụng tên mảng như con trỏ và sử dụng con trỏ)*

```
#include<iostream>
#include<time.h>
#include<stdlib.h>
#include<math.h>
using namespace std;
//de
void inputArray(int *&a,int n);
void outputArray(int *&a,int n);
void swap(int *&a,int *&b);
void sort(int *&a,int n);
int main(int argv,char** argc)
{
    int n;
    int *a;//quang trong
    do
    {
        cout<<"nhap so phan tu cho mang"<<endl;
        cin>>n;
        if(n<=0)
            cout<<"nhap lai"<<endl;
    }while(n<=0);
    inputArray(a,n);
    cout<<"mang vua nhap la"<<endl;
    outputArray(a,n);
    sort(a,n);
    cout<<"mang sau sap xep la"<<endl;
    outputArray(a,n);
    return 0;
    
}

//nhap mang random
void inputArray(int *&a,int n)
{
    srand(time(NULL));
    a=new int[n];
    for(int i=0;i<n;i++)
    {
        a[i]=rand()%100;
        //*(p+i)
    }
}

//xuat mang
void outputArray(int *&a,int n)
{
    for(int i=0;i<n;i++)
    {
        cout<<a[i]<<" ";
    }
    cout<<endl;
}

//hoan doi
void swap(int *&a,int *&b)
{
    int temp=*a;
    *a=*b;
    *b=temp;
}

//sap xep
void sort(int *&a,int n)
{
    int temp;
    for(int i=0;i<n-1;i++)
    {
        for(int j=i+1;j<n;j++)
        {
            if(a[i]<a[j])
            {
                swap(*(a+i),a[j]);
            }
                
        }
    }
}


```

**End**

## VIDEO 10 BAI 74 BTRL-CON TRO 3

*Đề: Hãy viết hàm để nhập/xuất vào một ma trận vuông n với các số ngẩu nhiên [-50;100] và hàm tìm phần tử max của ma trận này*

```
#include<iostream>
#include<time.h>
#include<stdlib.h>
using namespace std;
//de
void inputArray (int **&a,int n);
void outputArray (int **a,int n);
int max(int **a,int n);
int main(int argv, char** argc)
{
    int **a;
    int n;
    cout<<"nhap n cua ma tran vuong cap n"<<endl;
    cin>>n;
    inputArray(a,n);
    cout<<"mang sau khi nhap la"<<endl;
    outputArray(a,n);
    int kq=max(a,n);
    cout<<"phan tu max cua ma tran la:"<<endl;
    cout<<kq<<endl;
    return 0;
    
    
}

//nhap mang
void inputArray (int **&a,int n)
{
    a=new int*[n];
    for(int i=0;i<n;i++)
    {
        *(a+i)=new int[n];
    }
    for (int i=0;i<n;i++)
    {
        for(int j=0;j<n;j++)
        {
            *(*(a+i)+j)=-50+rand()%151;
        }
    }
}

//xuat mang
void outputArray (int **a,int n)
{
    for (int i=0;i<n;i++)
    {
        for(int j=0;j<n;j++)
        {
            cout<<*(*(a+i)+j)<<"\t";
            
        }
        cout<<endl;
    }
    
}
int max(int **a,int n)
{
    int temp=*(*(a+0)+0);
    for(int i=0;i<n;i++)
    {
        for(int j=0;j<n;j++)
        if(temp<*(*(a+i)+j))
        {
            temp=*(*(a+i)+j);
        }
    }
    return temp;
}

```

**End**



## VIDEO 11 BAI 75 BTRL-CON TRO 4

*Đề: Viết hàm cộng hai ma trận vuông cấp n(sử dụng con trỏ)*

```
#include<iostream>
#include<time.h>
#include<stdlib.h>
using namespace std;
//de
void inputA(int **&a,int n);
void outputA(int **a,int n);
int **sumA(int **&a,int **&b,int n);
int main(int argc,char** argv)
{
    srand(time(NULL));
    int**a;
    int**b;
    int n;
    cout<<"nhap n cho ma tran vuong cap n"<<endl;
    cin>>n;
    inputA(a,n);
    inputA(b,n);
    cout<<"mang a:"<<endl;
    outputA(a,n);
    cout<<"mang b"<<endl;
    outputA(b,n);
    int **kq=sumA(a,b,n);
    cout<<"tong hai ma tran la"<<endl;
    outputA(kq,n);
    return 0;
}

//random mang
void inputA(int **&a,int n)
{
    srand(time(NULL));
    a=new int*[n];
    for(int i=0;i<n;i++)
        *(a+i)=new int[n];
    for(int i=0;i<n;i++)
    {
        for(int j=0;j<n;j++)
        {
            a[i][j]=rand()%11;
        }
    }
}

//xuat mang
void outputA(int **a,int n)
{
    for(int i=0;i<n;i++)
    {
        for(int j=0;j<n;j++)
        {
            cout<<a[i][j]<<"\t";
        }
        cout<<endl;
    }
    
}
int **sumA(int **&a,int **&b,int n)
{
    int **c=new int*[n];
    for(int i=0;i<n;i++)
        *(c+i)=new int[n];
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

**End**



## VIDEO 12 BAI 76 BTRL-CON TRO 5

*Đề:*

- Dùng con trỏ để khai báo mảng một chiều (dùng con trỏ), thực hiện các chức năng:
  - Viết hàm cấp phát bộ nhớ cho mảng có n phần tử
  - Viết hàm nhập dữ liệu cho mảng từ bàn phím
  - Viết hàm xuất mảng ra màn hình
  - Viết hàm trả về 1 mảng con trỏ có tối đa 3 số lớn nhất trong dãy gốc

```
#include<iostream>
using namespace std;
//de
int *noArray(int n);
void inputArray(int *&a, int n);
void outputArray(int *a, int n);
int *maximumList(int *a,int n);
void sort(int *&a,int n);
int main(int argv, char** argc)
{
    int n=5;
    int *a=noArray(n);
    inputArray(a,n);
    cout<<"du lieu sau nhap la"<<endl;
    outputArray(a,n);
    int *max=maximumList(a,n);
    cout<<"3 phan tu lon nhat mang la"<<endl;
    outputArray(max,3);
    return 0;
    
}

//cap phat bo nho
int *noArray(int n)
{
    int *a=new int[n];
    return a;
}

//nhap mang
void inputArray(int *&a, int n)
{
    for(int i=0;i<n;i++)
    {
        cout<<"a["<<i<<"]=";
        cin>>a[i];//*(a+i)
    }
}

//xuat mang
void outputArray(int *a, int n)
{
    for(int i=0;i<n;i++)
    {
        cout<<*(a+i)<<"\t";
    }
    cout<<endl;
}

//danh sach max
int *maximumList(int *a, int n)
{
    int m=n>3?3:n;
    int *p=noArray(m);
    sort(a,n);
    for(int i=0;i<m;i++)
    {
        *(p+i)=*(a+i);
    }
    return p;
    
}

//sap xep giam dan
void sort(int *&a,int n)
{
    for(int i=0;i<n-1;i++)
    {
        for(int j=i+1;j<n;j++)
        {
            if(a[i]<a[j])
            {
                int temp=a[i];
                a[i]=a[j];
                a[j]=temp;
            }
        }
    }
}

```

**End**

