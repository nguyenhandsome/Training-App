## REPORT THE PROCESS OF WATCHING C++ SERIES 2 

# VIDEO 1 BAI 18 CAU LENH IF

**NOI DUNG**

*DẠNG 1* 

- Cú pháp:
```
if(experession)
      statement;
```
- Ý nghĩa: Expression được định trị. Nếu kết quả là True thì statement được thực thi còn không thì không làm gì cả

***VD: Viết chương trình nhập vào 1 số nguyên a. In ra màn hình kết quả a có phải số dương hay không ?***

```
#include<iostream>
using namespace std;
//Viết chương trình nhập vào 1 số nguyên a. In ra màn hình kết quả a có phải số dương hay không ?
int main(int argc, char** argv)
{
    int a;
    cout<<"nhap so nguyen a"<<endl;
    cin>>a;
    if(a>=0)
        cout<<a<<" la so nguyen duong"<<endl;
    return 0;
}
```
**End**

# VIDEO 2 BAI 19 CAU LENH IF...ELSE

**NOI DUNG** 

*Dạng 2*

- Cú pháp

```
if(experession)
      statement 1;
else
      statement 2;
```

- Ý nghĩa
    - Nếu experession được định là true thì statement 1 được thực thi
    - Ngược lại statement 2 được thực thi 

***VD: Viết chương trình nhập vào 1 số nguyên a. In ra màn hình kết quả a là số âm hay số dương ?***

```
#include<iostream>
using namespace std;
//Viết chương trình nhập vào 1 số nguyên a. In ra màn hình kết quả a có phải số dương hay không ?
int main(int argc, char** argv)
{
    int a;
    cout<<"nhap so nguyen a"<<endl;
    cin>>a;
    if(a>=0)
        cout<<a<<" la so nguyen duong"<<endl;
    else
        cout<<a<<" la so nguyen am"<<endl;
    return 0;
}
```

**End**

# VIDEO 3 BAI 20 CAU LENH IF ELSE LONG NHAU

- Ta có thể sử dụng các câu lệnh `if else' lồng nhau. Khi dùng thì else sẽ kết hợp với if gần nhất chưa có else

```
#include<iostream>
using namespace std;
//Viết chương trình nhập vào 1 số nguyên a. In ra màn hình kết quả a có phải số dương hay không ?
int main(int argc, char** argv)
{
    float n;
    cout<<"xet diem tot nghiep"<<endl;
    cout<<"nhap diem trung binh cua ban "<<endl;
    cin>>n;
    if(n<0||n>10)
        cout<<"diem khong hop le"<<endl;
    else
    {
        if(n>=5)
            cout<<"ban dau"<<endl;
        else
            cout<<"ban rot"<<endl;
    }
    return 0;
}
```

**End**

# VIDEO 4 BAI 21 TOAN TU 3 NGOI VA CAU LENH IF ELSE

**NOI DUNG**

- Có dạng:

```
<dk>?<bieu thuc 1>:<bieu thuc 2>
```

- Ý nghĩa: Nếu <dk> đúng thì<bieu thuc 1> thuc hien, ngược lại <bieu thuc 2> thuc hien
- Là dạng rút gọn của if...else

***VD:***

```
#include<iostream>
using namespace std;

int main()
{
    int n;
    cout<<"nhap so nguyen"<<endl;
    cin>>n;
    cout<<(n%2==0?"la so chan\n":"la so le\n");
   /* if(n%2==0)
        cout<<"la so chan"<<endl;
    else
        cout<<"la so le"<<endl;*/
    return 0;
}
```

# VIDEO 5 BAI 22 CAU LENH SWITCH

**NOI DUNG**

- Cấu trúc Switch là 1 cấu trúc lựa chọn có nhiều nhánh, được sử dụng khi có nhiều lựa chọn.
- Cú pháp:

```
switch(expression)
{
    case value_1:statement_1;[break;]
    ...
    case value_n:statement_n;[break;]
    [default:statement;]
}
```

- Giải thích:
    - Expression sẽ được định trị.
    - Nếu giá trị của expression bằng value_1 thì thực hiện statement_1 và thoát
    - Nếu khác value_1 thì so sánh với value_2, nếu bằng value_2 thì thực hiện statement_2 và thoát...,so sánh tới value_n
    - Nếu tất cả các phép so sánh đều sai thì thực hiện statement của default.
**VD: Nhập 1 số nguyên, chia số nguyên này cho 2 lấy phần dư. Kiểm tra nếu phần dư bằng 0 thì in ra thông báo "la số chẳn", nếu bằng 1 thì thông báo"là số lẻ"**

```
#include<iostream>
using namespace std;

