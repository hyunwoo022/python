# 2. print() 서식 출력

...  
print("%d" % 123)  
print("%5d" % 123)  
print("%05d" % 123)  
  
print("%f" % 123.45)    
print("%7.1f" % 123.45)  
print("%7.3f" % 123.45)  
  
print("%s" % "대한민국")    
print("%6s" % "대한민국")  
...

### format 함수 : 순서 지정 가능 

...  
print("{0:d} {1:5d} {2:05d}".format(123,456,789))  
...

...  
print("{2:d} {1:5d} {0:05d}".format(123,456,789))  
...

#### 서식 출력

...  
print("\n줄바꿈\n연습입니다.")  
...

...  
print("\t탭키\t연습")  
...

...  
print("글자가 \"강조\"되는 효과1")  
print("글자가 \'강조\'되는 효과2")  
print("역슬레시 3개출력 \\\\\\")  
print(r"\n \t \" \\ \' @를 그대로 출력") #그대로 출력됨  
...

#### 관계 연산자

...  
a,b = 10,20  
print(a==b, a!=b, a>b, a<b, a>=b, a<=b)  
...

...  
a = 99  
print((a>100) and (a<200))  
print((a>100) or (a<200))  
print(not(a==100))  
...

...  
if(123):  
  print("참이면 보입니다.")  
if(0):  
  print("거짓이면 안 보입니다.")  
...

### 퀴즈2 숫자 입력을 받아 동전으로 바꿔주는 프로그램(500원, 100원, 50원, 10원)  
### 나머지는 거스름 돈으로 출력

...  
bill = int(input("바꿀돈은?"))  
c500 = bill // 500  
bill %= 500  
c100 = bill // 100  
bill %= 100  
c50 = bill // 50  
bill %= 50  
c10 = bill // 10  
bill %= 10  

print("500원짜리 : %d개" % c500)  
print("100원짜리 : %d개" % c100)  
print("50원짜리 : %d개" % c50)  
print("10원짜리 : %d개" % c10)  
print("잔돈 %d원" % bill)  
...

## 조건문  

...  
a = 200  
if(a<100):  
  print("100보다 작음")  
  print("거짓이므로 이 문장은 안 보이겠죠?")  
print("프로그램 끝")  
...

...  
a = 2000  
if(a<100):  
  print("100보다 작음")  
else :  
  print("100보다 크다")  
print("프로그램 끝")  
...

# 홀짝 구분

...  
a = int(input("정수를 입력하세요 : "))  
if(a % 2 == 0) :  
  print("짝수")  
else :    
  print("홀수") 
...

...  
a = 75  
if(a > 50) :  
  if(a < 100) :  
    print("50 < a < 100")  
  else :  
    print("a > 100")  
else :  
  print("a < 50")  
...

...   
frult = ['사과' , '배' , '감' , '포도']
print(frult)
...

...  
frult = ['사과' , '배' , '감' , '포도']
frult.append('딸기')
print(frult)
...

...  
frult = ['사과' , '배' , '감' , '포도']
frult.append('딸기')
if '딸기' in frult :
  print("딸기가 있습니다")
print(frult)
...

...  
import random

number = []
for num in range(0,6) :
  number.append(random.randrange(1,46))
print("생성된 리스트", number)
...

### 반복문

...  
for i in range(0,3,1): # 시작값,끝값+1,증가값  
  print("안녕하세요~") # 반복 내용
...

...  
for i in range(0,3,1):  
  print("안녕하세요~")  
print("반갑습니다^^*")  
...

...  
for i in range(0,3,1):  
  print("%d 안녕하세요~" % i)  
  #print(i)  
print("반갑습니다^^*")   
...

...  
for i in range(1,9,1):  
  print("%d " % i, end="")  
print("\n")  
for i in range(1,9,1):  
  print("%d" % i, end= " ")  
...

...  
sum=0
for i in range(1,11,1):
  sum = sum + i
print("1~10까지 합계 : %d" % sum)
...

#### Quiz3 : 숫자 입력을 받아 1부터 입력된 숫자까지의 합을 for문을 이용하여여 출력하시오.  

...  
sum,num=0,0
num = int(input("숫자입력 : "))
for i in range(1,num+1,1):
  sum = sum + i
print("1~n까지 합계 : %d" % sum)
...

#### 중첩 for문  

...  
i,j,k=0,0,0
k = int(input("구구단 단수 입력 : "))
for i in range(1,10,1):
  print("%d x %d = %2d" % (k,i,k*i))
print("")
...

...  
i,j=0,0
for i in range(1,10,1):
  for j in range(2,10,1):
    print("%d x %d = %2d" % (j,i,i*j), end='\t')
  print("")
...
