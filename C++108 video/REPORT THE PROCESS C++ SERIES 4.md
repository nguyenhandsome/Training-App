# REPORT THE PROCESS C++ SERIES 4

## VIDEO 1 BAI 42 TRUY SUAT VA THAO TAC TREN MANG 1 CHIEU

**VD: Tạo một mảng nguyên a có N phần tử. Mỗi phẩn tử có giá trị là chỉ mục của nó. In mảng ra màn hình**

```
#include<iostream>
using namespace std;
//vd
#define N 4
int main(int argc, char** argv)
{
    while(true)
    {
        char c;
        int a[N];
        cout<<"nhap gia tri cho cac phan tu :"<<endl;
        for(int i=0;i<N;i++)
        {
            cout<<"M["<<i<<"]= ";
            cin>>a[i];
        }
        cout<<"in mang"<<endl;
        for (int i=0;i<N;i++)
        {
            cout<<a[i]<<"\t";
        }
        cout<<endl;
        cout<<"xuat nguoc"<<endl;
        
        for(int i=N-1;i>=0;i--)
        {
            cout<<a[i]<<"\t";
        }
        cout<<"continue ? (y/n)"<<endl;
        cin>>c;
        if(c=='n')
            break;
        
    }
    
    return 0;
}


```

**End**

## VIDEO 2 BAI 43 TIM KIEM TREN MANG 1 CHIEU

**NOI DUNG**

- Với K là 1 số nhập từ bàn phím. Kiểm tra xem K có mặt trong mảng hay không
- Với K là 1 số nhập từ bàn phím. Kiểm tra xem K xuất hiện bao nhiêu lần trong mảng

```
#include<iostream>
using namespace std;
//vd
int main(int argc, char** argv)
{
    while(true)
    {
        char c;
        int k;
        int temp=0;
        int n;
        cout<<"nhap so luong phan tu mang"<<endl;
        cin>>n;
        int a[n];
        cout<<"moi ban nhap cac gia tri cho mang"<<endl;
        for(int i=0;i<n;i++)
        {
            cout<<"a["<<i<<"]=";
            cin>>a[i];
        }
        for(int i=0;i<n;i++)
        {
            cout<<a[i]<<"\t";
        }
        cout<<endl;
        cout<<"nhap phan tu k muon tim"<<endl;
        cin>>k;
        bool kq=false;
        for(int i=0;i<n;i++)
        {
            if(k==a[i])
            {
                temp++;
                //break;
                kq=true;
            }
        }
        if(kq==true)
        {
            cout<<"K co mat trong mang"<<endl;
            cout<<"so lan xuat hien trong mang la "<<temp<<endl;
        }
        else
            cout<<"K khong co mat trong mang"<<endl;
        cout<<"continue ? (y/n)"<<endl;
        cin>>c;
        if(c=='n')
            break;
        
    }
    
    return 0;
}


```

**End**

## VIDEO 3 BAI 44 SAP XEP MANG 1 CHIEU

```
#include<iostream>
#include<time.h>
#include<stdlib.h>
using namespace std;
//vd
int main(int argc, char** argv)
{
    while(true)
    {
        srand(time(NULL));
        char c;
        int n;
        int temp;
        cout<<"nhap so phan tu cho mang"<<endl;
        cin>>n;
        int a[n];
        for(int i=0;i<n;i++)
        {
            a[i]=rand()%100;
            /*cout<<"a["<<i<<"]= ";
            cin>>a[i];*/
        }
        cout<<endl;
        //sap xep
        for (int i=0;i<n-1;i++)
        {
            for(int j=i+1;j<n;j++)
            {
                if(a[i]>a[j])
                {
                    temp=a[i];
                    a[i]=a[j];
                    a[j]=temp;
                }
            }
        }
        for(int i=0;i<n;i++)
        {
            cout<<a[i]<<"\t";
        }
        cout<<endl;
        cout<<"continue ? (y/n)"<<endl;
        cin>>c;
        if(c=='n')
            break;
        
    }
    
    return 0;
}


```

**End**

## VIDEO 4 BAI 45 CACH KHAI BAO MANG 2 CHIEU

