# REPORT THE PROCESS C++ SERIES 3

## VIDEO 1 BAI 30 VONG DO-WHILE

**Noi dung**

```
do
{
statement;
}while(expression);
```

**Y nghia**

- statement được thực hiện

- Expression được đình trị

- Nếu expression là true thì quay lại bước 1

- false thì thoát khỏi vòng lặp

  *VD: Viết chương trình in dãy số nguyên từ 1 đến 5*

  ```
  #include<iostream>
  using namespace std;
  //vd
  int main(int argc, char** argv)
  {
      int n=1;
      cout<<"display one to five"<<endl;
      do
      {
          cout<<n<<endl;
          n++;
          //n+=1;
      }while(n<=5);
      return 0;
  }
  
  ```

  **End**

  

  ## VIDEO 2 BAI 31 VONG FOR

  **NOI DUNG**

  - Cú pháp:

    ```
    for(exp1;exp2;exp3)
    statement;
    ```

  - Ý nghĩa:
  - exp1: là biểu thức khởi tạo được thưc hiện
  - exp2: biểu thức dk
  - exp3: biểu thức dk lặp

  *VD Viết chương trình tính tổng các số nguyên từ 1 đến n*

  ```
  #include<iostream>
  using namespace std;
  //vd
  int main(int argc, char** argv)
  {
      int n;
      int s=0;
      cout<<"nhap n"<<endl;
      cin>>n;
      for(int i=1;i<=n;i++)
      {
          s+=i;
      }
      cout<<"tong cac so tu 1 den "<<n<<" bang "<<s<<endl;
      return 0;
  }
  
  ```

  *Lưu ý*

  - C/C++ cho phép exp1 là 1 định nghĩa biến
  - Bất kỳ biểu thức nào trong vòng lặp for đều có thể rỗng
  - Xoá tất cả các biểu thức trong for sẽ cho 1 vòng lặp vô tận

**End**

## VIDEO 3 BAI 32 CAU LENH BREAK

**NOI DUNG**

- Trong vòng lặp, dùng break để thoát khỏi vòng lặp chứa nó trực tiếp. Được sử dụng rất nhiều trong quá trình điều hướng vòng lặp
- Lệnh break dùng để thoát khỏi một cấu trúc điều khiển mà không chở đến biểu thức điều kiện được định trị
- Khi thực hiện bên trong 1 cấu trúc vòng lặp, điều khiển(control flow) tự động nhảy đến lệnh đầu tiên ngay sau cấu trúc lặp đó
- Không sử dụng lệnh break bên ngoài các cấu trúc lặp

*VD Nhập 1 số nguyên n, tính tổng từ 1 đến n, khi tổng >= 9 thì dừng*

```
#include<iostream>
using namespace std;
//vd
int main(int argc, char** argv)
{
    int n;
    int s=0;
    cout<<"nhap n"<<endl;
    cin>>n;
    for (int i=1;i<=n;i++)
    {
        s+=i;
        if(s>=9)
            break;
    }
    cout<<"tong la "<<s<<endl;
    return 0;
}

```

**End**

## VIDEO 4 BAI 33 CAU LENH CONTINUE

**NOI DUNG**

- Dùng continue để nhảy đến lần lặp tiếp theo trong vòng lặp. Được sử dụng rất nhiều trong quá trình điều hướng vòng lặp
- Dùng để kết thúc lần lặp hiện tại và bắt đầu lần lặp tiếp theo
- Chỉ được dùng trong các thân các vòng lặp
- thường đi kèm với if

*VD: Nhập n, tính tổng 1 đến n ngoại trừ các số 2, 4*

```
#include<iostream>
using namespace std;
//vd
int main(int argc, char** argv)
{
    int n;
    int s=0;
    cout<<"nhap n"<<endl;
    cin>>n;
    for (int i=1;i<=n;i++)
    {
        if(i==2||i==4)
            continue;
        s+=i;
    }
    cout<<"tong la "<<s<<endl;
    return 0;
}

```

**End**

## VIDEO 5 BAI 34 VONG LAP LONG NHAU

**NOI DUNG**

