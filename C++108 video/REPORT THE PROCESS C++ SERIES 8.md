# REPORT THE PROCESS C++ SERIES 8

## VIDEO 1 BAI 89 BTRL-CHUOI 5

*Đề: Viết chương trình nhập vào họ và tên của một người, cắt bỏ các khoảng trống không cần thiết(nếu có), tách tên ra khỏi họ và tên, in tên lên màn hình. Chú ý đến trường hợp cả họ và tên chỉ có 1 từ*

```
#include<iostream>
#include<string.h>
//de chuoi 5
using namespace std;
void xoakhoangtrang(char *str);
void ftr(char *&str,char *&strcuoi,char *&strtruoc);
int main(int argv,char** argc)
{
    char *str=new char[200];
    char *strcuoi=new char[100];
    char *strtruoc=new char[100];
    cout<<"nhap ten"<<endl;
    cin.getline(str,200);
    cout<<"chuoi ban dau "<<str<<endl;
    cout<<"chieu dai chuoi "<<strlen(str)<<endl;
    xoakhoangtrang(str);
    puts(str);
    //xuat ten
    ftr(str,strcuoi,strtruoc);
    cout<<"Ten"<<endl;
    cout<<strcuoi<<endl;
    return 0;
}

//xoa khoang trang
void xoakhoangtrang(char *str)
{
    int j=0;
    long n=strlen(str);
    for(int i=0;i<n;i++)
    {
        if(str[i]!=' ')
            str[j++]=str[i];
        else if (j>0 && str[i+1]!=' ')
            str[j++]=str[i];
    }
    if(str[j-1]==' ')
        str[j-1]='\0';
    else
        str[j]='\0';
}

//tach ten tu ho va ten
void ftr(char *&str,char *&strcuoi,char *&strtruoc)
{
    int j=0;
    long n=strlen(str);
    for(int i=n-1;i>=0;i--)
    {
        if(str[i]==' ')
        {
            j=i+1;
            break;
        }
    }
    int i2=0;
    for(int i=j;i<n;i++)
    {
        strcuoi[i2]=str[i];
        i2++;
    }
}

```

**End**

## VIDEO 2 BAI 90 BTTRL 

*Đề: 1. Viết chương trình nhập vào 1 chuỗi ký tự và kiểm tra xem chuỗi đó có đối xứng hay không.*

2. Viết chương trình nhập vào họ và tên của một nguời, cắt bỏ các khoảng trắng bên phải, bên trái và các khoảng trắng không có nghĩa ở trong. In ra màn hình toàn bộ họ tên người đó dưới dạng chữ hoa, chữ thường
3. Viết chương trình nhập vào một danh sách họ và tên của n người theo kiểu chữ thường, đổi các chữ cái đầu của họ, tên và chữ lót của mỗi người thành chữ in hoa. In kết quả lên màn hình
4. Viết chương trình nhập vào một danh sách họ và tên của n người, tách tên từng người ra khỏi họ và tên rồi sắp xếp danh sách trên theo thứ tự từ điển

1.

```
#include<iostream>
#include<string.h>
//de 1
using namespace std;
bool check(char *&str,int n);
int main(int argv, char** argc)
{
    char *str=new char[200];
    cout<<"nhap chuoi so khong khoang cach"<<endl;
    cin.getline(str,200);
    int n=strlen(str);
    if(check(str,n)==0)
    {
        cout<<"doi xung"<<endl;
    }
    else
    {
        cout<<"khong doi xung"<<endl;
    }
    
    return 0;
}

//ham kiem tra doi xung
bool check(char *&str, int n)
{
    int j=n-1;
    int i2=0;
    for(int i=0;i<(n-1)/2;i++)
    {
        if(str[i]!=str[j])
        {
            i2=1;
            break;
        }
        j--;
    }
    if(i2==1)
        return 1;
    return 0;
}

```

2. 

```
#include<iostream>
#include<string.h>
//de 2
using namespace std;
void xkt(char *&str);
void hoa(char *&str);
void thuong(char *&str);
int main (int argv, char** argc)
{
    char *str=new char[200];
    cout<<"nhap ho va ten"<<endl;
    cin.getline(str,200);
    int m=strlen(str);
    cout<<m<<endl;
    xkt(str);
    puts(str);
    m=strlen(str);
    cout<<m<<endl;
    hoa(str);
    thuong(str);
    return 0;
}

//xoa khoang trang
void xkt(char *&str)
{
    int j=0;
    long n=strlen(str);
    for(int i=0;i<n;i++)
    {
        if(str[i]!=' ')
        {
            str[j++]=str[i];
            
        }
        else if(j>0 && str[i+1]!=' ')
        {
            str[j++]=str[i];
            
        }
        
    }
    if(str[j-1]==' ')
        str[j-1]='\0';
    else
        str[j]='\0';
}

//inhoa
void hoa(char *&str)
{
    int n=strlen(str);
    for (int i=0;i<n;i++)
    {
        putchar(toupper(str[i]));
    }
    cout<<endl;
}
void thuong(char *&str)
{
    int n=strlen(str);
    for (int i=0;i<n;i++)
    {
        putchar(tolower(str[i]));
    }
    cout<<endl;
}
```

3.

