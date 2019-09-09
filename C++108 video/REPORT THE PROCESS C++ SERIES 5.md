# REPORT THE PROCESS C++ SERIES 5

## VIDEO 1 BAI 54 NGUYEN TAC HOAT DONG CUA HAM

```
#include<iostream>
using namespace std;
//de
int Tongso(int a,int b);
void xuat(int x);//ko khai bao bien luu tru
void output();//ham goi ham

int main(int argc,char** argv)
{
    int a,b;
    cout<<"nhap a va b"<<endl;
    cin>>a>>b;
    int kq=Tongso(a,b);
    cout<<kq<<endl;
    int kq2=Tongso(115,21);
    cout<<kq2<<endl;
    int kq3=Tongso(1,5);
    xuat(kq3);
    cout<<"ham goi ham"<<endl;
    output();
    return 0;
}

int Tongso(int a,int b)
{
    return a+b;
}

void xuat(int x)
{
    cout<<x<<endl;
    return;
}

void output()
{
    int kq4=Tongso(2,3);
    xuat(kq4);
}

```

- LIFO là nguyên tắc hoạt động của Hàm: Khi một hàm được gọi, chương trình sẽ lưu lại giá trị các biến local và chỉ thị lệnh tiếp theo. Khi kết thúc quá trình gọi hàm, chương trình sẽ trả về đúng chỉ thị lệnh kế tiếp đó cùng với giá trị  của các biến local

**End**

## VIDEO 2 BAI 55 THAM SO HINH THUC VA THAM SO THUC

**NOI DUNG**

- Khi hàm cần đối số( arguments ) để thực thi thì khi khai báo hàm cần khai báo danh sách các tham số nhận giá trị từ chương trình gọi. Các tham số này gọi là ***tham số hình thức***

*VD*

```
int min(int a,int b)
{
if(a<b)
return a;
else 
return b;
}
```



- Khi gọi hàm, ta cung cấp các giá trị thật, cac gí trị này sẽ được sao chép vào các tham số hình thức và các gí trị thật gọi lài tham số thực

*VD* 

```
min(5,6)
```

**VD**

```
#include<iostream>
using namespace std;
//de
int min(int a,int b);
int main()
{
    int a=5;
    int b=6;
    int x=min(a,b);
    cout<<x<<endl;
    return 0;
}

int min(int a,int b)
{
    return a<b?a:b;
}

```

**End**

## VIDEO 3 BAI 56 TRUYEN THAM TRI VA THAM BIEN

1. Truyền Tham Trị:

- Sau khi thoát khỏi hảm nó vẫn giữ giá trị gốc
- Sao chép giá trị của đối số vào tham số hình thức của hàm
- Những thay đổi của tham số không ảnh hưởng đến giá trị của đối số

2. Truyền Tham Biến:

- Sau khi thoát khỏi hàm nó sẽ lấy giá trị bị thay đổi của hàm
- Sao chép địa chỉ của đối số vào tham số hình thức. Do đó, những thay đổi đối với tham số sẽ có tác dụng trên đối số

*VD*

```
hamgido(&a)
{

}
```

- Địa chỉ của a truyền vào cho tham số hình thức của hàm: hamgido(int&b)

*VD*

```
#include<iostream>
using namespace std;
//de
void ham1(int x);
void ham2(int &x);
int main()
{
    int x=5;
    cout<<"x truoc khi vao ham 1 "<<x<<endl;
    ham1(x);
    cout<<"x sau khi vao ham 1 "<<x<<endl;
    
    x=9;
    cout<<"x truoc khi vao ham 2 "<<x<<endl;
    ham2(x);
    cout<<"x sau khi vao ham 2 "<<x<<endl;
    return 0;
}

void ham1(int x)
{
    x=10;
    cout<<"x trong ham 1 "<<x<<endl;
}
void ham2(int &x)
{
    x=10;
    cout<<"x trong ham 2 "<<x<<endl;
}

```

**End**

## VIDEO 4 BAI 57 PARAMETER MAC DINH

**NOI DUNG**

- Parameter mặc định được gọi là các đối số trong hàm được định trị trước, nếu trong quá trình gọi hàm mà không truyền thì nó lấy giá trị mặc định này

