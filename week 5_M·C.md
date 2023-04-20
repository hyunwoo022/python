 # func()  
...  
def Hello():  
    "Hello():함수의 설명을 적을수 있음"  
    print("안녕하세요~")  
    print("파이썬 함수 연습입니다")  
  
Hello()  
help(Hello)  
...

# funcAdd  
...  
c = 0  
def add(a,b): 
    "두개의 변수를 받아 더하는 함수"   
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

# funcLocal  
...  
a = 20 #전역변수  
def func():  
    a = 10 #지역변수  
    print(a)  
  
func()  
print(a)  
...

# funcLocalErr  
...  
def func():  
    b = 10 #지역변수  
    print(b)  
  
func()  
print(b)  
...

# funcLocalRef  
...  
a = 10  
def func():  
    b = 20  
    return a + b  
x = func()  
print(x)  
...

# funcDefault  
...  
def func(a,b=20):  
    print(a+b)  
  
func(10)  
...

# tkWidget
...  
from tkinter import *  
  
window = Tk()  
  
#  
  
window.mainloop()  
...

...  
from tkinter import *  
  
window = Tk()  
#  
window.title("윈도우 창 연습")  
window.geometry("400x400") # x는 소문자로  
window.resizable(width=TRUE, height=FALSE)  
  
window.mainloop()  
...

# tkLabel  
...  
from tkinter import *  
  
window = Tk()  
window.title("레이블")  
Label1 = Label(window, text="안녕하세요! 이현우 입니다.")  
Label2 = Label(window, text="Python", font=("궁서체",30),fg="red")  
Label3 = Label(window, text="Love is", bg="yellow", width=20,height=5, anchor=NE)  
  
Label1.pack()  
Label2.pack()  
Label3.pack()  
  
window.mainloop()  
...

# tkImage  
...  
from tkinter import *  
window = Tk(screenName="kiki")  
  
photo = PhotoImage(file = "C:\\3B 42115014\\python\\dog.png")  
Label1 = Label(window, image = photo)  
  
Label1.pack()  
window.mainloop()  
...

...  
from tkinter import *  
window = Tk()  
  
window.title("강아지 사진")  
photo = PhotoImage(file = "C:\\3B 42115014\\python\\dog.png")  
photo2 = PhotoImage(file = "c:\\3B 42115014\\python\\cat.png")  
Label1 = Label(window, image = photo)  
Label2 = Label(window, image = photo2)  
  
Label1.pack(side=LEFT)  
Label2.pack(side=RIGHT)  
  
window.mainloop()  
...

# tkButton
...  
from tkinter import *  
  
tk = Tk()  
tk.geometry("300x200")  
button1 = Button(tk, text="파일썬 종료", fg="blue", bg="yellow", command=quit)  
  
button1.pack()  
  
tk.mainloop()  
...

# tkButtonmg  
...  
from tkinter import *  
from tkinter import messagebox  
  
def myFunc():  
    messagebox.showinfo("강아지 버튼", "강아지 너무 귀엽죠^^")  
  
tk = Tk()  
photo = PhotoImage(file="C:\\3B 42115014\\python\\dog.png")  
#button1 = Button(tk, text="파일썬 종료", fg="blue", bg="yellow", command=quit)  
button1 = Button(tk, image=photo, command=myFunc)  
  
button1.pack()  
tk.mainloop()  
...