```
#include<iostream>
#include<string.h>
//de 3
using namespace std;
void input(char **&dssv,int n);
void output(char **dssv,int n);
void outputn(char *&dssv,int n);
void hoa(char *&dssv,int n);
int main(int argv, char** argc)
{
     int n;
     cout<<"Nhap vao so luong sinh vien"<<endl;
     cin>>n;
     char **dssv=new char*[n];
     for(int i=0;i<n;i++)
     {
          *(dssv+i)=new char[100];
     }
     cout<<"DANH SACH SINH VIEN"<<endl;
     input(dssv,n);
     
     //cout<<"danh sach sinh vien sau khi nhap la"<<endl;
     //output(dssv,n);
     cout<<"Danh sach sv sau khi nhap la :"<<endl;
     cout<<"DANH SACH SINH VIEN"<<endl;
     for(int i=0;i<n;i++)
     {
          outputn(*(dssv+i),n);
     }
     cout<<endl;
     cout<<"sau khi chinh: "<<endl;
     cout<<"DANH SACH SINH VIEN"<<endl;
     for(int i=0;i<n;i++)
     {
          hoa(*(dssv+i),n);
     }
     return 0;
}

//nhap dssv
void input(char **&dssv,int n)
{
     int j=0;
     for(int i=0;i<n;i++)
     {
          j++;
          //if(i==0)
               //cin.getline(dssv[0],100);
          cout<<"sv "<<j<<":";
          cin.ignore();
          cin.getline(dssv[i],100);
     }
}

//xuat danh sach
void output(char **dssv,int n)
{
     for(int i=0;i<n;i++)
     {
          puts(dssv[i]);
     }
}

//lay chu thuong
void outputn(char *&dssv,int n)
{
     int m=strlen(dssv);
     for(int i=0;i<m;i++)
     {
          char c=dssv[i];
          putchar(tolower(c));
     }
     cout<<endl;
}

//lay chu cai dau
void hoa(char *&dssv,int n)
{
     int m=strlen(dssv);
     for(int i=0;i<m;i++)
     {
          if(i==0)
               putchar(toupper(dssv[i]));
          else if(i!=0 && dssv[i-1]==' ')
          {
               int j=i;
               putchar(toupper(dssv[j]));
          }
          else
          {
               putchar(tolower(dssv[i]));
          }
          
     }
     cout<<endl;
}

```

4. 

```
#include<iostream>
#include<string.h>
//de 3
using namespace std;
void input(char **&dssv,int n);
void output(char **dssv,int n);
void outputn(char *&dssv,int n);
void hoa(char *&dssv,int n);
void ftr(char *&dssv, char *&strcuoi, int n);
int main(int argv, char** argc)
{
     int n;
     cout<<"Nhap vao so luong sinh vien"<<endl;
     cin>>n;
     char **dssv=new char*[n];
     for(int i=0;i<n;i++)
     {
          *(dssv+i)=new char[100];
     }
     char *strcuoi=new char[100];
     cout<<"DANH SACH SINH VIEN"<<endl;
     input(dssv,n);
     
     //cout<<"danh sach sinh vien sau khi nhap la"<<endl;
     //output(dssv,n);
     cout<<"Danh sach sv sau khi nhap la :"<<endl;
     cout<<endl;
     cout<<"DANH SACH SINH VIEN"<<endl;
     for(int i=0;i<n;i++)
     {
          outputn(*(dssv+i),n);
     }
     cout<<endl;
     cout<<"sau khi chinh: "<<endl;
     cout<<"DANH SACH SINH VIEN"<<endl;
     for(int i=0;i<n;i++)
     {
          hoa(*(dssv+i),n);
     }
     cout<<endl;
     for(int i=0;i<n;i++)
     {
          ftr(*(dssv+i),strcuoi,n);
          puts(strcuoi);
          
     }
     return 0;
}

//nhap dssv
void input(char **&dssv,int n)
{
     int j=0;
     for(int i=0;i<n;i++)
     {
          j++;
          if(i==0)
               cin.getline(dssv[0],100);
          cout<<"sv "<<j<<":";
          cin.getline(dssv[i],100);
     }
}

//xuat danh sach
void output(char **dssv,int n)
{
     for(int i=0;i<n;i++)
     {
          puts(dssv[i]);
     }
}

//lay chu thuong
void outputn(char *&dssv,int n)
{
     int m=strlen(dssv);
     for(int i=0;i<m;i++)
     {
          char c=dssv[i];
          putchar(tolower(c));
     }
     cout<<endl;
}

//lay chu cai dau
void hoa(char *&dssv,int n)
{
     int m=strlen(dssv);
     for(int i=0;i<m;i++)
     {
          if(i==0)
               putchar(toupper(dssv[i]));
          else if(i!=0 && dssv[i-1]==' ')
          {
               int j=i;
               putchar(toupper(dssv[j]));
          }
          else
          {
               putchar(tolower(dssv[i]));
          }
          
     }
     cout<<endl;
}

//tach ten ra khoi ho ten
void ftr(char *&dssv, char *&strcuoi, int n)
{
     int j=0;
     //cout<<strlen(dssv)-1<<endl;
     for(int i=strlen(dssv)-1;i>=0;i--)
     {
          if(dssv[i]==' ')
          {
               j=i+1;
               break;
          }
     }
     int i2=0;
     for(int i=j;i<strlen(dssv);i++)
     {
          strcuoi[i2]=dssv[i];
          i2++;
     }
     strcuoi[strlen(dssv)]='\0';
}

```

