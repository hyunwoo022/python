# CH4 조건문, 반복문  
## 중첩 if문  

...  
score = int(input("점수를 입력해 주세요 : "))  
if (score > 100):  
  print("0~100까지의 숫자로 입력하세요.")  
else:  
  if(score >= 90):  
    print("A")  
  elif(score >= 80):  
    print("B")  
  elif(score >= 70):  
    print("C")  
  elif(score >= 60):  
    print("D")  
  else:  
    print("F")  
  print("학점, 점수: %3d" %score)  
...

...  
import random  
  
numbers = []  
for num in range(0,10):  
  numbers.append(random.randrange(0,10))  
  
print("생성된 리스트", numbers)  
  
for num in range(0,10):  
  if num not in numbers:  
    print("숫자 %d는 리스트에 없습니다." %num)  
...

...  
import random  
  
numbers = []  
for num in range(0,10):  
  numbers.append(random.randrange(0,10))  
  
print("생성된 리스트", numbers)  
  
for num in range(0,10):  
  if num not in numbers:  
    print("숫자 %d는 리스트에 없습니다." %num)  
  else:  
    print("숫자 %d는 리스트에 있습니다." %num)  
...

...  
select, answer, numStr, num1, num2 = 0,0,"",0,0  
  
select = int(input("1.입력한 수식 계산 2.두 수의 합계: "))  
  
if select == 1:  
  numStr = input("*** 수식을 입력하세요 : ")  
  answer = eval(numStr) # 1+2, "string"+"str"  
  print(" %s 결과는 %5.1f입니다. " %(numStr,answer))  
elif select == 2:  
  num1 = int(input("*** 첫번째 숫자를 입력하세요 : "))  
  num2 = int(input("*** 두번째 숫자를 입력하세요 : "))  
  for i in range(num1,num2+1):  
    answer = answer + i  
  print("%d+...+%d는 %d입니다. " %(num1,num2,answer))  
else:  
  print("1 또는 2만 입력해야 합니다. ")  
...

...  
for i in range(0,3,1):   
  print("안녕!")  
...

...  
for i in [0,3,1]:  
  print("안녕@")  
...

...  
for i in range(0,3,1):  
  for j in range(0,5,1):  
    print("i:%d, j:%d" %(i,j))  
...

...  
i,j = 0,0  
for i in range(2,10,1):  
  for j in range(1,10,1):  
    print("%d x %d = %2d" %(i,j,i*j))  
  print("")  
...

...  
i,j = 0,0  
for i in range(2,10,1):  
  for j in range(1,10,1):  
    print("%d x %d = %2d" %(i,j,i*j), end='')  
  print("")  
...

...  
i = 0  
while i<3:  
  print("%d : while문" %i)  
  i = i+1  
...

# Q 1부터 10까지 합계를 while, for문으로
...  
i,hap = 0,0  
i = 1  
while i<11:  
  hap = hap + i  
  i=i+1  
  
print("1부터 10까지의 합계: %d" %hap)  
...

# Q 1부터 10까지 합계를 for문으로
...  
i,hap = 0,0  
i = 1  
for i in range(1,11,1):  
  hap = hap+i  
  
print("1부터 10까지의 합계: %d" %hap)  
...

# while True:  
print("무한 루프ㅠㅠ", end='')  

# break
...  
for i in range(1,100):  
  print("for문 %d번 실행" %i)  
  break  
...

# break  
...  
for i in range(1,100):  
  print("for문 %d번 실행" %i)  
  break  
print("break문 빠짐")  
...

...  
hap = 0  
a,b = 0,0  
while True:  
  a = int(input("덧셈 첫번째 수 입력: "))  
  if a==0:  
    break  
  b = int(input("덧셈 두번째 수 입력: "))  
  hap = a + b  
  print("%d + %d = %d" %(a,b,hap))  
  
print("break로 탈출")  
...

# continue  
...  
hap, i = 0,0  
for i in range(1,10):  
  if i % 2 == 0:  
    print("i:%d" %i)  
    continue  
  hap += i  
  
print("1~100 합계(3의 배수 제외): %d" %hap)  
...

# continue  
...  
hap, i = 0,0  
for i in range(1,101):  
  if i % 3 == 0:  
    continue  
  hap += i  
  
print("1~100 합계(3의 배수 제외): %d" %hap)  
...

...  
fruits = ["사과","바나나","체리"]  
for x in fruits:  
  if x == "바나나":  
    continue  
  print(x)  
...

...  
for x in range(6):  
  print(x)  
else:  
  print("끝")  
...

...  
for x in range(6):  
  if x == 3: break  
  print(x)  
else:  
  print("끝")  
...

...  
# for문 루프는 비워 둘 수 없음  
...  
for x in [0,1,2]:  
  pass  
...

# 두 수를 더하는 함수  
...  
def plus(v1,v2):  
  result = 0  
  result = v1 + v2  
  return result  
  
hap = 0  
hap = plus(10,20)  
print("10+20 plus() 처리 결과는 %d" %hap)  
...

...  
def plus(v1,v2):  
  result = 0  
  result = v1 + v2  
  return result  
  
hap = 0  
hap = plus(10,20)  
print("10+20 plus() 처리 결과는 %d" %hap)  
hap = plus(20,30)  
print("20+30 plus() 처리 결과는 %d" %hap)  
...

# 계산기 코드  
...  
def calc(v1,v2,op):  
  result = 0  
  if op == '+':  
    result = v1 + v2  
  elif op == '-':  
    result = v1 - v2  
  elif op == '*':  
    result = v1 * v2  
  elif op == '/':  
    result = v1 / v2  
  return result  
  
res = 0  
var1,var2,opr = 0,0,""  
  
opr = input("(+,-,*,/) 입력: ")  
var1 = int(input("1번째 수 입력: "))  
var2 = int(input("2번째 수 입력: "))  
res = calc(var1,var2,opr)  
print("계산기 %d %s %d = %d" %(var1,opr,var2,res))  
...

# 전역 변수와 지역변수  
...  
def func1():  
  a = 10 # 지역변수  
  print("func1()에서 a값 %d" %a)  
  
def func2():  
  print("func2()에서 a값 %d" %a)  
  
a = 20 # 전역 변수  
  
func1()  
func2()  
...