**NOI DUNG**

1. C/C++ hỗ trợ mảng nhiều chiều. Dạng đơn giản nhất của mảng nhiều chiều là màng 2 chiều
2. Mảng 2 chiều thực chất là mảng của những mảng 1 chiều. Ta có thể xem mảng 2 chiều là một ma trận gồm nhiều hàng và cột

**Khai báo mảng 2 chiều**

```
type arrayName[rows][columns];
```

- Rows: số hàng
- Columns: số cột

*VD: khai báo mảng số nguyên 3 hàng 4 cột*

```
int num[3][4]
```

```
#include<iostream>
#include<time.h>
#include<stdlib.h>
using namespace std;
//vd
int main(int argc, char** argv)
{
    while(true)
    {
        srand(time(NULL));
        char b;
        int r,c;
        cout<<"nhap so dong"<<endl;
        cin>>r;
        cout<<"nhap so cot"<<endl;
        cin>>c;
        int a[r][c];
        for(int i=0;i<r;i++)
        {
            for(int j=0;j<c;j++)
            {
                a[i][j]=rand()%100;
            }
        }
        for(int i=0;i<r;i++)
        {
            for(int j=0;j<c;j++)
            {
                cout<<a[i][j]<<"\t";
            }
            cout<<endl;
        }
        cout<<"continue ? (y/n)"<<endl;
        cin>>b;
        if(b=='n')
            break;
        
    }
    
    return 0;
}


```

**End**

## VIDEO 5 BAI 46 TRUY SUAT VA THAO TAC TREN MANG 2 CHIEU

**NOI DUNG**

- Khai báo mảng
- Nhập dữ liệu
- Xuất dữ liệu toàn bộ
- Xuất theo dòng
- Xuất theo cột
- Nếu ma trận vuông thì xuất chéo chính và chéo phụ

```
#include<iostream>
#include<time.h>
#include<stdlib.h>
using namespace std;
//vd
int main(int argc, char** argv)
{
    while(true)
    {
        srand(time(NULL));
        char b;
        int r,c;
        cout<<"nhap so dong"<<endl;
        cin>>r;
        cout<<"nhap so cot"<<endl;
        cin>>c;
        int a[r][c];
        for(int i=0;i<r;i++)
        {
            for(int j=0;j<c;j++)
            {
                a[i][j]=rand()%100;
            }
        }
        for(int i=0;i<r;i++)
        {
            for(int j=0;j<c;j++)
            {
                cout<<a[i][j]<<"\t";
            }
            cout<<endl;
        }
        cout<<"ban muon xuat dong nao"<<endl;
        int temp;
        cin>>temp;
        for(int j=0;j<c;j++)
        {
            cout<<a[temp][j]<<"\t";
        }
        cout<<endl;
        cout<<"ban muon xuat cot nao"<<endl;
        int temp1;
        cin>>temp1;
        for(int i=0;i<r;i++)
        {
            cout<<a[i][temp1]<<"\t";
        }
        cout<<endl;
        if(r==c)
        {
            cout<<"duong cheo chinh"<<endl;
            for(int i=0;i<r;i++)
            {
                cout<<a[i][i]<<"\t";
            }
            cout<<endl;
            cout<<"duong cheo phu"<<endl;
            for(int i=0;i<r;i++)
            {
                cout<<a[i][r-i-1]<<"\t";
            }
        }
        cout<<endl;
        cout<<"continue ? (y/n)"<<endl;
        cin>>b;
        if(b=='n')
            break;
        
    }
    
    return 0;
}


```

**End**

## VIDEO 6 BAI 47 BTRL-XU LY MANG MOT CHIEU

*Đề:Viết chương trình nhập vào nột dãy n số thực a[0],a[1],...a[n-1], sắp xếp teo thứ tự giảm dần. Xuất ra dãy số sau khi sắp xếp*