**End**

## VIDEO 3 BAI 91 KHAI NIEM VA CACH KHAI BAO CAU TRUC

**NOI DUNG**

1. Khái niệm: Một cấu trúc là tập các biến được tham chiếu thông qua một tên chung. Một khai báo cấu trúc hình thành một khuôn mẫu (template) mà có thể dùng để taọ nên các biến cấu trúc có cùng kiểu. Những biến mà tạo nên cấu trúc được gọi là thanh viên(members)

**NÓI NGẮN GỌN**: Nó là 1 kiểu dữ liệu phức hợp do ta tạo ra

2. Dạng tổng quát của một khai báo cấu trúc

```
struct structer name
{
type member_1;
type member_2;
...
type member_n;
...
}Var name;
```

- *struct* : từ khoá tạo cấu trúc trong c++
- *structureName:* tên của cấu trúc
- *type*:  kiểu dữ liệu của thành viên tương ứng
- *member_n*..... : Tên các biến thành viên của cấu trúc
- *varNames:* Tên các biến cấu trúc phân cách nhau bằng dấu phẩy

**VD:**

```
struct addr
{
char name[30];
char street[40];
char city[20];
char state[3];
unsigned  long int zip;
}
```

```
#include<iostream>
using namespace std;
//de
struct diachi
{
     char sonha[25];
     char tenduong[100];
     char quan[100];
     char tinhthanh[100];
};
struct sinhvien
{
     char mssv[50];
     char tensv[200];
     bool gioitinh;
     diachi diachinha;
     diachi diachitruong;
}ty,teo;

int main(int argv, char** argc)
{
     
}

```

**End**

## VIDEO 4 BAI 92 TRUY CAP CAC THANH VIEN CUA BIEN CAU TRUC

**NOI DUNG**

- Toán tử dấu chấm (dot operator) dùng để truy cập(access) các thành viên của một biến cấu trúc. Dạng tổng quát để truy cập 1 thành viên của một biến cấu trúc là: 

`structureName.memberName`

**VD:**

```
#include<iostream>
#include<string.h>
using namespace std;
//de
struct diachi
{
     char sonha[25];
     char tenduong[100];
     char quan[100];
     char tinhthanh[100];
};
struct sinhvien
{
     char mssv[50];
     char tensv[200];
     bool gioitinh;
     diachi diachinha;
     diachi diachitruong;
}ty,teo;

int main(int argv, char** argc)
{
     strcpy(teo.tensv,"nguyen van teo");
     teo.gioitinh=false;
     strcpy(teo.mssv,"at15");
     cout<<"----------------------------"<<endl;
     cout<<"ten: "<<teo.tensv<<endl;
     cout<<"ma so: "<<teo.mssv<<endl;
     cout<<"gioi tinh: "<<(teo.gioitinh==true?"nu":"nam")<<endl;
     cout<<"----------------------------"<<endl;
     
     sinhvien bin;
     strcpy(bin.tensv,"pham nguyen");
     cout<<bin.tensv<<endl;
     return 0;
}

```

**End**

## VIDEO 5 BAI 93 LENH GAN CAU TRUC

**NOI DUNG**

- Noi dung trong 1 biến cấu trúc có thể gán cho một biến cấu trúc khác có cùng kiểu dùng một câu lệnh gán. Ví dụ để gán nội dung bct pointA cho biến pointB, ta thực hiện lệnh sau:

`pointB=pointA`

- Sau câu lệnh này, biến pointB có cùng nội dung như biến pointA. Tuy nhiên, ta có thể sao chép từng thành viên như sau:

```
pointB.x=pointA.x
pointB.y=pointA.y
```

**VD:**

```
#include<iostream>
#include<string.h>
using namespace std;
//de
struct book
{
     char title[30];
     char author[20];
     int pages;
     float price;
};
int main(int argv, char** argc)
{
     book b;
     cout<<"input book information"<<endl;
     cout<<"title: ";
     cin.getline(b.title,30);
     cout<<"author: ";
     cin.getline(b.author,20);
     cout<<"Number og pages: ";
     cin>>b.pages;
     cout<<"price: ";
     cin>>b.price;
     book a=b;
     cout<<"information of this book is:"<<endl;
     cout<<"title: "<<a.title<<endl;
     cout<<"author: "<<a.author<<endl;
     cout<<"Number og pages: "<<a.pages<<endl;
     cout<<"price: "<<a.price<<endl;
     
     
}

```

**End**

## VIDEO 6 BAI 94 MANG CAU TRUC

**NOI DUNG**

- Ta khai báo cấu trúc, sau đó khai báo 1 mảng của cấu trúc đó
- Công thức tổng quát:

`structerName arrayName[number of elements];`

**VD:**

