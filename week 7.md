# CH5 파일 처리  
"r" : read  
"a" : append  
"w" : write  
"x" : create  
"t" : text  
"b" : binary  


...  
# w  
from google.colab import files  
  
f = open("a.txt",'w')  
f.write("12345")  
f.close()  
  
f = open("a.txt",'w')  
f.write("abcde")  
f.close()  
  
files.download('a.txt')  
...

...  
from google.colab import files  
  
f = open("a.txt",'w')  
f.write("12345")  
f.close()  
  
f = open("a.txt",'a')  
f.write("6789")  
f.close()  
  
files.download('a.txt')  
...

## 생성된 파일이 있으면 에러  
...  
from google.colab import files  
  
f = open("b.txt",'x')  
f.write("abcde")  
f.close()  
  
files.download('b.txt')  
...

# 여러 줄 내용 입력  
...  
from google.colab import files  
  
f = open("a.txt",'w')  
#f.write("12345678\n987654321\nabcde")  
f.write("""1234  
4567  
890""")  
f.close()  
  
files.download('a.txt')  
...

...  
from google.colab import files  
  
t = ("1","2","3","4","\n")  
l = ["a","b","c","d"]  
f = open("a.txt",'w')  
f.writelines(t)  
f.writelines(l)  
f.close()  
  
files.download('a.txt')  
...

# read 모드로 파일 열기  
...  
from google.colab import files  
  
f = open("a.txt",'w')  
f.write("1234")  
f.close()  
  
f = open("a.txt",'r')  
print(f.read())  
f.close()  
  
files.download('a.txt')  
...

# readline() 함수 : 한 줄씩 가져옴  
...  
f = open("a.txt",'w')  
f.write("1234\nabcd")  
f.close()  
  
f = open("a.txt",'r')  
print(f.readline())  
  
files.download('a.txt')  
...

...  
from google.colab import files  
  
import os  
if os.path.exists("a.txt"):  
  os.remove("a.txt") # os.rmdir("folder")  
else:  
  print("파일이 없음")  
...

...  
from google.colab import files  
import os  
  
print(os.listdir('.'))  
os.rename("b.txt","a.txt") # file이름 변경  
print(os.listdir('.'))  
...

# file 존재 유무 확인  
...  
from google.colab import files  
import os  
  
print(os.path.exists('a.txt'))  
print(os.path.exists('b.txt'))  
...

# 구구단 파일로 저장  
...  
from google.colab import files  
import sys  
  
f = open("a.txt",'w', encoding='utf8') # euc-kr  
sys.stdout = f  
for i in range(2,10):  
  for j in range(1,10):  
    print("{} x {} = {}".format(i,j,i*j))  
  print()  
f.close()  
  
files.download('a.txt')  
...

...  
from google.colab import files  
  
f = open("c.txt",'w', encoding='utf8')  
f.write("동해물과 백두산이 마르고 닳도록\n안녕하세요.\nHello World!!")  
f.close()  
  
f = open("c.txt",'r')  
lines = f.readlines()  
for line in lines:  
  print(line, end='')  
f.close()  
  
files.download('c.txt')  
...