```
#include<iostream>
using namespace std;
//vd
int main(int argc, char** argv)
{
    while(true)
    {
        char c;
        int n;
        double temp;
        cout<<"nhap vao so phan tu cua mang"<<endl;
        cin>>n;
        double a[n];
        for (int i=0;i<n;i++)
        {
            cout<<"a["<<i<<"]= ";
            cin>>a[i];
        }
        //xuat mang
        for (int i=0;i<n;i++)
        {
            cout<<a[i]<<"\t";
        }
        cout<<endl;
        //sap xep
        for(int i=0;i<n-1;i++)
        {
            for(int j=i+1;j<n;j++)
            {
                if(a[i]<a[j])
                {
                    temp=a[i];
                    a[i]=a[j];
                    a[j]=temp;
                }
            }
        }
        //xuat mang sau sap xep
        cout<<"mang sau khi sap xep la"<<endl;
        for (int i=0;i<n;i++)
        {
            cout<<a[i]<<"\t";
        }
        cout<<endl;
        cout<<"continue ? (y/n)"<<endl;
        cin>>c;
        if(c=='n')
            break;
        
    }
    cout<<"good bye"<<endl;
    return 0;
}


```

**End**

## VIDEO 7 BAI 48 BTRL-XU LY MANG 2

- Đề: Viết chương trình nhập vào một mảng nguyên, hãy xuất ra màn hình

1. Phần tử lớn nhất của mảng
2. Phần tử nhỏ nhất của mảng
3. Tính tổng các phần tử trong mảng

```
#include<iostream>
using namespace std;
//vd
int main(int argc, char** argv)
{
    while(true)
    {
        char c;
        int n;
        int max,min;
        int s=0;
        cout<<"nhap vao so phan tu cua mang"<<endl;
        cin>>n;
        int a[n];
        for (int i=0;i<n;i++)
        {
            cout<<"a["<<i<<"]= ";
            cin>>a[i];
        }
        //phan tu lon nhat cua mang
        for(int i=0;i<n;i++)
        {
            if(max<a[i])
                max=a[i];
        }
        cout<<"phan tu lon nhat cua mang la "<<max<<endl;
        //phan tu nho nhat cua mang
        min=max;
        for(int i=0;i<n;i++)
        {
            if(min>a[i])
                min=a[i];
        }
        cout<<"phan tu nho nhat cua mang la "<<min<<endl;
        //tong cac phan tu trong mang
        int i=0;
        do
        {
            s+=a[i];
            i++;
        }while(i<n);
        cout<<"tong la "<<s<<endl;
        cout<<"continue ? (y/n)"<<endl;
        cin>>c;
        if(c=='n')
            break;
        
    }
    cout<<"good bye"<<endl;
    return 0;
}


```

**End**

## VIDEO 8 BAI 49 BTRL-XU LY MANG 3

**NOI DUNG**

*Đề: Viết chương trình nhập vào 1 dãy các số theo thứ tự tăng, nếu nhập sai quy cách thì yêu cầu nhập lại. In dãy số sau khi nhập xong*

*Tự code*

```
#include<iostream>
using namespace std;
//đề
int main(int argc, char** argv)
{
while(true)
{
    int n=0;
    int a[n];
    int i=0;
 char c,b;
    int kt=0;
    //nhap mang
    cout<<"nhap phan tu "<<endl;
    do
    {
        cin>>a[i];
        i++;
        c=getchar();
    }while(c!='\n');
    
    //kiem tra phan tu trong mang
    n=i;
    for(int i=0;i<n-1;i++)
    {
        for(int j=i+1;j<n;j++)
        {
            if(a[i]>a[j])
                kt++;
        }
    }
    if(kt!=0)
        cout<<"nhap lai"<<endl;
    
    //xuat mang sau kiem tra
    else if(kt==0)
    {
        cout<<"mang co cac so theo chieu tang dan la"<<endl;
        for(int i=0;i<n;i++)
        {
            cout<<a[i]<<"\t";
        }
    }
    cout<<endl;
    
    //tiep tuc hay khong
    cout<<"continue ? (y/n)"<<endl;
    cin>>b;
    if(b=='n')
        break;
}
    cout<<"good bye"<<endl;
    return 0;
}
```

*Ý bài*