```
#include<iostream>
#include<string.h>
using namespace std;
//de
struct sinhvien
{
     char ten[100];
     char ma[20];
};

void input(sinhvien dssv[], int n);
void output(sinhvien dssv[], int n);
int main(int argv, char** argc)
{
     int n;
     cout<<"nhap so luong sinh vien"<<endl;
     cin>>n;
     sinhvien dssv[n];
     input(dssv,n);
     cout<<"-------------------------"<<endl;
     cout<<"DANH SACH SINH VIEN"<<endl;
     cout<<"ma\tten"<<endl;
     output(dssv,n);
     cout<<"-------------------------"<<endl;
     return 0;
}

//nhap danh sach
void input(sinhvien dssv[], int n)
{
     int j=1;
     for(int i=0;i<n;i++)
     {
          cout<<"nhap sinh vien thu "<<j++<<endl;
          cout<<"nhap ma: ";
          cin>>dssv[i].ma;
          cout<<"nhap ten: ";
          cin.ignore();
          cin.getline(dssv[i].ten,100);
     }
}

//xuat danh sach
void output(sinhvien dssv[], int n)
{
     for(int i=0;i<n;i++)
     {
          cout<<dssv[i].ma<<"\t"<<dssv[i].ten<<endl;
     }
}

```

**End**

## VIDEO 7 BAI 95 CON TRO CAU TRUC

**NOI DUNG**

- C/C++ cho phép dùng con trỏ với các cấu trúc như vấy bất kì kiểu dữ liệu nào của biến
- Cú pháp khai báo con trỏ cấu trúc giống như các loại con trỏ khác.
- Dạng tổng quát

`structureName*structurePointers;`

- Và cũng phải cấp phát bộ nhớ để sử dụng(new ), cũng dùng -> để truy xuất

```
#include<iostream>
#include<string.h>
using namespace std;
//de
struct sinhvien
{
     char ten[100];
     int ma;
};

int main(int argv, char** argc)
{
     sinhvien teo;
     teo.ma=113;
     strcpy(teo.ten,"teo");
     cout<<"thong tin cua teo:"<<endl;
     cout<<teo.ma<<"\t"<<teo.ten<<endl;
     
     sinhvien *pteo=&teo;
     cout<<"thong tin theo con tro"<<endl;
     cout<<pteo->ma<<"\t"<<pteo->ten<<endl;
     pteo->ma=115;
     strcpy(pteo->ten,"teo2");
     cout<<"thong tin cua teo sau khi thay doi "<<endl;
     cout<<pteo->ma<<"\t"<<pteo->ten<<endl;
     
     teo.ma=204;
     strcpy(teo.ten,"teo 2019");
     cout<<"thong tin theo con tro"<<endl;
     cout<<pteo->ma<<"\t"<<pteo->ten<<endl;
     
     sinhvien *pty;
     pty=new sinhvien;
     pty->ma=114;
     strcpy(pty->ten,"ty");
     cout<<"thong tin cua ty"<<endl;
     cout<<pty->ma<<"\t"<<pty->ten<<endl;
     
     //con tro tro den 1 con tro
     sinhvien *pty2=pty;
     pty2->ma=214;
     cout<<"thong tin cua pty sau khi pty2 thay doi"<<endl;
     cout<<pty->ma<<"\t"<<pty->ten<<endl;
}

```

**End**

## VIDEO 8 BAI 96 BTRL-CAU TRUC NHAN VIEN

*Đề: cho cấu trúc nhân viên: Mã(int),tên(chuỗi),tuổi (int), địa chỉ cơ qua, địa chỉ nhà riêng. Địa chỉ : tên đường, quận, tỉnh thành*

- *hãy tạo 2 cấu trúc như yêu cầu*
- *giả lập 2 nhân viên có đầy đủ thông tin như mô tả, xuất thông tin ra màn hình*

*VD:*

```
#include<iostream>
#include<string.h>
using namespace std;
//de
struct diachi
{
     char duong[200];
     char quan[100];
     char tt[100];
};

struct nhanvien
{
     int ma;
     char ten[200];
     int tuoi;
     diachi cq;
     diachi nr;
};

int main(int argv, char** argc)
{
     //teo
     nhanvien teo;
     teo.ma=1;
     teo.tuoi=13;
     strcpy(teo.ten,"huynh van teo");
     strcpy(teo.cq.duong,"au co");
     strcpy(teo.cq.quan,"quan 11");
     strcpy(teo.cq.tt,"tp HCM");
     strcpy(teo.nr.duong,"lac long quan");
     strcpy(teo.nr.quan,"quan 11");
     strcpy(teo.nr.tt,"tp HCM");
     
     //xuat thong tin
     cout<<"thong tin cua Teo"<<endl;
     cout<<"Ma= "<<teo.ma<<endl;
     cout<<"Ten day du: "<<teo.ten<<endl;
     cout<<"tuoi: "<<teo.tuoi<<endl;
     cout<<"Dia chi co quan: "<<teo.cq.duong<<","<<teo.cq.quan<<","<<teo.cq.tt<<endl;
     cout<<"Dia chi nha rieng: "<<teo.nr.duong<<","<<teo.nr.quan<<","<<teo.nr.tt<<endl;
     cout<<"-----------------------"<<endl;
     //ty
     nhanvien *ty=new nhanvien;
     ty=&teo;
     strcpy(ty->ten,"ty lun");
     ty->ma=2;
     ty->tuoi=14;
     strcpy(ty->nr.tt,"Ha Noi");
     cout<<ty->ten<<"->"<<ty->nr.tt<<endl;
      return 0;
}

```

**End**

## VIDEO 9 BAI 97 BTRL-CAU TRUC DIEM

