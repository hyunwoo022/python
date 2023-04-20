# "Hello():함수의 설명을 적을수 있음"  
...  
def Hello():  
    "Hello():함수의 설명을 적을수 있음"  
    print("안녕하세요~")  
    print("파이썬 함수 연습입니다")  
  
Hello()  
help(Hello)  
...

# "두개의 변수를 받아 더하는 함수"  
...  
c = 0  
def add(a,b):  
    global c  
    c = a+b  
    # print(c) #pass  
  
def addr(a,b):  
    return a+b  
  
add(10,20)  
print(c)  
print("------------")  
y = addr(10+20)  
print(y)  
...

...  
a = 20 #전역변수  
def func():  
    a = 10 #지역변수  
    print(a)  
  
func()  
print(a)  
...

...  
def func():  
    b = 10 #지역변수  
    print(b)  
  
func()  
print(b)  
...

...  
a = 10  
def func():  
    b = 20  
    return a + b  
x = func()  
print(x)  
...

...  
def func(a,b=20):  
    print(a+b)  
  
func(10)  
...

...  