```
#include<iostream>
using namespace std;
//đề
int main()
{
    while(true)
    {
        int n;
        int c;
        int i=0;
        cout<<"nhap so phan tu cua mang"<<endl;
        cin>>n;
        int a[n];
    
    //nhap phan tu cho mang va sap xep
   while(i<n)
   {
        cout<<"a["<<i<<"]= ";
        cin>>a[i];
        if(i>0 && a[i]<=a[i-1])
            continue;
        i++;
   }
    
    //xuat mang sau kiem tra
    cout<<"mang co cac so theo chieu tang dan la"<<endl;
    for(int i=0;i<n;i++)
    {
        cout<<a[i]<<"\t";
    }
        
        //tiep tuc hay khong
        cout<<"continue ? (y/n)"<<endl;
        cin>>c;
        if(c=='n')
            break;
    }
    cout<<"good bye"<<endl;
    return 0;
}

```

**End**

## VIDEO 9 BAI 50 BTRL-XU LI MANG 4

*Đề: Viết chương trình để chuyển đổi vị trí từ dòng thành cột của một ma trận cấp mxn*

```
#include<iostream>
#include<time.h>
#include<stdlib.h>
using namespace std;
//đề
int main(int argc, char** argv)
{
while(true)
{
    srand(time(NULL));
    char c;
    int m,n;
    cout<<"nhap so dong"<<endl;
    cin>>m;
    cout<<"nhap so cot"<<endl;
    cin>>n;
    int a[m][n];
    
    //nhap mang
    for(int i=0;i<m;i++)
    {
        for(int j=0;j<n;j++)
        {
            a[i][j]=rand()%100;
        }
            
    }
    
    //xuat mang
    for(int i=0;i<m;i++)
    {
        for(int j=0;j<n;j++)
        {
            cout<<a[i][j]<<"\t";
        }
        cout<<endl;
    }
   
    //hoan vi
    int b[n][m];
    for(int i=0;i<m;i++)
    {
        for(int j=0;j<n;j++)
        {
            b[j][i]=a[i][j];
        }
        
    }
    
    //xuat mang sau hoan vi
    cout<<"mang sau hoan vi la"<<endl;
    for(int i=0;i<n;i++)
    {
        for(int j=0;j<m;j++)
        {
            cout<<b[i][j]<<"\t";
        }
        cout<<endl;
    }
    //tiep tuc hay khong
    cout<<"continue ? (y/n)"<<endl;
    cin>>c;
    if(c=='n')
        break;
}
    cout<<"good bye"<<endl;
    return 0;
}


```

**End**

## VIDEO 10 BAI 52 BTRL-XU LY MANG 5

*Đề:*

- Viết chương trình nhập vào một mảng số tự nhiên. Hãy xuất ra màn hình
- Dòng 1: Xuất toàn bộ mảng
- Dòng 2: Gồm các số lẻ, tổng cộng có bao nhiêu số lẻ
- Dòng 3: số chẵn và tổng cộng
- Dòng 4: gồm các số nguyên tố

```
#include<iostream>
#include<time.h>
#include<stdlib.h>
using namespace std;
//đề
int main(int argc, char** argv)
{
while(true)
{
    srand(time(NULL));
    char c,b;
    int n;
    int temp=0;
    cout<<"nhap so luong phan tu cho mang"<<endl;
    cin>>n;
    int a[n];
    
    //random phan tu mang
    for(int i=0;i<n;i++)
    {
        a[i]=rand()%100;
    }
    
    //xuat mang
    for(int i=0;i<n;i++)
    {
        cout<<a[i]<<"\t";
    }
    cout<<endl;
    
    //cac so le va tong cong bao nhieu so le
    cout<<"cac so le trong mang "<<endl;
    for(int i=0;i<n;i++)
    {
        if(a[i]%2!=0)
        {
            cout<<a[i]<<"\t";
            temp++;
        }
        
    }
    cout<<endl;
    cout<<"so luong so le trong mang la "<<temp<<" so"<<endl;
    
    //cac so chang va tong cong bao nhieu so chan
    temp=0;
    cout<<"cac so chan trong mang "<<endl;
    for(int i=0;i<n;i++)
    {
        if(a[i]%2==0)
        {
            cout<<a[i]<<"\t";
            temp++;
        }
        
    }
    cout<<endl;
    cout<<"so luong so chan trong mang la "<<temp<<" so"<<endl;
    
    //cac so nguyen to
    cout<<"cac so nguyen to la"<<endl;
    for(int i=0;i<n;i++)
    {
        temp=0;
        for(int j=2;j<a[i];j++)
        {
            if(a[i]%j==0)
            {
                temp++;
            }
            
        }
        if(temp==0)
            cout<<a[i]<<"\t";
    }
    cout<<endl;
    //tiep tuc hay khong
    cout<<"continue ? (y/n)"<<endl;
    cin>>c;
    if(c=='n')
        break;
}
    cout<<"good bye"<<endl;
    return 0;
}


```