*Đề: cho cấu trúc điểm: toạ độ x, toạ độ y. Sau đó viết các hàm:*

- *tính khoảng cách giữ 2 điểm*
- *nhập vào xuất danh sách các điểm*
- *tính tổng độ dài*

```
#include<iostream>
#include<string.h>
#include<math.h>
using namespace std;
//de
struct toado
{
     int x;
     int y;
     
};
double khoangcach(toado a, toado b);
double dodaicacdiem(toado arrdiem[],int n);
void nhaptd(toado arrdiem[],int n);
void xuattd(toado arrdiem[],int n);
int main(int argv, char** argc)
{
     toado a;
     cin>>a.x>>a.y;
     toado b;
     cin>>b.x>>b.y;
     int kq=khoangcach(a,b);
     cout<<"khoang cach tu A("<<a.x<<","<<a.y<<")->B("<<b.x<<","<<b.y<<")"<<endl;
     cout<<"khoang cach giu 2 diem la: "<<kq<<endl;
     toado arrdiem[3];
     nhaptd(arrdiem,3);
     cout<<"danh sach cac diem ban vua nhap la:"<<endl;
     xuattd(arrdiem,3);
     cout<<"tong do dai khoang cach la "<<dodaicacdiem(arrdiem,3)<<endl;
     return 0;
}

//khoang cach giu 2 diem
double khoangcach(toado a, toado b)
{
     return sqrt(pow(a.x-b.x,2)+pow(a.y-b.y,2));
}

//do dai cac diem
double dodaicacdiem(toado arrdiem[],int n)
{
     double tongkc=0;
     for(int i=0;i<n-1;i++)
     {
          double kc=khoangcach(arrdiem[i],arrdiem[i+1]);
          tongkc+=kc;
     }
     return tongkc;
}

//nhap toa do cac diem
void nhaptd(toado arrdiem[],int n)
{
     for(int i=0;i<n;i++)
     {
          cout<<"nhap diem thu "<<i<<endl;
          cout<<"nhap toa do x: ";
          cin>>arrdiem[i].x;
          cin.ignore();
          cout<<"nhap toa do y: ";
          cin>>arrdiem[i].y;
          cin.ignore();
          
     }
}

//xuat
void xuattd(toado arrdiem[],int n)
{
     for(int i=0;i<n;i++)
     {
          cout<<"("<<arrdiem[i].x<<","<<arrdiem[i].y<<")"<<endl;
     }
}

```

**End**

## VIDEO 10 BAI 98 BTRL-CAU TRUC PHAN SO

*Đề: cho phân số có cấu trúc: tử số, mẫu số, Viết hàm: cộng , trừ, nhân, chia, tối giãn phân số*

```
#include<iostream>
#include<string.h>
#include<math.h>
using namespace std;
//de
struct ps
{
     int tuso;
     int mauso;
};
ps *cong(ps ps1,ps ps2);
ps *tru(ps ps1,ps ps2);
ps *nhan(ps ps1,ps ps2);
ps *chia(ps ps1,ps ps2);
int UCLN(ps pstong);
ps *toigian(ps ps);
int main(int argv, char** argc)
{
     ps ps1;
     ps1.tuso=3;
     ps1.mauso=4;
     ps ps2;
     ps2.tuso=1;
     ps2.mauso=2;
     
     ps *ps3=cong(ps1, ps2);
     cout<<"tong 2 phan so la"<<endl;
     cout<<ps3->tuso<<"/"<<ps3->mauso<<endl;
     
     ps *ps4=tru(ps1,ps2);
     cout<<"hieu 2 phan so la"<<endl;
     cout<<ps4->tuso<<"/"<<ps4->mauso<<endl;
     
     ps *ps5=nhan(ps1,ps2);
     cout<<"nhan 2 phan so la"<<endl;
     cout<<ps5->tuso<<"/"<<ps5->mauso<<endl;
     
     ps *ps6=chia(ps1,ps2);
     cout<<"chia 2 phan so la"<<endl;
     cout<<ps6->tuso<<"/"<<ps6->mauso<<endl;
     
     ps *ps7=toigian(*ps3);
     cout<<"tong 2 phan so sau khi toi gian la: "<<endl;
     cout<<ps7->tuso<<"/"<<ps7->mauso<<endl;
     return 0;
}

//cong
ps *cong(ps ps1,ps ps2)
{
     //a/b+c/d=(a*d+c*b)/(b*d)
     ps *ps3=new ps;
     ps3->tuso=ps1.tuso*ps2.mauso+ps2.tuso*ps1.mauso;
     ps3->mauso=ps1.mauso*ps2.mauso;
     return ps3;
}

//tru
ps *tru(ps ps1,ps ps2)
{
     ps *ps3=new ps;
     ps3->tuso=ps1.tuso*ps2.mauso-ps2.tuso*ps1.mauso;
     ps3->mauso=ps1.mauso*ps2.mauso;
     return ps3;
}

//nhan
ps *nhan(ps ps1,ps ps2)
{
     //(a/b) *(c/d)=(a*c)/(b*d)
     ps *ps3=new ps;
     ps3->tuso=ps1.tuso*ps2.tuso;
     ps3->mauso=ps1.mauso*ps2.mauso;
     return ps3;
}

//chia
ps *chia(ps ps1,ps ps2)
{
      //(a/b) *(c/d)=a*d/b*c
     ps *ps3=new ps;
     ps3->tuso=ps1.tuso*ps2.mauso;
     ps3->mauso=ps1.mauso*ps2.tuso;
     return ps3;
}

//uoc chung lon nhat
int UCLN(ps pstong)
{
     int min=pstong.tuso<pstong.mauso?pstong.tuso:pstong.mauso;
     for(int i=min;i>=1;i--)
     {
          if(pstong.tuso%i==0&&pstong.mauso%i==0)
               return i;
     }
     return 1;
}

//toi gian 1 phan so
ps *toigian(ps pstong)
{
     ps *pstoigian=new ps;
     int uoc=UCLN(pstong);
     pstoigian->tuso=pstong.tuso/uoc;
     pstoigian->mauso=pstong.mauso/uoc;
     return pstoigian;
}

```