*VD*

```
#include<iostream>
using namespace std;
//de
void tong(int x,int y=1)
{
    cout<<(x+y)<<endl;
}

int main(int argc,char** argv)
{
    tong(9);
    tong(9,2);
    tong(10);
    return 0;
}

```

**End**

## VIDEO 5 BAI 58 GIOI THIEU VE HAM DE QUY

**NOI DUNG**

- Mội hàm được gọi là đệ qui nếu một lệnh trong thân hàm gọi đến chính hàm đó
- Đệ qui giúp giải quyết theo cách nghỉ thông thường một cách tự nhiên
- Đệ qui phải xác định được điểm dừng. Nếu không xác định chính xác thì làm bài toán bị sai và có thể bị lặp vĩnh cửu (Stack Overhead)

- Hoạt đông theo cơ chế stack

```
#include<iostream>
using namespace std;
//de
int giaithua(int n);
void h10toh2(int n);
int main(int argc,char** argv)
{
    //goi giai thua
    int gt=giaithua(5);
    cout<<"5!= "<<gt<<endl;
    h10toh2(11);
    return 0;
}

int giaithua(int n)
{
    if(n<=1)
        return 1;
    return n*giaithua(n-1);
}

//giai thua
void h10toh2(int n)
{
    if(n>0)
    {
        int t=n%2;
        h10toh2(n/2);
        cout<<t<<" ";
    }
}

```

**End**

## VIDEO 6 BAI 59 BTRL-PT BAC 2

*Đề: giải và biện luận phương trình bậc 2*

```
#include<iostream>
#include<math.h>
using namespace std;
//de
void bac2(int a,int b,int c);
int main(int argc,char** argv)
{
    while(true)
    {
    int a,b,c;
    char d;
    cout<<"tinh phuong trinh bac 2"<<endl;
    cout<<"ax^2+bx+c=0"<<endl;
    cout<<"nhap lan luot cac so a,b,c"<<endl;
    cin>>a>>b>>c;
    bac2(a,b,c);
        
    //tiep tuc khong
    cout<<"continue ? (y/n)"<<endl;
    cin>>c;
    if(d=='n')
        break;
    }
}

//phuong trinh bac 2
void bac2(int a,int b,int c)
{
    //phuong trinh bac 1
    if(a==0)
    {
        if(b==0&&c==0)
            cout<<"phuong trinh vo so nghiem"<<endl;
        else if(b==0&&c!=0)
            cout<<"phuong trinh vo nghiem"<<endl;
        else
        {
            double x=-c*1.0/b;
            cout<<"bai toan co 1 nghiem x= "<<x<<endl;
        }
            
    }
    else
    {
        //truong hop dac biet
        if(a+b+c==0)
        {
            double x1=1;
            double x2=c*1.0/a;
            cout<<"phuong trinh co 2 nghiem x1= "<<x1<<" x2= "<<x2<<endl;
        }
        else if(a-b+c==0)
        {
            double x1=-1;
            double x2=-c*1.0/a;
            cout<<"phuong trinh co 2 nghiem x1= "<<x1<<" x2= "<<x2<<endl;
        }
        
        //xu li thong thuong
        else
        {
            double delta=pow(b,2)-4*a*c;
            if(delta<0)
                cout<<"phuong trinh vo nghiem"<<endl;
            else if(delta==0)
            {
                double x1=-b*1.0/(2*a);
                cout<<"phuong trinh co nghiem kep x1=x2= "<<x1<<endl;
            }
            else
            {
                double x1=(-b+sqrt(delta))*1.0/(2*a);
                double x2=(-b-sqrt(delta))*1.0/(2*a);
                cout<<"phuong trinh co 2 nghiem x1= "<<x1<<" x2= "<<x2<<endl;
            }
        }
    }
    
}


```