## VIDEO 11 BAI 52 BTTRL

*Đề*

1. Viết chương trình thực hiện việc đảo một mảng một chiều
2. Viết chương trình nhập vào hai ma trận A và B có cấp m,n. In hai ma trận lên màn hình. Tổng hai ma trận A và B là ma trận C được tính bởi công thức: c=a+b(i=0,1,2...m-1;j=0,1,2....n-1). Tính ma trận tổng C và in kết quả ra màn hình
3. Viết chương trình nhập vào hai ma trận A có cấp m,k và B có cấp k,n. In hay ma trận lên màn hình. Tích 2 ma trận A và B là mt C. Tính kq ma trận tích C và in kq ra màn hình
4. Nhập số phần tử nguyên dương của mảng a

- In các số nguyên tố có trong mảng a
- Sắp xếp các số chẵn trong mảng theo thứ tự tăng dần

5. Nhập vào mảng a,b có m và n phần tử

- Nhập các phần tử của a và b ko trùng nhau
- Xếp theo thứ tự tăng dần hai mảng a,b
- Nối 2 mảng này lại thành 1 mảng duy nhất sao cho mảng vẫn tăng

6. Nhập vào một dãy số nguyên dương ngẫu nhiên(random) có n phần tử. In ra số lớn hơn số nhỏ nhất của dãy và nhỏ hơn hay bằng với mọi số còn lại (tìm số nhỏ thứ hai trong dãy). Nếu n phần tử đều bằng nhau thì thông báo: không tồn tại số cần tìm

*Câu 1:*

```
#include<iostream>
#include<time.h>
#include<stdlib.h>
using namespace std;
//đề
int main(int argc, char** argv)
{
while(true)
{
    srand(time(NULL));
    char c;
    int n;
    int temp=0;
    cout<<"nhap so luong phan tu cho mang"<<endl;
    cin>>n;
    int a[n];
    
    //random phan tu mang
    for(int i=0;i<n;i++)
    {
        a[i]=rand()%100;
    }
    
    //xuat mang
    for(int i=0;i<n;i++)
    {
        cout<<a[i]<<"\t";
    }
    cout<<endl;
    
    //dao mang
    int m=n;
    for(int i=0;i<n;i++)
    {
            temp=a[i];
            a[i]=a[m-1];
            a[m-1]=temp;
            m--;
        if(i==m-1 ||i==(m-1)-1)
            break;
    }

    //xuat mang sau khi hoan doi
    for(int i=0;i<n;i++)
    {
        cout<<a[i]<<"\t";
    }
    cout<<endl;
    
    //tiep tuc hay khong
    cout<<"continue ? (y/n)"<<endl;
    cin>>c;
    if(c=='n')
        break;
}
    cout<<"good bye"<<endl;
    return 0;
}


```

**Câu 2**

