#### CH3. 자료형  

### 1. 인덱싱과 슬라이싱  

...  
L = [0,1,2,3,4,5,6,7,8,9]  
print(L[1])  
...

...  
L = [0,1,2,3,4,5,6,7,8,9]  
print(L[-1])  
...

...  
L = [0,1,2,3,4,5,6,7,8,9]  
print(L[0:9:2])  
...

...  
L = [0,1,2,3,4,5,6,7,8,9]  
print(len(L))  
...

...  
L = [0,1,2,3,4,5,6,7,8,9]  
print(len(L))  
print(L[len(L)-1])  
...

...  
L = [0,1,2,3,4,5,6,7,8,9]  
L[0] = 99  
L[9] = '가나다'  
print(L)  
print(L[9])  
...

...  
a = [1,2,3]  
b = [4,5,6]  
print(a+b)  
...

...  
a = [1,2,3]  
b = [4,5,6]  
c = a+b  
print(a+b)  
print(c)  
...

...  
a = [1,2,3]  
b = [4,5,6]  
c = a+b  
print(a+b)  
print(c)  
print(a*3)  
...

...  
L = [1,2,3,4,5]  
print(L)  
L.append(6)  
print(L)  
...

...  
L = [1,2,3,4,5]  
print(L)  
L.append(6) #리스트 뒤에 추가  
print(L)  
L.remove(3) #해당 요소값을 삭제  
print(L)  
...

...  
k = ['a','b','c','d']  
k.remove('d')  
print(k)  
...

...  
k = "God is love!"  
print(k[:3])  
...

...  
k = "God is love!"  
print(k[:3])  
print(k[6:])  
...

...  
k = "God is love!"  
print(k[:3])  
print(k[6:])  
print(k[-8:-2])  
...

...  
k = " God is love! "  
print(k.upper())  
...

...  
k = " God is love! "  
print(k.upper())  
print(k.lower())  
...

...  
k = " God is love! "  
print(k.upper())  
print(k.lower())  
print(k.strip())  
...

...  
a = " God, is, love! "  
print(a.split(","))  
...

...  
a = ["apple", "banana","cherry"]  
a.append("orange") # 맨뒤에 추가  
print(a)  
...

...  
a = ["apple", "banana","cherry"]  
a.insert(1,"orange") # 지정한 곳에 삽입  
print(a)  
...

...  
a = ["apple", "banana","cherry"]  
a.remove("banana")  
print(a)  
...

...  
a = ["apple", "banana","cherry"]  
a.pop(1)  
print(a)  
...

...  
a = ["apple", "banana","cherry"]  
a.pop() # 맨뒤 삭제  
print(a)  
a.pop(1) # 지정한 위치 삭제  
print(a)  
...

...  
a = ["apple", "banana","cherry"]  
del a[0]  
print(a)  
...

...  
a = ["apple", "banana","cherry"]  
del a[0]  
print(a)  
a.clear()  
print(a)  
...

...  
fruit = ["apple", "banana","cherry"]  
for x in fruit:  
  print(x)  
...

...  
fruit = ["apple", "banana","cherry"]  
for i in range(len(fruit)):  
  print(fruit)  
...

...  
a = [5,3,6,8,1,9,0]  
a.sort()  
print(a)  
...

...  
a = [5,3,6,8,1,9,0,2,4,7]  
a.sort(reverse = True)  
print(a)  
...

...  
a = [5,3,6,8,1,9,0,2,4,7]  
a.sort(reverse = True)  
print(a)  
a.sort()  
print(a)  
...

...  
fruit = ["banana","apple","Kiwi","cherry","Orange"]  
fruit.sort() # 대소문자 구분하여 정렬
print(fruit)  
...

...  
fruit = ["banana","apple","Kiwi","cherry","Orange"]  
fruit.sort() # 대소문자 구분하여 정렬  
print(fruit)  
fruit.sort(key = str.lower) # 대소문자 구분 없이 정렬  
print(fruit)  
...

...  
fruit = ["banana","apple","Kiwi","cherry","Orange"]  
fruit.sort() # 대소문자 구분하여 정렬  
print(fruit)  
fruit.sort(key = str.lower) # 대소문자 구분 없이 정렬  
print(fruit)  
fruit.reverse() # 항목의 순서를 역으로 바꿈  
print(fruit)  
...

...  
fruit = ["banana","apple","Kiwi","cherry","Orange"]  
myList = fruit.copy()  
print(myList)  
...