```
#include<iostream>
#include<math.h>
using namespace std;
//de
void bac2(int a,int b,int c);
void xuat(double x1=0,double x2=0);
int main(int argc,char** argv)
{
    while(true)
    {
    int a,b,c;
    char d;
    cout<<"tinh phuong trinh bac 2"<<endl;
    cout<<"ax^2+bx+c=0"<<endl;
    cout<<"nhap lan luot cac so a,b,c"<<endl;
    cin>>a>>b>>c;
    bac2(a,b,c);
        
    //tiep tuc khong
    cout<<"continue ? (y/n)"<<endl;
    cin>>c;
    if(d=='n')
        break;
    }
}

//xuat
void xuat (double x1,double x2)
{
    if(x2==0&&x1!=0)
        cout<<"bai toan co 1 nghiem x= "<<x1<<endl;
    else if(x1!=0&&x2!=0)
        cout<<"phuong trinh co 2 nghiem x1= "<<x1<<" x2= "<<x2<<endl;
    else if(x1==0&&x2==0)
    {
        cout<<"phuong trinh vo nghiem hoac vo so nghiem"<<endl;
    }
    return;
    
}

//phuong trinh bac 2
void bac2(int a,int b,int c)
{
    //phuong trinh bac 1
    if(a==0)
    {
        if(b==0&&c==0)
            xuat();
        else if(b==0&&c!=0)
            xuat();
        else
        {
            double x1=-c*1.0/b;
            xuat(x1);
        }
            
    }
    else
    {
        //truong hop dac biet
        if(a+b+c==0)
        {
            double x1=1;
            double x2=c*1.0/a;
            xuat(x1,x2);
        }
        else if(a-b+c==0)
        {
            double x1=-1;
            double x2=-c*1.0/a;
            xuat(x1,x2);
        }
        
        //xu li thong thuong
        else
        {
            double delta=pow(b,2)-4*a*c;
            if(delta<0)
                xuat();
            else if(delta==0)
            {
                double x1=-b*1.0/(2*a);
                double x2=-b*1.0/(2*a);
                xuat(x1,x2);
                
            }
            else
            {
                double x1=(-b+sqrt(delta))*1.0/(2*a);
                double x2=(-b-sqrt(delta))*1.0/(2*a);
                xuat(x1,x2);
            }
        }
    }
    
}


```

**End**

## VIDEO 7 BAI 60 BTRL-XU LY MANG BANG HAM

*Đề*

- Dùng hàm để xử lý các yêu cầu về mảng:
- Nhập mảng
- Xuất mảng
- Tìm K trong mảng
- Sắp xếp mảng

```
#include<iostream>
#include<math.h>
using namespace std;
//de
void nhapmang(int a[],int n);
void xuatmang(int a[],int n);
int ftn(int a[],int n,int k);
void stl(int a[],int n);
int main(int argv, char** argc)
{
    while(true)
    {
        int n;
        int m;
        char c;
        cout<<"nhap so luong phan tu mang"<<endl;
        cin>>n;
        int a[n];
        nhapmang(a,n);
        cout<<"mang sau khi nhap la"<<endl;
        xuatmang(a,n);
        cout<<endl;
        cout<<"nhap so K can tim trong mang"<<endl;
        cin>>m;
        int kq=ftn(a,n,m);
        if (kq==-1)
            cout<<"khong ton tai "<<m<<" trong mang"<<endl;
        else
            cout<<"ton tai so "<<m<<" tai vi tri thu "<<kq<<endl;
            
        
        cout<<"mang sau sap xep tu be den lon"<<endl;
        stl(a,n);
        xuatmang(a,n);
        
        //tiep tuc ko
        cout<<endl;
        cout<<"continue ? (y/n)"<<endl;
        cin>>c;
        if(c=='n')
            break;
        
    }
    
}

//nhapmang
void nhapmang(int a[], int n)
{
    for(int i=0;i<n;i++)
    {
        cout<<"a["<<i<<"]=";
        cin>>a[i];
    }
}

//xuatmang
void xuatmang(int a[],int n)
{
    for (int i=0;i<n;i++)
    {
        cout<<a[i]<<" ";
    }
}

//tim k
/* c1
void ftn(int a[],int n,int k)
{
    int j=0;
    for(int i=0;i<n;i++)
    {
        if(a[i]==k)
        {
            cout<<"ton tai so "<<k<<" tai vi tri thu "<<i<<endl;
            j++;
            break;
        }
        else if(i==n-1&&j==0)
            cout<<"khong ton tai "<<k<<" trong mang"<<endl;
        
    }
}*/
int ftn(int a[],int n,int k)
{
    for(int i=0;i<n;i++)
    {
        if(a[i]==k)
            return i;
        
    }
    return -1;
}

//sap xep tu be den lon
void stl(int a[],int n)
{
    int temp;
    for(int i=0;i<n-1;i++)
    {
        for (int j=i+1;j<n;j++)
        {
            if(a[i]>a[j])
            {
                temp=a[i];
                a[i]=a[j];
                a[j]=temp;
            }
        }
    }
}

```

