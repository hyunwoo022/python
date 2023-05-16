# 1. file1  
  
...  
f = open("C:\\42115014\\python\\CSV\\singer1.csv","r",encoding='UTF-8')  
  
s = f.readline()  
print(s, end="")  
  
s = f.readline()  
print(s, end="")  
  
f.close()  
...
  
# 2. file2  
  
...  
with open("C:\\42115014\\python\\CSV\\singer1.csv","r",encoding='UTF-8') as f:  
  
  s = f.readlines()  
  print(s, end="")  

  #s = f.readline()  
  #print(s, end="")  
...
  
# 3. file3  
  
...  
def printList(pList) :  
    for data in pList :  
        print(data, end='\t')  
    print()  
  
with open("C:\\42115014\\python\\CSV\\singer1.csv","r",encoding='UTF-8') as f:  
    #header = f.readline()  
    #header = header.strip()  
    #headerList = header.split(',')  
    #printList(headerList)  
    for s in f:  
        s = s.strip()  
        rowList = s.split(',')  
        printList(rowList)  
...
  
# 4. file4  
  
...  
with open("C:\\42115014\\python\\CSV\\singer1.csv","r",encoding='UTF-8') as f:  
    with open("C:\\42115014\\python\\CSV\\singer2.csv","w",encoding='UTF-8') as fs:  
        h = f.readline()  
        h = h.strip()  
        hList = h.split(',')  
  
        index1 = hList.index('아이디')  
        index2 = hList.index('이름')  
        index3 = hList.index('평균 키')  
  
        hList = [hList[index1],hList[index2],hList[index3]]  
        hStr = ','.join(map(str,hList))  
        fs.write(hStr + '\n')  
        for s in f :  
            s = s.strip()  
            rList = s.split(',')  
            if int(rList[index3]) >= 165:  
                rList = [rList[index1], rList[index2], rList[index3]]  
                rStr = ','.join(map(str,rList))  
                fs.write(rStr + '\n')  
  
print('Save OK!')  
...
  
# 5. tkinterCounter  
  
...  
from tkinter import *  
  
tk = Tk()  
counter = 0  
  
def clicked():  
    global counter  
    counter += 1  
    label1['text'] = '카운터 :' + str(counter)  
  
def reset():  
    global counter  
    counter = 0  
    label1['text'] = '카운터 리셋됨'  
  
tk.title('GUI 카운터')  
label1 = Label(tk, text='옆에 버튼 있음', fg='blue', font=20)  
label1.pack(side=LEFT, padx=10, pady=10)  
  
#button  
button1 = Button(tk,text='카운트 증가!',bg='green',font=15,width=30,height=5,command=clicked)  
button1.pack(side=LEFT, padx=10, pady=10)  
  
button2 = Button(tk,text='리셋',bg='red',font=15,width=30,height=5,command=reset)  
button2.pack(side=LEFT, padx=10, pady=10)  
  
tk.mainloop()  
...
  
# 6. craw1  
  
...  
import urllib.request  
import bs4  
  
url = "https://www.nate.com"  
res = urllib.request.urlopen(url)  
html = res.read()  
  
bsObject = bs4.BeautifulSoup(res,'html.parser')  
  
print(bsObject)  
...
  
# 7. craw2  
  
...  
import bs4  
import urllib.request  
  
nateurl = "https://www.nate.com"  
htmlObject = urllib.request.urlopen(nateurl)  
WebPape = htmlObject.read()  
bsObject = bs4.BeautifulSoup(webPape,'html.parser')  
  
tag = bsObject.find('div', {'id':'NateBi'})  
print(tag, '\n')  
  
a_tag = tag.finda('a')  
print(a_tag, '\n')  
  
href = a_tag['href']  
print(href, '\n')  
  
text = a_tag.text  
print(text)  
...