int main()
{
    int n,cd;
    cout<<"nhap so nguyen"<<endl;
    cin>>n;
    cd=n%2;
    switch(cd)
    {
        case 0:
            cout<<"la so chan"<<endl;
            break;
        case 1:
            cout<<"la so le"<<endl;
            break;
        default:
            cout<<"so ban nhap sai"<<endl;
            
    }
    /*th2: nhieu case cung thuc hien 1 lenh
     int x=1;
     switch(x)
    {
     case 1:
     case 2:
     case 3:
     cout<<"xyz"<<endl;
     break;
     case 4:
     case 9:
     cout<<"w"<<endl;
     break;
     default:
     cout<<"chua ho tro"<<endl;
    }*/
    return 0;
}
```

**End**

# VIDEO 6 BAI 23 BTRL-GIAI PHUONG TRINH BAC 1

**NOI DUNG**

```
#include<iostream>
#include<iomanip>
using namespace std;
int main(int argc, char** argv)
{
    int a,b;
    float x;
    cout<<"giai phuong trinh bac 1 ax*b=0"<<endl;
    cout<<"nhap a va b"<<endl;
    cin>>a>>b;
    if(a==0 && b==0 )
        cout<<"phuong trinh vo so nghiem"<<endl;
    else if (a==0 && b!=0)
        cout<<"phuong trinh vo nghiem"<<endl;
    else
    {
        if (b==0)
            cout<<"x=0"<<endl;
        else
        {
            x=-b*1.0/a;
            cout<<"ket qua la = "<<x<<endl;
            cout<<"ket qua sau khi rut gon la "<<setprecision(2)<<x<<endl;
        }
    }
    return 0;
}
```

**End**

# VIDEO 7 BAI 24 BTRL-PHUONG TRINH BAC 2

**NOI DUNG**

```
#include<iostream>
#include<math.h>
using namespace std;
//phuong trinh bac 2
int main(int argc, char** argv)
{
    double a,b,c;
    double dt,x1,x2;
    cout<<"giai phuong trinh bac 2 ax^2+bx+c=0 "<<endl;
    cout<<"nhap lan luoc cho he so cua a,b,c"<<endl;
    cin>>a>>b>>c;
    if(a==0)
    {
     if(b==0&&c==0)
        cout<<"phuong trinh co vo so nghiem"<<endl;
     else if (b==0)
        cout<<"phuong trinh vo nghiem"<<endl;
     else 
        cout<<"quay lai phuong trinh bac 1"<<endl;
    }
    else if(a+b+c==0)
    {
        x1=1;
        x2=c/a;
        cout<<"pt co 2 nghiem x1= "<<x1<< " x2= "<<x2<<endl;
    }
    else if(a-b+c==0)
    {
        x1=-1;
        x2=-c/a;
        cout<<"pt co 2 nghiem x1= "<<x1<< " x2= "<<x2<<endl;
    }
    else
    {
        dt=pow(b,2)-4*a*c;
        if (dt<0)
            cout<<"phuong trinh vo nghiem"<<endl;
        else if (dt==0)
        {
            x1=-b*1.0/(2*a);
            cout<<"phuong trinh co 2 nghiem kep x1=x2= "<<x1<<endl;
        }
        else
        {
            x1=(-b-sqrt(dt))/2*a;
            x2=(-b+sqrt(dt))/2*a;
            cout<<"pt co 2 nghiem phan biet x1= "<<x1<< " x2= "<<x2<<endl;
            
        }
        
    }
    return 0;
}
```

# VIDEO 8 BAI 25 BTRL-TINH TIEU THU DIEN

**NOI DUNG**

- Khai báo hằng số

*Đề: Nhập vào số KwH tiêu thụ điện. Tính tiền điện phải trả biết rằng cách thức tính tiền theo qui định như sau: 
a) 100 Kwh định mức đầu tiên có đơn giá trung bình là 600đ/Kwh
b) Các kwh từ 101-150 có đơn giá là 700đ/kwh
c) 151-200 900đ/kwh
d) 201 trở lên 1100đ/kwh*

```
#include<iostream>
#include<math.h>
using namespace std;
//tinh tien dien
int main(int argc, char** argv)
{
    int n;
    int t;
    const int gia1=600;
    const int gia2=700;
    const int gia3=900;
    const int gia4=1100;
    cout<<"nhap so kwh tieu thu"<<endl;
    cin>>n;
    if (n<=0)
        cout<<"nhap lai"<<endl;
    else
    {
        if (n<=100)
            t=n*gia1;
        else if (n>100&&n<=150)
            t=100*gia1+(n-100)*gia2;
        else if (n>150&&n<=200)
            t=100*gia1+150*gia2+(n-150)*gia3;
        else
            t=100*gia1+150*gia2+200*gia3+(n-200)*gia4;
    }
    cout<<"tong tien la "<<t<<endl;
    return 0;
}
```
 **End**


 # VIDEO 9 BÀI 26 BTRL-TINH TOAN SO HOC

 **NOI DUNG**

 *Viết chương trình nhập từ bàn phím 2 số a,b và số ký tự ch
 - ch "+" thì thực hiện phép tính a+b và in kq ra màn hinh
 - ch "-" a-b
 - ch "*" a*b
 - ch "/" a/b"

```
#include<iostream>
#include<iomanip>
using namespace std;
//tinh tien dien
int main(int argc, char** argv)
{
    double a,b;
    double s;
    char ch;
    cout<<"nhap 2 so a va b"<<endl;
    cin>>a>>b;
    cout<<"nhap ky tu (+,-,*,/)"<<endl;
    cin>>ch;
    switch (ch)
    {
        case '+':
        {
            s=a+b;
            cout<<a<<"+"<<b<<"="<<s<<endl;
            break;
        }
        case '-':
        {
            s=a-b;
            cout<<a<<"-"<<b<<"="<<s<<endl;
            break;
        }
        case '*':
        {
            s=a*b;
            cout<<a<<"*"<<b<<"="<<s<<endl;
            cout<<"ket qua rut gon "<<a<<"*"<<b<<"="<<setprecision(2)<<s<<endl;
            break;
        }
        case '/':
        {
            if (b==0)
                cout<<"b phai khac 0"<<endl;
            else
            {
            s=a*1.0/b;
            cout<<a<<"/"<<b<<"="<<s<<endl;
            cout<<"ket qua rut gon "<<a<<"/"<<b<<"="<<setprecision(2)<<s<<endl;
            break;
            }
        }
        default:
            cout<<"nhap sai"<<endl;
    }
    return 0;
}
```

# VIDEO 10 BAI 27 BTRL-TINH CHU VI DIEN TICH TAM GIAC

**NOI DUNG**

*Đề: nhập cạnh a>=0,b>=0,c>=0. Nếu a,b,c tạo thành 1 tam giác thì hãy tính và xuất chu vi diện tích hinh tam giac. Ngươc lại thông báo "không tạo thành tam giác"*

```
#include<iostream>
#include<iomanip>
#include<math.h>
using namespace std;
//tinh chu vi dien tich tam giac
int main(int argc, char** argv)
{
    double a,b,c;
    double p,s;
    double n;
    cout<<"nhap 3 canh cua tam giac"<<endl;
    cin>>a>>b>>c;
    if(a>=0 &&b>=0&&c>=0)
    {
       
    if(a+b>c&&a+c>b&&b+c>a)
    {
        p=a+b+c;
        n=p/2.0;
        s=sqrt(n*(n-a)*(n-b)*(n-c));
        cout<<"cv la "<<p<<" dt la "<<s<<endl;
    }
        else
            cout<<"khong tao thanh 1 tam giac"<<endl;
    }
    else
        cout<<"khong tao thanh 1 tam giac"<<endl;
    return 0;
}