## VIDEO 8 BAI 61 BTRL-XU LY DAY FIBONACCI

*NOI DUNG*



- Dùng hàm xử lý các yêu cầu về Fibonacci

  1. Tìm số fib tại vị trí N bất kì
  2. Xuất dãy fib từ 1 đến N;

  ```
  #include<iostream>
  using namespace std;
  //de
  int fib(int n);
  void xuat(int n);
  int main(int argv, char** argc)
  {
      while(true)
      {
          int n;
          char c;
          cout<<"dien vi tri de tim so fabonacci"<<endl;
          cin>>n;
          int m=fib(n);
          cout<<m<<endl;
          cout<<"chi tiet day la"<<endl;
          xuat(n);
          
          //tiep tuc ko
          cout<<"continue ?(y/n)"<<endl;
          cin>>c;
          if(c=='n')
              break;
      }
  }
  
  //ham fibonacci
  int fib(int n)
  {
      if(n<=2)
          return 1;
      return fib(n-1)+fib(n-2);
  }
  
  //xuat mang
  void xuat(int n)
  {
      for(int i=1;i<=n;i++)
      {
          cout<<fib(i)<<"\t";
      }
  }
  
  ```

  **End**

  

  ## VIDEO 9 BAI 62 BTRL-CHU VI DIEN TICH TAM GIAC

  *NOI DUNG*

  *Đề: Viết hàm để tính chu vi diện tích tam giác*

  ```
  #include<iostream>
  #include<math.h>
  using namespace std;
  //de
  int cv(int a,int b,int c);
  double dt(int a,int b,int c);
  bool check(int a,int b,int c);
  int main(int argv, char** argc)
  {
      while(true)
      {
          char c;
          int m,n,i;
          cout<<"chuong trinh tinh chu vi dien tich hinh tam giac"<<endl;
          cout<<"nhap lan luot 3 canh cua tam giac"<<endl;
          cin>>m>>n>>i;
          if(check(m,n,i)==false)
          {
              cout<<"khong tao thanh 1 tam giac"<<endl;
              
          }
          else
          {
          int p=cv(m,n,i);
          int s=dt(m,n,i);
          cout<<"chu vi tam giac la"<<endl;
          cout<<p<<endl;
          cout<<"dien tich tam giac la"<<endl;
          cout<<s<<endl;
          }
          
          //tiep tuc ko
          cout<<"continue ?(y/n)"<<endl;
          cin>>c;
          if(c=='n')
              break;
      }
  }
  
  // tinh chu vi tam giac
  int cv(int a,int b,int c)
  {
      return a+b+c;
  }
  
  //tinh dien tich
  double dt(int a,int b,int c)
  {
      double p=cv(a,b,c)/2;
      double dt=sqrt(p*(p-a)*(p-b)*(p-c));
      return dt;
  }
  
  //kiem tra co phai la mot tam giac hay khong
  bool check(int a,int b,int c)
  {
      if(a<=0||b<=0||c<=0||(a+b)<=c||(a+c)<=b||(b+c)<=a)
      {
          return false;
      }
      return true;
  }
  
  ```

  **End**

  ## VIDEO 10 BAI 63 BTRL-HAM CHOI GAME DOAN SO

  **NOI DUNG**

  *Đề:*

  - Máy ra 1 số trong đoạn [1...100]
  - Người chơi đoán số, chỉ được phép sai 7 lần. Mỗi lần đoán sẽ thông báo sẽ thông báo số người chơi nhỏ hơn hay lớn hơn số của máy và hiển thị số lần đoán
  - Game kết thúc khi: Đoán sai trước 7 lần hoặc đoán trúng trước 7 lần
  - Sau khi game kết thúc hỏi người chơi có tiếp tục không ?!

  ```
  #include<iostream>
  #include<time.h>
  #include<stdlib.h>
  using namespace std;
  //de
  void play(int n,int i);
  void loopPlay(int n,int i);
  int main(int argv, char** argc)
  {
      srand(time(NULL));
      int n;
      int i=0;
      cout<<"chao mung den voi tro choi doan so"<<endl;
      play(n,i);
      loopPlay(n,i);
      return 0;
      
          
      
  }
  
  //choi
  void play(int n,int i)
  {
      int m=rand()%100;
      cout<<"may da random tu 1..100, so ban doan la"<<endl;
      do
      {
          i++;
          cout<<"ban doan lan "<<i<<endl;
          cin>>n;
          if(n==m)
          {
              cout<<"ban da WIN !!, so may = "<<m<<endl;
              break;
          }
          else if(n<m)
          {
              cout<<"ban doan so nho hon so may"<<endl;
          }
          else if(n>m)
          {
              cout<<"ban doan so lon hon so may"<<endl;
          }
          if(i==7)
          {
              cout<<"GAME OVER"<<endl;
              cout<<"so may = "<<m<<endl;
              break;
          }
          
          
      }while(true);
  }
  
  //choi tiep khong
  void loopPlay(int n,int i)
  {
      char c;
      while(true)
      {
          cout<<"continue ? (y/n)"<<endl;
          cin>>c;
          if(c=='n')
          {
              break;
          }
          play(n,i);
      }
      cout<<"cam on ban da choi"<<endl;
  }
  
  ```

  **End**

  ## VIDEO 11 BAI 64 BTTRL

  *Đề:*

  1. Suy nghĩ viết hàm để có thể tái sử dụng cách tính mẫu số cho 2 th dưới đây

  - Nhập n. Tính S(n)=1+1/(1+2)+...1/(1+2+...n)
  - Nhập x,n. Tính S(x,n)=x+x^2/(1+2)...+x^n/(1+2+..n)

  2. Một số chia hết cho 3 khi tổng các chữ số của nó chia hết cho 3, hãy viết hàm tính tổng các chữ số của 1 số để áp dụng kiểm tra số chia hết cho 3

  `Viết hàm tính tổng ước số để áp dụng cho 2 bài dưới đây`

  3. Kiểm tra n nguyên dương có phải là số hoàn thiện hay không ?
  4. Kiểm tra n có phải là số thịnh vượng hay. không ?

  

  *Câu 1*

  ```
  #include<iostream>
  #include<math.h>
  using namespace std;
  //de
  int tms(int n);
  double s1(int n);
  double s2(int x,int n);
  
  int main(int argc, char** argv)
  {
      while(true)
      {
          int x,n;
          char c;
          cout<<"Tinh S(n) 1/(1+2+...n)"<<endl;
          cout<<"nhap n"<<endl;
          cin>>n;
          cout<<"S(n)=1/(1+2+...n) = "<<s1(n)<<endl;
          cout<<"Tính S(x,n)=x+x^2/(1+2)...+x^n/(1+2+..n)"<<endl;
          cout<<"nhap x"<<endl;
          cin>>x;
          cout<<"S(x,n)=x+x^2/(1+2)...+x^n/(1+2+..n)= "<<s2(x,n)<<endl;
          
      //tiep tuc khong
          cout<<"continue ? (y/n)"<<endl;
          cin>>c;
          if(c=='n')
          {
              break;
          }
      }
  }
  
  //tong mau so
  int tms(int n)
  {
      if(n<=1)
          return 1;
      return n+tms(n-1);
  }
  
  //S(n)=1+1/(1+2)+...1/(1+2+...n)
  double s1(int n)
  {
      double s=0;
      for(int i=1;i<=n;i++)
      {
          s+=1.0/tms(i);
      }
      return s;
  }
  
  //S(x,n)=x+x^2/(1+2)...+x^n/(1+2+..n)
  double s2(int x,int n)
  {
      double s=0;
      for(int i=1;i<=n;i++)
      {
          s+=pow(x,i)*1.0/tms(i);
      }
      return s;
  }
  
  ```