- Vòng lặp lồng nhau được dùng rất nhiều trong các giải thuật xử lý. Vòng lặp này có thể chứa các vòng lặp khác

**VD: vẽ hình tam giác**

```
#include<iostream>
using namespace std;
//vd
int main(int argc, char** argv)
{
    int h;
    cout<<"nhap chieu cao"<<endl;
    cin>>h;
    for(int i=0;i<h;i++)
    {
        for(int j=0;j<h;j++)
        {
            if(j==0||i==h-1||i==j)
                cout<<".";
            else
                cout<<" ";
        }
        cout<<endl;
    }
    return 0;
    return 0;
}

```

**End**

## VIDEO 6 BAI 35 BTRL-TINH DAY SO

**Đề: Tính s(x.n):x+x^2/2!+x^3/3!...x^n/n!**

```
#include<iostream>
#include<math.h>
using namespace std;
//vd
int main(int argc, char** argv)
{
    int x,n;
    double s,m;
    m=1;
    s=0;
    cout<<"nhap x va n"<<endl;
    cin>>x>>n;
    for(int i=1;i<=n;i++)
    {
        m*=i;
        s+=pow(x,i)/m;
    }
    cout<<"tổng là "<<s<<endl;
    return 0;
}

```

**End**

## VIDEO 7 BAI 36 BTRL-TINH TONG CAC CHU SO TRONG 1 SO

*Đề: Chọn N là 1 số nguyên dương, tính tổng các chữ số trong N*

```
#include<iostream>
using namespace std;
//vd
int main(int argc, char** argv)
{
    int n;
    int temp;
    int s=0;
    cout<<"nhap so tu nhien n"<<endl;
    cin>>n;
    while(n>0)
    {
        temp=n%10;
        s+=temp;
        n=(int)n/10;
    }
    cout<<s<<endl;
    return 0;
}


```

**End**



## VIDEO 7 BAI 37 BTRL-SO HOAN THIEN

**Đề: kiểm tra xem n có phải số hoàn thiện không**

```
#include<iostream>
#include<math.h>
using namespace std;
//vd
int main(int argc, char** argv)
{
    int n;
    int temp=0;
    cout<<"nhap n"<<endl;
    cin>>n;
    for(int i=1;i<n;i++)
    {
        if(n%i==0)
        {
            temp+=i;
        }
    }
    if (n==temp)
        cout<<"la so hoan thien"<<endl;
    else
        cout<<"khong la so hoan thien"<<endl;
    return 0;
}

```

**End**

## VIDEO 9 BAI 38 BTRL-GAME ĐOÁN SỐ

**NOI DUNG**

**Đề: Viết chương trình thực hiện trò chơi đoán số như sau:

- Máy lấy ngẫu nhiên n thuộc [1,100] là số của máy: số máy (sử dụng hàm random)
- Nguời nhập vào một số(số nhập)
- Nếu số nhập lớn hơn số máy thì tb"so ban lon hon so may"
- Nhỏ hơn thì tb"so ban nho hon so may".
- Trò chơi kết thúc khi:
- Hoặc bạn đã đoán trúng: tb"haha ban tai that"
- Hoặc bạn đã đoán sa 7 lầni: tb"ban da thua roi"và hiển thị số máy
- Hỏi xem người chơi có tiếp tục không

```
cách code:
#include<iostream>
#include<time.h>
#include<stdlib.h>
#include<iomanip>
using namespace std;
//vd
int main(int argc, char** argv)
{
    while(true)
    {
        srand(time(NULL));
        int sm=1+rand()%100;
        int sn;
        int sld;
        sld=0;
        char c;
        bool iswin=false;
        cout<<"Tro choi doan so"<<endl;
    do
    {
        cout<<"chuong trinh da nhap so tu (1...100), moi ban doan"<<endl;
        sld++;
        cout<<"ban doan lan "<<sld<<endl;
        cin>>sn;
        if(sn==sm)
        {
            cout<<"ban nhap dung roi, so may = "<<sm<<endl;
            iswin=true;
            break;
        }
        if(sn>sm)
        {
            cout<<"ban nhap so lon hon so may"<<endl;
        }
        if(sn<sm)
        {
            cout<<"ban nhap so nho hon so may"<<endl;
        }
        if (sld==7)
            break;
    }while(true);
    if(iswin!=true)
    {
        cout<<"game over"<<endl;
        cout<<"so may la "<<sm<<endl;
    }
        cout<<"continue (c/k)"<<endl;
        cin>>c;
        if (c=='k')
            break;
    }
    cout<<"GOOD BYE"<<endl;
    return 0;
}
```