```
#include<iostream>
#include<time.h>
#include<stdlib.h>
using namespace std;
//đề
int main(int argc, char** argv)
{
while(true)
{
    srand(time(NULL));
    int m,n;
    char c;
    cout<<"nhap so dong"<<endl;
    cin>>m;
    cout<<"nhap so cot"<<endl;
    cin>>n;
    int A[m][n],B[m][n];
    int C[m][n];
    cout<<endl;
    //nhap mang
    for(int i=0;i<m;i++)
    {
        for (int j=0;j<n;j++)
        {
            A[i][j]=rand()%100;
            B[i][j]=rand()%100;
        }
    }
    
    //xuat mang
    for(int i=0;i<m;i++)
    {
        for (int j=0;j<n;j++)
        {
            cout<<A[i][j]<<"\t";
        }
        cout<<endl;
    }
    cout<<endl;
    for(int i=0;i<m;i++)
    {
        for (int j=0;j<n;j++)
        {
            cout<<B[i][j]<<"\t";
        }
        cout<<endl;
    }
    cout<<endl;
    
    //tong 2 mang
    for(int i=0;i<m;i++)
    {
        for (int j=0;j<n;j++)
        {
            C[i][j]=A[i][j]+B[i][j];
        }
    }
    
    //xuat tong 2 mang
    cout<<"tong 2 mang la"<<endl;
    for(int i=0;i<m;i++)
    {
        for (int j=0;j<n;j++)
        {
            cout<<C[i][j]<<"\t";
        }
        cout<<endl;
    }
    cout<<endl;
    
    //tiep tuc hay khong
    cout<<"continue ? (y/n)"<<endl;
    cin>>c;
    if(c=='n')
        break;
}
    cout<<"good bye"<<endl;
    return 0;
}


```

**Câu 3**

```
#include<iostream>
#include<time.h>
#include<stdlib.h>
using namespace std;
//đề
int main(int argc, char** argv)
{
while(true)
{
    srand(time(NULL));
    int m,n,k;
    char c;
    int temp1,temp2;
    int h=0;
    cout<<"nhap so dong cho mang a"<<endl;
    cin>>m;
    cout<<"nhap so cot cho mang a va so dong cho mang b"<<endl;
    cin>>k;
    cout<<"nhap so cot cho mang b"<<endl;
    cin>>n;
    int A[m][k],B[k][n];
    int C[m][n];
    cout<<endl;
    
    //nhap mang
    for(int i=0;i<m;i++)
    {
        for (int j=0;j<k;j++)
        {
            A[i][j]=rand()%10;
        }
    }
    for(int i=0;i<k;i++)
    {
        for (int j=0;j<n;j++)
        {
            B[i][j]=rand()%10;
        }
    }
    
    //xuat mang
    for(int i=0;i<m;i++)
    {
        for (int j=0;j<k;j++)
        {
            cout<<A[i][j]<<"\t";
        }
        cout<<endl;
    }
    cout<<endl;
    for(int i=0;i<k;i++)
    {
        for (int j=0;j<n;j++)
        {
            cout<<B[i][j]<<"\t";
        }
        cout<<endl;
    }
    cout<<endl;
    
    //tich 2 mang
    for(int i=0;i<m;i++)
    {
        for(int j=0;j<n;j++)
        {
            int sum=0;
            for(int h=0;h<k;h++)
            {
                sum+=A[i][h]*B[h][j];
            }
            C[i][j]=sum;
        }
    }
    
    //xuat tich 2 mang
    cout<<"tich 2 mang la"<<endl;
    for(int i=0;i<m;i++)
    {
        for (int j=0;j<n;j++)
        {
            cout<<C[i][j]<<"\t";
        }
        cout<<endl;
    }
    cout<<endl;
    
    //tiep tuc hay khong
    cout<<"continue ? (y/n)"<<endl;
    cin>>c;
    if(c=='n')
        break;
}
    cout<<"good bye"<<endl;
    return 0;
}


```

**Câu 4**