**End**

## VIDEO 11 BAI 99 BTTRL

*Đề :*

1 Cho cấu trúc nhân viên: Mã, tên, năm sinh

- Nhập xuất nhân viên
- Nhập xuất danh sách nhân viên
- Lọc nhân viên theo năm sinh bất kì

2. Cho cấu trúc phòng ban, nhân viên

- Phòng ban: mã phòng ban, tên phòng ban
- Nhân viên: mã nhân viên, tên nhân viên
- Một phong ban có nhiều nhân viên, 1 nhân viên thuộc về 1 phòng ban
- Nhập xuất phòng ban nhân viên
- Lọc nhân viên theo phòng ban

3. Cho cấu trúc sinh viên, địa chỉ

- Sinh viên: Mã, tên, địa chỉ trường học, địa chỉ nhà riêng
- Địa chỉ: tên đường,quận, tỉnh thành
- Nhập xuất sinh viên, địa chỉ
- lọc sinh viên có cùng tỉnh thành(theo nhà riêng)

1. 

```
#include<iostream>
#include<string.h>
//de 1
using namespace std;
struct nhanvien
{
     char ma[20];
     char ten[100];
     int nam;
};
void nhapnv(nhanvien &i);
void xuatnv(nhanvien i);
void nhapdsnv(nhanvien dsnv[],int n);
void xuatdsnv(nhanvien dsnv[],int n);
bool ns(nhanvien &i,int m);
void locns(nhanvien dssv[],int n,int m);
int main(int argv,char** argc)
{
     int n;
     int m;
     cout<<"nhap so luong nhan vien "<<endl;
     cin>>n;
     nhanvien dsnv[n];
     nhapdsnv(dsnv,n);
     cout<<"DANH SACH NHAN VIEN TRONG CONG TY"<<endl;
     cout<<"---------------------"<<endl;
     xuatdsnv(dsnv,n);
     
     cout<<"Nhap nam sinh can loc"<<endl;
     cin>>m;
     cout<<"Nhan vien co nam sinh: "<<m<<endl;
     locns(dsnv,n,m);
     return 0;
}

//nhap nhan vien
void nhapnv(nhanvien &i)
{
     cout<<"---------------------"<<endl;
     cout<<"Ten: ";
     cin.ignore();
     cin.getline(i.ten,100);
     cout<<"Ma: ";
     cin.getline(i.ma,20);
     cout<<"Nam sinh: ";
     cin>>i.nam;
     cout<<"---------------------"<<endl;
}

//xuat nhan vien
void xuatnv(nhanvien i)
{
     cout<<"Nhan vien: "<<i.ten<<endl;
     cout<<"Nam sinh: "<<i.nam<<endl;
     cout<<"Ma: "<<i.ma<<endl;
}

//nhap danh sach
void nhapdsnv(nhanvien dsnv[],int n)
{
     int j=1;
     for (int i=0;i<n;i++)
     {
          cout<<"nhap nhan vien thu "<<j++<<endl;
          nhapnv(dsnv[i]);
     }
}

//xuat danh sach
void xuatdsnv(nhanvien dsnv[],int n)
{
     for(int i=0;i<n;i++)
     {
          xuatnv(dsnv[i]);
          if (i<=n)
          cout<<"---------------------"<<endl;
     }
}

//loc nhan vien theo nam sinh
bool ns(nhanvien &i,int m)
{
     if(i.nam==m)
          return 0;
     return 1;
}

//loc danh sach nhan vien
void locns(nhanvien dsnv[],int n,int m)
{
     int j=0;
     for(int i=0;i<n;i++)
     {
          if(ns(dsnv[i],m)==0)
          {
               xuatnv(dsnv[i]);
               j++;
          }
          else if (i==n-1 && j==0 )
          {
               cout<<"khong ton tai nhan vien"<<endl;
          }
     }
}

```



2.