**Tự làm**

```
#include<iostream>
#include<time.h>
#include<stdlib.h>
#include<iomanip>
using namespace std;
//vd
int main(int argc, char** argv)
{
    while(true)
    {
        srand(time(NULL));
        int sm=1+rand()%100;
        int sn;
        char c;
        int w=1;
        int r=0;
        cout<<"chuong trinh choi game doan so"<<endl;
        do
        {
            cout<<"chuong trinh may da nhap tu (1...100), moi ban doan"<<endl;
            cout<<"ban doan lan "<<w<<endl;
            cin>>sn;
        if(sn==sm)
        {
            cout<<"ban doan dung roi, so may la "<<sm<<endl;
            r++;
            break;
        }
        if(sn>sm)
        {
            cout<<"ban nhap so lon hon so may"<<endl;
            w++;
        }
        if(sn<sm)
        {
            cout<<"ban nhap so be hon so may"<<endl;
            w++;
        }
        }while(w<=7);
        if(w>=7)
        {
            cout<<"game over, so may la "<<sm<<endl;
        }
            cout<<"continue ? (y/n)"<<endl;
            cin>>c;
            if(c='n')
                break;
    }
        cout<<"GOOD BYE"<<endl;
    
    return 0;
}
```

**End**



## VIDEO 10 BAI 39 BTRL-BAI TAP VE HINH

```
#include<iostream>
#include<time.h>
#include<stdlib.h>
#include<iomanip>
using namespace std;
//vd
int main(int argc, char** argv)
{
    int n;
    do
    {
        cout<<"nhap hang va cot ma tran vuong n"<<endl;
        cin>>n;
        if(n%2==0)
            cout<<"nhap lai"<<endl;
    }while(n%2==0);
    for (int i=0;i<n;i++)
    {
        for (int j=0;j<n;j++)
        {
            if(i==j)
                cout<<".";
            else if((j==0&&i<=n/2) ||(j==n-1&&i>=n/2)||(i==n/2))
            {
                cout<<".";
            }
            else
            {
                cout<<" ";
            }
        }
        cout<<endl;
    }
    
    return 0;
}


```

**End**

## VIDEO 11 BTTRL

**NOI DUNG**

*Đề:*

- Câu 1 kiểm tra n có phải số nguyên tố hay không ?

- Câu 2: Liệt kê các chữ số là số nguyên tố của số nguyên dương n

- Câu 3: Nhập x,n. Tính s(x,n)=x+x^3\3!+x^5\5!+x^(2*n+1)/(2**n+1)

- Câu 4: Nhập n, có n dấu căn lồng nhau
- Câu 5: xuất số đảo của số nguyên dương n

*Câu 1:*

\#include<iostream>

```
#include<iostream>
using namespace std;
//vd
int main(int argc, char** argv)
{
    while(true)
    {
        int dk=0;
        int n;
        char c;
    do
    {
        cout<<"nhap so tu nhien n"<<endl;
        cin>>n;
        if(n==1)
            cout<<"khong phai so nguyen to, moi nhap lai"<<endl;
        if(n==2)
            cout<<"la so nguyen to"<<endl;
    }while(n==1 ||n==2);
        for(int i=2;i<n;i++)
        {
            if (n%i==0)
            {
                dk++;
            }
        }
        if(dk==0)
            cout<<"la so nguyen to"<<endl;
        else
            cout<<"khong la so nguyen to"<<endl;
        cout<<"continue ? (y/n)"<<endl;
        cin>>c;
        if(c=='n')
            break;
        
    }
    
    return 0;
}


```

*câu 2*