*Câu 2*

```
#include<iostream>
#include<math.h>
using namespace std;
//de
bool c3(int n);
int main(int argv, char** argc)
{
    int n;
    do
    {
        cout<<"nhap 1 so tu nhien n"<<endl;
        cin>>n;
        if(n<=0)
            cout<<"nhap lai"<<endl;
    }while(n<=0);
    if(c3(n)==true)
        cout<<n<<" chia het cho 3"<<endl;
    else
        cout<<n<<" khong chia het cho 3"<<endl;
    return 0;
}

//kiem tra co chia het cho 3 hay khong
bool c3(int n)
{
    int s=0;
    while(true)
    {
        int temp=n%10;
        n=n*1.0/10;
        s+=temp;
        if(n<=0&&s%3==0)
        {
            return true;
            break;
        }
        else if(n<=0&&s%3!=0)
        {
            return false;
            break;
        }
        
    }
}

```

*Câu 3,4*

```
#include<iostream>
#include<math.h>
using namespace std;
//de
void us(int n);
int tus(int n);
bool pn(int n);
bool an(int n);
int main(int argv, char** argc)
{
    int n;
    do
    {
        cout<<"nhap 1 so tu nhien n"<<endl;
        cin>>n;
        if(n<=0)
            cout<<"nhap lai"<<endl;
    }while(n<=0);
    us(n);
    //check so hoan hao
    if(pn(n)==true)
        cout<<"la so hoan thien"<<endl;
    else
        cout<<"khong phai so hoan thien"<<endl;
    //check so thinh vuon
    if(an(n)==true)
        cout<<"la so thinh vuong"<<endl;
    else
        cout<<"khong phai so thinh vuong"<<endl;
    return 0;
    
}

//uoc so
void us(int n)
{
    cout<<"uoc so cua "<<n<<" la"<<endl;
    for(int i=1;i<=n;i++)
    {
        if(n%i==0)
        {
            cout<<i<<"\t";
        }
    }
    cout<<endl;
    
}

//tong uoc so
int tus(int n)
{
    int s=0;
    for(int i=1;i<n;i++)
    {
        if(n%i==0)
        {
            s+=i;
        }
    }
    return s;

}

//check so hoan thien
bool pn(int n)
{
    if(tus(n)==n)
        return true;
    return false;
}

//check so thinh vuong
bool an(int n)
{
    if(tus(n)>n)
        return true;
    return false;
}

```