```

**End**

# VIDEO 11 BTTRL

**NOI DUNG**

*1) NHẬP SỐ THỰC A,B,C. TÌM SỐ LỚN NHÂT
 2) NHẬP VÀO THÁNG t (1<=t<=12). CHO BIẾT THÁNG t CÓ BAO NHIÊU NGÀY. RIÊNG THÁNG 2 THÌ PHẢI KIỂM TRA NĂM NHUẬN
 3) NHẬP MỘT SỐ N TỐI ĐA CÓ 2 CHỮ SỐ. HÃY BIẾT CÁCH ĐỌC RA DẠNG CHỮ
 4) NHẬP 1 NGÀY (NGÀY/THÁNG/NĂM). TÌM NGÀY KẾ SAU NGÀY VỪA NHẬP(NGÀY/THÁNG/NĂM)
 5) Hãy viết chương trình cho nhập vào ký tự biểu diễn một ký số của hệ thập lục phân và cho biết giá trị thập phân tương ứng. Trường hợp ký tự nhập vào không thuộc các ký số trên, đưa ra thông báo lỗi:"He thap luc phan khong dung ky so nay"*

 
```
#include<iostream>
using namespace std;
//cau 1
int main(int argc, char** argv)
{
    float a,b,c;
    cout<<"so sanh 3 so thuc a,b,c "<<endl;
    cout<<"nhap la luot 3 so a b c"<<endl;
    cin>>a>>b>>c;
    if(a>=b)
    {
        if(a>c&&a>b)
            cout<<"so lon nhat la a="<<a<<endl;
        else if(a==c&&a>b||a>c&&a==b)
            cout<<"khong ton tai so lon nhat"<<endl;
        else if(a==c && a==b)
            cout<<"ca 3 so bang nhau"<<endl;
        else if(a<c)
        {
            if(b>c)
                cout<<"so lon nhat la b="<<b<<endl;
            else if (c>b)
                cout<<"so lon nhat la c= "<<c<<endl;
        }
    }
    else
    {
        if(b>c)
            cout<<"so lon nhat la b="<<b<<endl;
        else if (c>b)
            cout<<"so lon nhat la c= "<<c<<endl;
        else
            cout<<"khong co so lon nhat"<<endl;
    }
    return 0;
}
```

```
#include<iostream>
using namespace std;
//cau 2
int main(int argc, char** argv)
{
    int t,n;
    int a;
    cout<<"nhap vao thang"<<endl;
    cin>>t;
    if(1<=t&&t<=12)
        a++;
    switch(a)
    {
        case 1:
        {
            switch(t)
            {
                case 1:
                case 3:
                case 5:
                case 7:
                case 8:
                case 10:
                case 12:
                    cout<<"thang "<<t<<" co 31 ngay"<<endl;
                    break;
                case 2:
                {
                    cout<<"nhap them nam"<<endl;
                    cin>>n;
                    if(n%4==0&&n%100!=0&&n>0 )
                        cout<<"thang "<<t<<" co 29 ngay"<<endl;
                    else if(n>0)
                        cout<<"thang "<<t<<" co 28 ngay"<<endl;
                    else
                        cout<<"nhap lai"<<endl;
                    break;
                }
                default:
                {
                    cout<<"thang "<<t<<" co 30 ngay"<<endl;
                    break;
                }
            }
            break;
        }
        default:
            cout<<"nhap lai"<<endl;
    }
    return 0;
}
```

```
#include<iostream>
using namespace std;
//cau 3
int main(int argc, char** argv)
{
    int n;
    cout<<"nhap vao so toi da 2 chu so"<<endl;
    cin>>n;
    if(n<100)
    {
        if(n>=10)
        {
        //xet 2 chu so
        int temp = n / 10;
        if (temp == 1)
            cout<<"muoi ";
        else if (temp == 2)
            cout<<"hai muoi ";
        else if (temp == 3)
            cout<<"ba muoi ";
        else if (temp == 4)
            cout<<"bon muoi ";
        else if (temp == 5)
            cout<<"nam muoi ";
        else if (temp == 6)
            cout<<"sau muoi ";
        else if (temp == 7)
            cout<<"bay muoi" ;
        else if (temp == 8)
            cout<<"tam muoi ";
        else if (temp == 9)
            cout<<"chin muoi ";
        }
        //xet 1 chu so
        int temp=n%10;
        if (temp == 1)
            cout<<"mot ";
        else if (temp == 2)
            cout<<"hai ";
        else if (temp == 3)
            cout<<"ba  ";
        else if (temp == 4)
            cout<<"bon ";
        else if (temp == 5)
            cout<<"nam ";
        else if (temp == 6)
            cout<<"sau ";
        else if (temp == 7)
            cout<<"bay " ;
        else if (temp == 8)
            cout<<"tam ";
        else if (temp == 9)
            cout<<"chin ";
    }
    else
        cout<<"nhap lai"<<endl;
    return 0;
}
```

```
#include<iostream>
using namespace std;
//cau 4
int main(int argc, char** argv)
{
    int d,m,y;
    int temp=0;
    int a;
    cout<<"input day month and year"<<endl;
    cin>>d>>m>>y;
    if(d<0||d>31||m<0||m>12||y<0)
    {
        temp++;
    }
    cout<<d<<"/"<<m<<"/"<<y<<endl;
    switch(temp)
    {
        case 0:
        {
            switch (m)
            {
                case 1:
                case 3:
                case 5:
                case 7:
                case 8:
                case 10:
                case 12:
                {
                    if (d<31)
                    {
                        d++;
                    }
                    else
                        d=1;
                    break;
                }
                case 2:
                {
                    if(y%4==0&&y%100!=0)
                    {
                        if(d<29)
                            d++;
                        else if(d>=30)
                            a++;
                        else
                            d=1;
                    }
                    else
                    {
                        if(d<28)
                            d++;
                        else if(d>=29)
                            a++;
                        else
                            d=1;
                    }
                    break;
                }
                default:
                {
                    if(d<29)
                        d++;
                    else
                        d=1;
                    break;
                }
            }
            if(a==0)
            {
            if(m<12&&d==1)
                m++;
            else if (m>=12&&d==1)
            {
                m=1;
                y++;
            }
                 cout<<"the next is "<<d<<"/"<<m<<"/"<<y<<endl;
            }
            else
                cout<<"nhap lai"<<endl;
            break;
        }
        default:
            cout<<"nhap lai"<<endl;
            
            
    }
    return 0;
}