```
#include<iostream>
#include<string.h>
using namespace std;
//de 2
struct phongban
{
     int mapb;
     char tenpb[100];
};

struct nhanvien
{
     char manv[20];
     char tennv[100];
     phongban pb;
};
void inputpb(phongban &i);
void outputpb(phongban i);
void inputdspb(phongban dspb[],int n);
void outputdspb(phongban dspb[],int n);
void inputdsnv(phongban dspb[],nhanvien dsnv[],int m,int n);
void outputdsnv(nhanvien dsnv[],int m);
bool checkpb(nhanvien dsnv[],phongban dspb[],int n);
void locnv(nhanvien dsnv[],int m,int n);
int main(int argv, char** argc)
{
     int n;
     cout<<"nhap so luong phong ban: ";
     cin>>n;
     phongban dspb[n];
     inputdspb(dspb,n);
     cout<<"--------------------------------"<<endl;
     cout<<"DANH SACH PHONG BAN CUA CONG TY"<<endl;
     cout<<"--------------------------------"<<endl;
     outputdspb(dspb,n);
     
     int m;
     cout<<"nhap so luong nhan vien hien tai: ";
     cin>>m;
     nhanvien dsnv[m];
     inputdsnv(dspb,dsnv,m,n);
     cout<<"--------------------------------"<<endl;
     cout<<"DANH SACH NHAN SU CUA CONG TY"<<endl;
     cout<<"--------------------------------"<<endl;
     outputdsnv(dsnv,m);
     
     int l;
     cout<<"nhap ma phong ban can loc nhan vien: "<<endl;
     cin>>l;
     cout<<"cac nhan vien thuoc ma: ";
     locnv(dsnv,m,l);
     return 0;
}

//nhap 1 phong ban
void inputpb(phongban &i)
{
     cout<<"---------------------"<<endl;
     cout<<"nhap ten phong ban: ";
     cin.ignore();
     cin.getline(i.tenpb,100);
     cout<<"nhap ma phong ban: ";
     cin>>i.mapb;
     cout<<"---------------------"<<endl;
}

//xuat 1 phong ban
void outputpb(phongban i)
{
     cout<<"phong ban: "<<i.tenpb<<endl;
     cout<<"ma: "<<i.mapb<<endl;
     
}

//nhap danh sach phong ban
void inputdspb(phongban dspb[],int n)
{
     int j=1;
     for(int i=0;i<n;i++)
     {
          cout<<"phong ban: "<<j++<<endl;
          inputpb(dspb[i]);
     }
}

//xuat danh sach phong ban
void outputdspb(phongban dspb[],int n)
{
     for(int i=0;i<n;i++)
     {
          outputpb(dspb[i]);
          if(i<=n)
               cout<<"---------------------"<<endl;
     }
}

//check phong ban co ton tai hay khong
bool checkpb(nhanvien dsnv[],phongban dspb[],int m,int n)
{
     int j=0;
     for(int i=0;i<n;i++)
     {
          for(int j=0;j<m;j++)
          {
               if(dsnv[j].pb.mapb==dspb[i].mapb)
               {
                    return 0;
               }
          }
     }
     return 1;
}

//nhap danh sach sinh vien
void inputdsnv(phongban dspb[],nhanvien dsnv[],int m,int n)
{
     int j=1;
     for(int i=0;i<m;i++)
     {
          cout<<"---------------------"<<endl;
          cout<<"nhan vien: "<<j++<<endl;
          cout<<"nhap ten nhan vien: ";
          cin.ignore();
          cin.getline(dsnv[i].tennv,100);
          cout<<"nhap ma nhan vien: ";
          cin>>dsnv[i].manv;
          cout<<"nhap ma phong ban: ";
          do
          {
               cin>>dsnv[i].pb.mapb;
               if(dsnv[i].pb.mapb>n || checkpb(dsnv,dspb,m,n)!=0)
               {
                    cout<<"phong ban khong ton tai, moi nhap lai"<<endl;
               }
          }while(dsnv[i].pb.mapb>n || checkpb(dsnv,dspb,m,n)!=0);
          cout<<"---------------------"<<endl;
     }
}

//xuat danh sach phong ban sinh vien
void outputdsnv(nhanvien dsnv[],int m)
{
     for(int i=0;i<m;i++)
     {
          cout<<"nhan vien: "<<dsnv[i].tennv<<endl;
          cout<<"ma nhan vien: "<<dsnv[i].manv<<endl;
          cout<<"thuoc phong ban co ma: "<<dsnv[i].pb.mapb<<endl;
          if(i<=m)
               cout<<"---------------------"<<endl;
     }
}

//loc nhan vien theo phong ban
void locnv(nhanvien dsnv[],int m,int n)
{
     for(int i=0;i<m;i++)
     {
          if(n==dsnv[i].pb.mapb)
          {
               cout<<"nhan vien: "<<dsnv[i].tennv<<endl;
               cout<<"ma nhan vien: "<<dsnv[i].manv<<endl;
               cout<<"thuoc phong ban co ma: "<<dsnv[i].pb.mapb<<endl;
          }
     }
}

```

**End**

3. 