```
#include<iostream>
#include<time.h>
#include<stdlib.h>
using namespace std;
//đề
int main(int argc, char** argv)
{
while(true)
{
    srand(time(NULL));
    char c;
    int n;
    int m=0;
    cout<<"nhap so luong phan tu mang"<<endl;
    cin>>n;
    int a[n];
    int b[m];
    
    //random so trong mang
    for(int i=0;i<n;i++)
    {
        a[i]=rand()%100;
    }
    
    //xuat mang
    for(int i=0;i<n;i++)
    {
        cout<<a[i]<<"\t";
    }
    cout<<endl;
    
    //ham xet cac so nguyen to va xuat
    int temp;
    int temp1=0;
    cout<<"cac so nguyen to co trong mang la"<<endl;
    for(int i=0;i<n;i++)
    {
        temp=0;
        for(int j=2;j<a[i];j++)
        {
            if(a[i]%j==0)
            {
                temp++;
            }
           
        }
        if(temp==0&&a[i]!=1)
        {
            cout<<a[i]<<"\t";
            temp1++;
        }
        if(temp1==0&&i==n-1)
            cout<<"khong co so nguyen to trong mang"<<endl;
    }
    cout<<endl;
    
    //lay cac so chan trong mang
    for(int i=0;i<n;i++)
    {
        if(a[i]%2==0)
        {
            b[m]=a[i];
            m++;
        }
    }
    
    //sap xep theo thu tu tang dan
    for(int i=0;i<m-1;i++)
    {
        for(int j=i+1;j<m;j++)
        {
            if(b[i]>b[j])
            {
                temp=b[i];
                b[i]=b[j];
                b[j]=temp;
            }
        }
    }
    
    //xuat mang sau sap xep
    cout<<"mang sau khi lay so chan xep theo thu tu tang dan la"<<endl;
    for(int i=0;i<m;i++)
    {
        cout<<b[i]<<"\t";
    }
    cout<<endl;
    
    //tiep tuc hay khong
    cout<<"continue ? (y/n)"<<endl;
    cin>>c;
    if(c=='n')
        break;
}
    cout<<"good bye"<<endl;
    return 0;
}


```

**Câu 5**

```
#include<iostream>
#include<time.h>
#include<stdlib.h>
using namespace std;
//đề
int main(int argc, char** argv)
{
while(true)
{
    srand(time(NULL));
    char c;
    int n;
    int m;
    cout<<"nhap so luong phan tu mang 1"<<endl;
    cin>>m;
    cout<<"nhap so luong phan tu mang 2"<<endl;
    cin>>n;
    int a[m];
    int b[n];
    int d[m+n];
    
    //random khong trung
    for(int i=0;i<m;i++)
    {
        a[i]=rand()%100;
    }
    for(int j=0;j<n;j++)
    {
        for(int i=0;i<m;)
        {
            b[j]=rand()%100;
            if(b[j]==a[i])
                continue;
            i++;
        }
    }
    
    //xuat 2 mang
    cout<<"mang 1"<<endl;
    for(int i=0;i<m;i++)
    {
        cout<<a[i]<<"\t";
    }
    cout<<endl;
    cout<<"mang 2"<<endl;
    for(int i=0;i<n;i++)
    {
        cout<<b[i]<<"\t";
    }
    cout<<endl;
    
    //sap xep theo thu tu tang dan 2 mang
    int temp;
    for(int i=0;i<m-1;i++)
    {
        for(int j=i+1;j<m;j++)
        {
            if(a[i]>a[j])
            {
                temp=a[i];
                a[i]=a[j];
                a[j]=temp;
            }
        }
    }
    for(int i=0;i<n-1;i++)
    {
        for(int j=i+1;j<n;j++)
        {
            if(b[i]>b[j])
            {
                temp=b[i];
                b[i]=b[j];
                b[j]=temp;
            }
        }
    }
    
    //xuat 2 mang sau thay doi
    cout<<"2 mang theo thu tu tang dan la"<<endl;
    cout<<"mang 1"<<endl;
    for(int i=0;i<m;i++)
    {
        cout<<a[i]<<"\t";
    }
    cout<<endl;
    cout<<"mang 2"<<endl;
    for(int i=0;i<n;i++)
    {
        cout<<b[i]<<"\t";
    }
    cout<<endl;
    
    //hop hai mang va xep theo chieu tang dan
    int j=0;
    int k=0;
    for(int i=0;i<m+n;i++)
    {
       if(i<m)
       {
           d[i]=a[j];
           j++;
       }
       else
       {
           d[i]=b[k];
           k++;
       }
    }
    
    //sap xep mang hop
    for(int i=0;i<m+n-1;i++)
    {
        for(int j=i+1;j<m+n;j++)
        {
            if(d[i]>d[j])
            {
                temp=d[i];
                d[i]=d[j];
                d[j]=temp;
            }
        }
    }
    
    //xuat mang c
    cout<<"mang hop theo thu tu tang dan la"<<endl;
    for(int i=0;i<m+n;i++)
    {
        cout<<d[i]<<"\t";
    }
    cout<<endl;
    
    //tiep tuc hay khong
    cout<<"continue ? (y/n)"<<endl;
    cin>>c;
    if(c=='n')
        break;
}
    cout<<"good bye"<<endl;
    return 0;
}


```