```

```
#include<iostream>
using namespace std;
//cau 5
int main(int argc, char** argv)
{
    unsigned char n;
    unsigned char a;
    unsigned char temp;
    int m;
    int b;
    cout<<"nhap ky so n"<<endl;
    cin>>n;
    temp=n;
    temp=m;
    a=n;
    switch(m)
    {
        case 0:
        case 1:
        case 2:
        case 3:
        case 4:
        case 5:
        case 6:
        case 7:
        case 8:
        case 9:
        {
            cout<<"he thap luc phan "<<n<<" chuyen qua he thap phan la "<<n<<endl;
            b++;
            break;
        }
    }
    if(b==0)
    {
    switch (a)
    {
        case 'A':
        {
            cout<<"he thap luc phan "<<n<<" chuyen qua he thap phan la 11"<<endl;
            break;
        }
        case 'B':
        {
            cout<<"he thap luc phan "<<n<<" chuyen qua he thap phan la 12"<<endl;
            break;
        }
        case 'C':
        {
            cout<<"he thap luc phan "<<n<<" chuyen qua he thap phan la 13"<<endl;
            break;
        }
        case 'D':
        {
            cout<<"he thap luc phan "<<n<<" chuyen qua he thap phan la 14"<<endl;
            break;
        }
        case 'E':
        {
            cout<<"he thap luc phan "<<n<<" chuyen qua he thap phan la 15"<<endl;
            break;
        }
        case 'F':
        {
            cout<<"he thap luc phan "<<n<<" chuyen qua he thap phan la 16"<<endl;
            break;
        }
        default :
            cout<<"he thap phan khong su dung ky so nay"<<endl;
    }
            
}
    return 0;
}
```

**End**

# VIDEO 12 BAI 29: VONG WHILE

**NOI DUNG**

- Cú pháp
```
while(exprecision)
    statement;
```

- Ý nghĩa
- B1: Exprecesion được đình trị
- B2: Nếu kq là true thì statement thực thi và quay lại bước 1
- B3: Nếu kq false thì thoát khỏi vòng lặp

*vd: viết chương trình tính tổng số nguyên tử từ 1->n*

```
#include<iostream>
using namespace std;
int main(int argc, char** argv)
{
    int n;
    int s;
    cout<<"nhap n"<<endl;
    cin>>n;
    int i=0;
    while(i<=n)
    {
        s+=i;
        i++;
    }
    cout<<"tong la "<<s<<endl;
    return 0;
}

```


**End**