```
#include<iostream>
using namespace std;
//vd
int main(int argc, char** argv)
{
    while(true)
    {
        int dk=0;
        int n;
        char c;
    do
    {
        cout<<"nhap so tu nhien n"<<endl;
        cin>>n;
        if(n==1)
            cout<<"khong phai so nguyen to, moi nhap lai"<<endl;
        if(n==2)
            cout<<"cac so nguyen to la 1,2"<<endl;
    }while(n==1 ||n==2);
        for(int i=1;i<=n;i++)
        {
            dk=0;
            for(int j=2;j<i;j++)
            {
                if(i%j==0)
                    dk++;
            }
            if(dk==0)
                cout<<i<<endl;
            else
                continue;
        }
        cout<<"continue ? (y/n)"<<endl;
        cin>>c;
        if(c=='n')
            break;
        
    }
    
    return 0;
}


```

*Câu 3*

```
#include<iostream>
#include<math.h>
using namespace std;
//vd
int main(int argc, char** argv)
{
    while(true)
    {
        char c;
        int x,n;
        int temp;
        int j=1;
        double s=0;
        int m=1;
        cout<<"nhap x va n"<<endl;
        cin>>x>>n;
        for(int i=0 ;i<=n;i++)
        {
            temp=(2*i+1);
            m=1;
            for(int j=1;j<=temp;j++)
            {
                m*=j;
            }
            s+=pow(x,(2*i+1))/m;
            cout<<m<<endl;
        }
        cout<<"tong la "<<s<<endl;
        cout<<"continue ? (y/n)"<<endl;
        cin>>c;
        if(c=='n')
            break;
        
    }
    
    return 0;
}


```

*Câu 4*

```
#include<iostream>
#include<math.h>
using namespace std;
//vd
int main(int argc, char** argv)
{
    while(true)
    {
        char c;
        int n;
        int a;
        double sum=0;
        cout<<"nhap n"<<endl;
        cin>>n;
        a=n;
        for (int i=1;i<=n;i++)
        {
            sum=sqrt(a+sum);
            a--;
        }
        cout<<"tong so co "<<n<<" long nhau la "<<sum<<endl;
        cout<<"continue ? (y/n)"<<endl;
        cin>>c;
        if(c=='n')
            break;
        
    }
    
    return 0;
}


```

*Câu 5*

```
#include<iostream>
#include<math.h>
using namespace std;
//vd
int main(int argc, char** argv)
{
    while(true)
    {
        char c;
        int n;
        int a;
        cout<<"nhap so n"<<endl;
        cin>>n;
        while(n>10)
        {
            a=(int)n%10;
            cout<<a;
            n=n/10;
        }
        cout<<n<<endl;
        cout<<"continue ? (y/n)"<<endl;
        cin>>c;
        if(c=='n')
            break;
        
    }
    
    return 0;
}


```

**End**

## VIDEO 12 BAI 41 KHAI NIEM VE MANG VA CACH KHAI BAO

*NOI DUNG*

- Khái niệm: Mảng là 1 tập hợp các biến có cùng kiểu dữ liệu nằm liên tiếp nhau trong bộ nhớ và được tham chiếu bởi 1 tên chung đó là mảng
- Mỗi phần tử của mảng được tham chiếu thông qua chỉ mục  [index]
- Nếu mảng có n phần tử thì phần tử đầu tiên có chỉ mục là 0 và phần tử cuối có chỉ mục là n-1
- Để tham chiếuđến 1 phần tử ta dùng tên mảng và chỉ mục của phần tử được đặt trong cặp dấu []

*KHAI BAO*

- Khai báo mảng 1 chiều:
- Cú pháp:

```
Type arrayName[elements];
```

- type: kiểu dữ liệu của mỗi phần tử mảng
- elements: số phần tử có trong mãng

- arrayName: tên Mảng
- Mỗi phần tử mảng là một biến thông thường

*KHAI BAO VA KHOI TAO BIEN 1 CHIEU*

- Cú pháp:

```
type arrayName[]={value1,value2,...,valuen};
```

*Lưu ý*

- Không khai báo kích thước mảng
- slpt trong mảng là số các gía trị được cung cấp trong cặp dấu { }, được phân cách nhau bởi dấu phẩy

**End**

