# python
Python Learning Repository

## 자료형
#### 숫자형
정수 : 123, -20, 0  
실수 : 123.45, -4321.5, 6.08e9  
8진수 : 0o456, 0o123  
16진수 : 0xFF, 0x0D, 0x0A

#### 변수
* 문자 또는 밑줄로 시작(beta, _lee)  
* 대소문자를 구분(sum, Sum, SUM)  
* 영문자, 숫자, 밑줄(A-z, 0-9, _)  
* 파이썬 키워드는 사용 불가

///  
a = 10  
b = 20  
c = a + b  
d = b - a  
print(c, d)  
/// 

///  
a = 10  
b = 3  
c = a / b # 나눗셈  
d = a // b # 몫  
e = a % b # 나머지  
f = a * b  
g = a ** b # 제곱  
print(c, d, e, f, g)  
///  

#### 문자열
1. 큰 따옴표 : "hello world!"  
2. 작은 따옴표 : '대한민국'  
3. 큰 따옴표 3개 : """Hello!"""  
4. 작은 따옴표 3개 : ''' Life is too short, You need python '''

///  
myName = "Hyunwoo Lee" # 카멜  
my_name = "이현우" # 스네이크  
MyName = "kiki" # 파스칼  
_my_name = "korea"  
MYNAME = "God is love"  
my2name = "12345"  
myStr = '123' # str  
myNum = 123 # int  
print(myStr, myNum)  
print(type(myStr))  
print(type(myNum))  
///  

#### 여러개 변수 할당

///  
x,y,z = "포도","딸기","수박"  
print(x)  
print(y)  
print(z)  
///  

///  
a = b = c = "오렌지"  
print(a)  
print(b)  
print(c)  
///  

///  
fruits = ["포도","딸기","수박"]  
x,y,z = fruits  
print(x)  
print(y)  
print(z)  
///  

///  
x = "Life"  
y = "is"  
z = "beautiful"  
print(x, y, z)  
print(x+y+z)  
...  

///  
a = 1  
b = 2  
c = 3  
print(a, b, c)  
print(a+b+c)  
///  

#### 데이터 유형
+ 텍스트
+ 숫자  
+ 불(bool)

///  
a = 100  
b = 200  
result = a + b  
print(a, '+', b, '=', result)  
result = b - a  
print(b, '-', a, '=', result)  
result = a * b  
print(a, '*', b, '=', result)  
result = b / a  
print(b, '/', a, '=', result)  
///  

#### input() 함수 이용한 계산기

///  
a = int(input("첫번째 숫자를 입력하세요: "))  
b = int(input("두번째 숫자를 입력하세요: "))  
result = a + b  
print(a, '+', b, '=', result)  
result = b - a  
print(b, '-', a, '=', result)  
result = a * b  
print(a, '*', b, '=', result)  
result = b / a  
print(b, '/', a, '=', result)  
///  

///  
a = int(input("첫번째 숫자를 입력하세요: "))  
b = int(input("두번째 숫자를 입력하세요: "))  
result = a // b  
print(a, '//', b, '=', result)  
result = a % b  
print(a, '%', b, '=', result)  
result = a ** b  
print(a, '**', b, '=', result)  
///  