```
#include<iostream>
#include<string.h>
//de
using namespace std;

struct diachi
{
     char duong[100];
     char quan[100];
     char tt[100];
};

struct sinhvien
{
     char ma[20];
     char ten[100];
     diachi diachitruong;
     diachi diachinr;
};

void nhapnv(sinhvien &i);
void xuatnv(sinhvien i);
void nhapdsnv(sinhvien dssv[],int n);
void xuatdsnv(sinhvien dssv[],int n);
void sinhvientt(sinhvien dssv[],int n,char *c);
int main(int argv,char** argc)
{
     int n;
     cout<<"nhap so luong sinh vien: ";
     cin>>n;
     sinhvien dssv[n];
     nhapdsnv(dssv,n);
     xuatdsnv(dssv,n);
     
     char *c=new char[100];
     cout<<"nhap tinh thanh can loc:"<<endl;
     cin.getline(c,100);
     /*char *p2=strstr(dssv[0].diachinr.tt,c);
     if(p2!=NULL)
     {
          cout<<"ket qua: "<<endl;
          xuatnv(dssv[0]);
     }
     else
     {
          cout<<"ket qua: KHONG TIM THAY"<<endl;
     }*/
     
     cout<<"ket qua: "<<endl;
     sinhvientt(dssv,n,c);
     return 0;
}

//nhap nhan vien
void nhapnv(sinhvien &i)
{
     cout<<"---------------------"<<endl;
     cout<<"Ten: ";
     cin.ignore();
     cin.getline(i.ten,100);
     cout<<"Ma: ";
     cin.getline(i.ma,20);
     cout<<"Dia chi truong hoc: "<<endl;
     cout<<"Nhap ten duong: ";
     cin.getline(i.diachitruong.duong,100);
     cout<<"Nhap ten quan: ";
     cin.getline(i.diachitruong.quan,100);
     cout<<"Nhap Tinh Thanh ";
     cin.getline(i.diachitruong.tt,100);
     cout<<"Dia chi nha rieng: "<<endl;
     cout<<"Nhap ten duong: ";
     cin.getline(i.diachinr.duong,100);
     cout<<"Nhap ten quan: ";
     cin.getline(i.diachinr.quan,100);
     cout<<"Nhap Tinh Thanh ";
     cin.getline(i.diachinr.tt,100);
     cout<<"---------------------"<<endl;
}

//xuat nhan vien
void xuatnv(sinhvien i)
{
     cout<<"Sinh vien: "<<i.ten<<endl;
     cout<<"Ma: "<<i.ma<<endl;
     cout<<"DC Truong: "<<endl;
     cout<<"Duong: "<<i.diachitruong.duong<<endl;
     cout<<"Quan: "<<i.diachitruong.quan<<endl;
     cout<<"Tinh: "<<i.diachitruong.tt<<endl;
     cout<<"DC Nha:"<<endl;
     cout<<"Duong: "<<i.diachinr.duong<<endl;
     cout<<"Quan: "<<i.diachinr.quan<<endl;
     cout<<"Tinh: "<<i.diachinr.tt<<endl;
     
}

//nhap danh sach
void nhapdsnv(sinhvien dssv[],int n)
{
     int j=1;
     for (int i=0;i<n;i++)
     {
          cout<<"nhap sinh vien thu "<<j++<<endl;
          nhapnv(dssv[i]);
     }
}

//xuat danh sach
void xuatdsnv(sinhvien dssv[],int n)
{
     for(int i=0;i<n;i++)
     {
          xuatnv(dssv[i]);
          if (i<=n)
          cout<<"---------------------"<<endl;
     }
}

//loc sinh vien tinh thanh
void sinhvientt(sinhvien dssv[],int n,char *c)
{
     for(int i=0;i<n;i++)
     {
         char *p2=strstr(dssv[i].diachinr.tt,c);
         if(p2!=NULL)
         {
              xuatnv(dssv[i]);
         }
         else if(i==n-1&&p2==NULL)
         {
              cout<<"KHONG TIM THAY"<<endl;
         }
     }
}

```

**End**

## VIDEO 12 BAI 100 KHAI NIEM TEP TIN

**NOI DUNG**

- Vì sao phải lưu tập tin

- Các loại tập tin lưu trữ

- Các hàm tương tác file

1. Vì sao phải lưu tập tin

- Các dữ liệu ta đang thao tác là trên thanh Ram->mất dữ liệu khi tắt phần mềm, tắt máy
- Nên cần phải lưu trữ vào thiết bị lưu trữ vĩnh cửu rồi nạp trở lại bộ nhớ

2. Các loại tập tin lưu trữ

- Gồm: Text stream và Binary stream

- Text stream:
  - Là 1 chuỗi các ký tự. Trong một text stream, một số ký tự có thể bị chuyển đổi[được hiểu như là một ký tự khác] tuỳ thược môi trường
- Binary stream
  - Là một chuổi bytes mà có sự tương ứng một-một với chuỗi bytes trên thiết bị ngoài. Nghĩa là không có sự chuyển đổi xảy ra. Do đó, số bytes được viết (hay đọc) thì bằng với số bytes trên thiết bị ngoài. 

- File
  - Một file có thể là một tập tin trên dĩa, một terminal, hay máy in. Để tạo kết nối (associate) giữa một stream với một file ta dùng hoạt đông mở (open). Một khi một file được mở, thông tin có thể được trao đổi giữa nó và chương trình
  - Mỗi stream liên đới với một file có cấu trúc kiểu FILE
- Sử dụng các hàm tương tác
  - `stdio.h` là một trong những thư viện dùng để tương tác file
  - `fopen()` Mở một file
  - `fclose()` Đóng một file
  - `fputs()` Viết một chuỗi đến một file 
  - `fgets()` Đọc một chuỗi từ một file
  - `feof()` Trả về true nếu duyệt đến cuối file (end-of-file).
  - `remove()` Xóa một file

**End**