...  
# list 복사  
fruit = ["banana","apple","Kiwi","cherry","Orange"]  
myList = fruit.copy()  
print(myList)  
cpList = list(fruit)  
print(cpList)  
...

### 2. 튜플(Tuple)  

...  
l = [1,2,3]  
t = (4,5,6)  
l[0] = 5  
print(l)  
...

...  
l = [1,2,3]  
t = (4,5,6)  
l[0] = 5  
print(l)  
# t[0] = 1  
print(t)  
...

...  
f = ["banana","apple","Kiwi","cherry","Orange"]  
print(len(f))  
...

...  
t = ("apple")  
print(t)  
f = ("banana")  
print(f)  
print(type(f))  
...

...  
t = ("apple")  
print(t)  
print(type(t))  
f = ("banana") # 튜플로 인식하기 위해서는 ","필요  
print(f)  
print(type(f))  
...

...  
f = ("banana","apple","Kiwi","cherry","Orange")  
print(f[:4])  
print(f[2:])  
...

...  
f = ("banana","apple","Kiwi","cherry","Orange")  
if "apple" in f:  
  print("Yes, 'apple' is in")  
...

...  
f = ("banana","apple","Kiwi","cherry","Orange")  
if "apple" in f:  
  print("Yes, 'apple' is in")  
else:  
  print("No")  
...

## list<->tuple  

...  
firm = ['Samsung','LG','SK']  
tdata = tuple(firm)  
print(firm)  
...

...  
firm = ['Samsung','LG','SK']  
tdata = tuple(firm)  
print(firm)  
print(tdata)  
...

...  
# tuple에 추가  
t = ("banana","apple","Kiwi","cherry")  
y = list(t)  
y.append("Orange")  
t = tuple(y)  
print(t)  
...

...  
t = ("apple","banana","cherry")  
q = ("kiwi",)  
t += q  
print(t)  
...

...  
t = ('apple','banana','cherry','kiwi')  
l = list(t)  
l.remove('apple')  
t = tuple(l)  
print(t)  
...

...  
t = ('apple','banana','cherry','kiwi')  
l = list(t)  
l.remove('apple')  
t = tuple(l)  
print(t)  
del t  
# print(t)  
...


### 3. dict 사전 자료형  

...  
d = {  
    'a':1,  
    'b':2,  
    'c':3  
}  
print(d)  
print(d.keys())  
print(d.values())  
print(d.items())  
...

...  
car = {  
    "brand" : "BMW",  
    "model" : "GT",  
    "year"  : "1988"  
}  
print(car)  
...

...  
car = {  
    "brand" : "BMW",  
    "model" : "GT",  
    "year"  : "1988"  
}  
print(car)  
print(len(car)) 
car["year"] = 2000  
print(car)  
...

...  
car = {  
    "brand" : "BMW",  
    "model" : "GT",  
    "year"  : "1988"  
}  
print(car)  
print(len(car))  
car["year"] = 2000  
car["item"] = 123456  
...

...  
car = {  
    "brand" : "BMW",  
    "model" : "GT",  
    "year"  : "1988"  
}  
print(car)  
print(len(car))  
car["year"] = 2000  
car["item"] = 123456  
car.update({"color" : "red"})  
print(car)  
...

...  
car : {  
    "brand" : "BMW",  
    "model" : "GT",  
    "year"  : 1988  
}  
car.popitem()  
print(car)  
...

...  
car = {  
    "brand" : "BMW",  
    "model" : "GT",  
    "year"  : 1988  
}  
car.clear() # 비움  
del car # 삭제  
...

...  
car = {  
    "brand" : "BMW",  
    "model" : "GT",  
    "year"  : 1988  
}  
for x in car:  
  print(car[x])  
...

...  
car = {  
    "brand" : "BMW",  
    "model" : "GT",  
    "year"  : 1988  
}  
for x in car.keys():  
  print(x)  
...

...  
car = {  
    "brand" : "BMW",  
    "model" : "GT",  
    "year"  : 1988  
}  
for x in car.values():  
  print(x)  
...

...  
car = {  
    "brand" : "BMW",  
    "model" : "GT",  
    "year"  : 1988  
}  
myCar = dict(car)  
print(myCar)  
...

...  
name1 = {"name":"이현우", "year":2002}  
name2 = {"name":"이현준", "year":2004}  
name3 = {"name":"이점현", "year":1968}  
name4 = {"name":"심미순", "year":1972}  
family = {  
    "name1" :name1,  
    "name2" :name2,  
    "name3" :name3,  
    "name4" :name4  
}  
print(family)  