**Câu 6**

```
#include<iostream>
#include<time.h>
#include<stdlib.h>
using namespace std;
//đề
int main(int argc, char** argv)
{
while(true)
{
    srand(time(NULL));
    char c;
    int n;
    cout<<"nhap so luong phan tu cho mang"<<endl;
    cin>>n;
    int a[n];
    
    //randome mang
    for(int i=0;i<n;i++)
    {
        a[i]=rand()%100;
    }
    
    //xuat mang
    for(int i=0;i<n;i++)
    {
        cout<<a[i]<<"\t";
    }
    cout<<endl;
    
    //so min cua mang
    int min=a[0];
    for(int i=0;i<n;i++)
    {
        if(min>a[i])
        {
            min=a[i];
        }
    }
    
    //in ra min
    cout<<min<<endl;
    
    //tim min thu hai
    int min2;
    for(int i=0;i<n;i++)
    {
        if(a[i]>min)
        {
            min2=a[i];
            for(int j=0;j<n;j++)
            {
                if(min2>a[j]&&a[j]!=min)
                {
                    min2=a[j];
                }
            }
        }
    }
    
    cout<<"min thu hai la"<<endl;
    cout<<min2<<endl;
    //tiep tuc hay khong
    cout<<"continue ? (y/n)"<<endl;
    cin>>c;
    if(c=='n')
        break;
}
    cout<<"good bye"<<endl;
    return 0;
}


```

**End**

## VIDEO 12 KHAI NIEM VA CACH SU DUNG HAM

**NOI DUNG**

- Khái niệm

  1. Hàm là một khối lệnh thực hiện một công việc hoàn chỉnh, được đặt tên và được gọi thực thi nhiều lần tại nhiều vị trí trong chương trình
  2. Hàm còn gọi là 1 chương trình con
  3. Hàm có thể được gọi từ chương trình chính hoặc từ 1 hàm khác
  4. Hàm có giá trị trả về hoặc không. Nếu hàm không có giá trị trả về còn được gọi là thủ tục
  5. Có hai loại hàm:
     - Hàm thư viện: là những hàm được xây dựng sẵn. Muốn sử dụng phải khai báo tv chứa nó trong phần khai báo
     - Hàm do người dùng định nghĩa

  - Cấu trúc tổng quát của hàm

    1. Dạng tổng quát của hàm do người dùng định nghĩa

    ```
    returnType functionName(parameterList)
    {
    body of function
    }
    ```

    2. Tác dụng của return trong hàm

       - Khi một hàm muốn trả về một giá trị nào đó thì chúng ta dùng return. Bất cứ kiểu dữ liệu nào của hàm cũng có thể sử dụng return

    3. Cách triệu gọi hàm

       - Một hàm khi đã định nghĩa nhưng chúng vẫn chưa được thực thi. Chỉ thực thi khi trong chương trình có 1 lời gọi hàm
       - Cú pháp

       ```
       <tên hàm>([danh sách các tham số])
       ```

    **VD:**

    ```
    #include<iostream>
    using namespace std;
    //
    int tong2so(int a,int b);
    void xuatdulieu(int x);
    void output();//prototype
    int main(int argc,char** argv)
    {
        int a,b;
        cin>>a;
        cin>>b;
        int kq=tong2so(a,b);
        cout<<"tong "<<a<<"+"<<b<<"= "<<kq<<endl;
        return 0;
    }
    int tong2so(int a,int b)
    {
        return a+b;
    }
    
    ```

    **End**

    

