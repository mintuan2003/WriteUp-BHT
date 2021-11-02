# WriteUp BHT 
 ### Lưu đồ thuật toán  + Code
 ![image](https://user-images.githubusercontent.com/93105703/139884121-d9d7e8d5-d0e9-4990-949c-bd670617eacd.png)
 ## Ý tưởng 

 * Muốn có x^11 với số lần nhân ít nhất thì ta cần 2 lần nhân (x^11 = x^5 * x^5 *x)
 * Muốn có x^5 với số lần nhân ít nhất thì ta cần 2 lần nhân (x^5 = x^2 * x^2 *x)  
 * Muốn có x^2 với số lần nhân ít nhất thì ta cần 1 lầm nhân (x^2 = x*x)
 * Vậy nên muốn có x^11 với số lần nhân ít nhất thì cần bắt đầu từ x^2 -> x^5 -> x^11  (5 lần nhân)
  ## Lưu đồ thuật toán 
![bai 1](https://user-images.githubusercontent.com/93105703/139921107-6822382e-ad49-4ae5-8225-ca1766d69077.png)

  ## Code 
  ```
 #include <iostream>

using namespace std;

int main()
{
   int x;
   cin>>x;
   int x2=x*x;
   int x5=x2*x2*x;
   int x11=x5*x5*x;
   cout<<x11;
   return 0;
}
```
![image](https://user-images.githubusercontent.com/93105703/139910722-befb3e02-558a-4fc5-954a-20dfa904c35c.png)
## Ý tưởng 
* Sử dụng phép toán Chia lấy phần dư (%) và Chia lấy phần nguyên (/) để "Tách" các số hạng của n rồi cộng chúng lại với nhau
## Lưu đồ thuật toán
![bai 2](https://user-images.githubusercontent.com/93105703/139911398-a993fce7-4fd7-4d3d-a966-a001b7b7afb6.png)
## Code 
```
#include <iostream>

using namespace std;

int main()
{
    int n;
    cin>>n;
    int kq=0;
    while (n>0)
    {
        kq+=n%10;
        n=n/10;
    }
    cout<<kq;
    return 0;
}
```
![image](https://user-images.githubusercontent.com/93105703/139911690-4bfc2b92-94a9-47ce-923b-d2f25dd8db4e.png)
## Ý tưởng 
* Đây là phép toán cộng với số lần biết trước => Sử dụng vòng lặp for
* Với tử số tăng x lần sau mỗi lần cộng 
* Và mẫu số tăng i đơn vị sau mỗi lần cộng
## Lưu đồ thuật toán
![bai 3](https://user-images.githubusercontent.com/93105703/139912205-e9ae88dd-439e-4c6c-ac46-de1cdc4d314b.png)
## Code
```
#include <iostream>

using namespace std;

int main()
{
    int x,n;
    cin>>x>>n;
    double kq=x;
    double tu=1;
    double mau=x;
    for (int i=2;i<=n;i++)
    {
        mau=mau+i;
        tu=tu*x;
        kq= kq+ tu/mau;
    }
    cout<<kq;
    return 0;
}

```
![image](https://user-images.githubusercontent.com/93105703/139912447-faacf1e8-52e2-43bf-8ad1-56c145d500a8.png)
## Ý tưởng
* Lại 1 bài toán cộng với số lần biết trước => Sử dụng for ( Số lần lặp = n)
* Với giá trị y cộng vào tăng -(x^2) lần sau mỗi lần cộng
## Lưu đồ thuật toán
![bai 4](https://user-images.githubusercontent.com/93105703/139912989-d01f2903-eae9-4e93-8ad8-4a295c53a68c.png)
## Code
```
#include <iostream>

using namespace std;

int main()
{
    int x,n;
    cin>>x>>n;
    int kq=0;
    int y=1;
    for (int i=1;i<=n;i++)
    {
        y*=(-1)*x*x;
        kq+=y;
    }
    cout<<kq;
    return 0;
}
```
![image](https://user-images.githubusercontent.com/93105703/139913261-1b7443ef-653e-4ca1-99b5-8ce478a33dcd.png)
## Ý tưởng
* Đây tiếp tục là 1 bài toán tính với số lần lặp biết trước ( Số lần lặp = n)
* Sử dụng hàm sqrt() của thư viện <math.h> để tính căn 
* Dễ thấy: Giá trị cộng vào y tăng x lần sau mỗi lần cộng
## Lưu đồ thuật toán
![bai 5](https://user-images.githubusercontent.com/93105703/139913933-48421184-5d94-4a10-89de-d96cc5db3779.png)
## Code
```
#include <iostream>
#include <math.h>

using namespace std;

int main()
{
    int x,n;
    cin>>x>>n;
    int y=1;
    double kq=0;
    for (int i=1;i<=n;i++)
    {
        y=y*x;
        kq=sqrt(y + kq);
    }
    cout<<kq;
    return 0;
}
```
![image](https://user-images.githubusercontent.com/93105703/139914124-be89513a-3b4e-4d1a-ac4b-d767b525172f.png)
## Ý tưởng
 * Với độ chính xác 10^-6 thì => có giá trị x nhỏ nhất cộng vào bằng 10^-6 
 * Hoặc nếu giá trị cộng vào là 1/x thì x lớn nhất phải bằng 10^6
## Lưu đồ thuật toán
![bai 6](https://user-images.githubusercontent.com/93105703/139914683-82d2e674-0511-4896-bc9e-b62740948e69.png)
## Code 
```
#include <iostream>
#include <iomanip>

using namespace std;

int main()
{
    double kq=0;
    double i=1;
    for (double i=1.0;i<=1000000;i++)
    {
       kq+=1/i;
    }
    cout<<kq<<endl;
      cout<<fixed<<setprecision(6)<<kq;

    return 0;
}
```
![image](https://user-images.githubusercontent.com/93105703/139914803-abbf3113-8fab-4e97-abe7-4f0f9671a7f6.png)
## Ý tưởng
* Muốn tìm a[n] thì sẽ cần tính a[n-1]
* Và bắt đầu với a[1]=-2 -> a[2] -> a[3] -> ... -> a[n]
* Vì là lặp với số lần biết trước=> sẽ sử dụng vòng for
## Lưu đồ thuật toán
![bai 7](https://user-images.githubusercontent.com/93105703/139916238-77180eae-f50a-4027-9840-7d81ffae9b5f.png)
## Code
```
#include <iostream>

using namespace std;

int main()
{
    int n;
    cin>>n;
    int kq=-2;
    int mu3=2*3;
    int mu7=6*7;
    for(int i=2;i<=n;i++)
    {
        mu3=mu3*3;
        mu7=mu7*7;
        kq=5*kq+mu3-mu7+12;
    }
    cout<<kq;
    return 0;
}
```
![image](https://user-images.githubusercontent.com/93105703/139916339-192ea06f-b704-490a-8227-8d3df900656d.png)
## Ý tưởng
* Sử dụng câu lệnh if,else 
* Kết hợp với tính chất cosin của tam giác để xác định các trường hợp của tam giác 
 1. Nếu giá trị cosin của 3 góc bằng nhau => Tam giác đều 
 2. Tồn tại 1 giá trị cosin bằng 0 => Tam giác vuông 
 3. Các giá trị cosin đều lớn hơn 0 => Tam giác nhọn
 4. Có 1 giá trị cosin nhỏ hơn 0 => Tam giác tù 
 ## Lưu đồ thuật toán
 ![bai 8](https://user-images.githubusercontent.com/93105703/139917992-a954aeb7-b242-4cb6-ac10-df56d5b5880a.png)
 ## Code 
 ```
 #include <iostream>

using namespace std;

int main()
{
    float  x,y,z;
    cin>>x>>y>>z;
    float cosA=(x*x+y*y-z*z)/(2*x*y);
    float cosB=(x*x+z*z-y*y)/(2*x*z);
    float cosC=(y*y+z*z-x*x)/(2*y*z);
    if (cosA==cosB && cosB==cosC) cout<<"Tam giac deu";
        else if( cosA==1 || cosB==1 || cosC==1) cout<<"Tam giac vuong";
              else if ( cosA<0 || cosB<0 || cosC<0 ) cout<<"Tam giac tu";
                    else cout<<"Tam giac nhon";
    return 0;
}
```
![image](https://user-images.githubusercontent.com/93105703/139918161-5f85bd44-d9ab-40f0-9574-1e5f52cbc357.png)
## Ý tưởng 
* Sử dụng vòng for kiểm tra i từ 1-> 100 000 000 ( Giá trị max của for)
* Nếu tồn tại giá trị i nguyên mà i*i == n thì sẽ thông báo "co" ngược lại thông báo "khong";
* Nhưng nếu như với giá trị n nhỏ mà vẫn chạy i đến 10^8 thì sẽ rất mất thời gian => Nên nếu i*i mà đã lớn hơn giá trị n rồi thì sẽ dừng lại (không tăng i để kiểm tra nữa)
## Lưu đồ thuật toán
![bai 9](https://user-images.githubusercontent.com/93105703/139920108-daaf0156-af83-4eb4-8aed-1908a77f0231.png)
## Code 
```#include <iostream>

using namespace std;

int main()
{
    int n;
    cin>>n;
    for(int i=1;i<=100000000;i++)
    {
        if (i*i==n) {cout<<"n la so chinh phuong";break;};
        if (i*i>n) {cout<<"n khong la so chinh phuong";break;};
    }
    return 0;
}
```
![image](https://user-images.githubusercontent.com/93105703/139920179-23a6a8e6-2a3c-4dfa-83ca-8ed6dca21a49.png)
### Ý tưởng
* Chia n cho 5 đến khi nào n=1 thì n có dạng 5^m ( m nguyên dương)
* Nếu không n sẽ không là dạng 5^m
## Lưu đồ thuật toán
![bai 10](https://user-images.githubusercontent.com/93105703/139920686-3c9da6a3-0a03-45f4-8842-6c02d1b24da5.png)
## Code
```
#include <iostream>

using namespace std;

int main()
{
    int n;
    cin>>n;
    while (n>1)
    {
        if(n%5==0) n=n/5;
        else {cout<<"khong";break;};
    }
    if (n==1) cout<<"co";
    return 0;
}
```