**End**

## VIDEO 12 BAI 64 KHAI NIEM CON TRO VA BIEN CON TRO

**NOI DUNG**

1. Khái niệm con trỏ: Một con trỏ là một biến chứa một địa chỉ bộ nhớ, địa chỉ này là vị trí của một đối tượng khác (Thường là 1 biến ) trong bộ nhớ. Nếu một biến chứa địa chỉ của một biến khác, biến thứ nhất được gọi là trỏ đến biến thứ hai
2. Biến con trỏ

- Nếu một biến sẽ chứa địa chỉ của một biến khác thì nó phải được khai báo là một con trỏ. Khai báo một biến gồm kiểu dữ liệu cơ sở, một dấu * và tên biến. Dạng tổng quát để khai báo 1 biến con trỏ là: 

`type*pointerVariable`

*type: xác định kiểu dữ liệu của biến mà con trỏ có thể trỏ đến.VD có trỏ có kiểu int sẽ trỏ đến biến có kiểu int. Do các phép toàn số học trên con trỏ (  tăng,giảm ) liên quan đến type của nó nên cần phải khai báo type của con trỏ đúng đắng

- Khai báo:

`DataType*PointerVariable;`

- Cấp phát:

`PointerVariable=new DataType;`

- Huỷ bộ nhớ

`delete PointerVariable;`

*VD*

```
#include<iostream>
using namespace std;
//de
int main(int argv,char** argc)
{
    int *p;
    p=new int;
    *p=100;//gam gia tri bang 100 tai o nho ma con tro p dang tro den
    cout<<"dia chi tai con tro p = "<<p<<endl;
    cout<<"gia tri tai dia chi p ma con tro tro toi bang "<<*p<<endl;
    delete p;//bi loi memory leak neu ko thu hoi bo nho
    return 0;
}

```

**End**

