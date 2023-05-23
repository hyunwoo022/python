# 우리나라의 인구  
  
...  
import pandas as pd  
url = "https://ko.wikipedia.org/wiki/%EB%8C%80%ED%95%9C%EB%AF%BC%EA%B5%AD%EC%9D%98_%EC%9D%B8%EA%B5%AC"  
...
  
...  
table = pd.read_html(url)  
len(table)  
...
  
...  
table[4]  
...
  
...  
df = table[4]  
df.shape  
...
  
...  
df.head()  
...
  
...  
df.tail()  
...
  
# 시각화  
  
...  
import seaborn as sb  
import matplotlib.font_manager as fm  
  
sb.set(font="NanumGothic")  
#sb.set(font="AppleGothic")  
...
  
...  
sb.pointplot(data=df, x="연도 (년)", y="추계인구(명)")  
...
  
# 한글 폰트 설치
  
...  
!apt-get updata -qq  
!apt-get install fonts-nanum* -qq  
...
  
# 코랩 한글 폰트 깨짐 현상, 폰트 설치 후 런타임 다시 시작  
  
...  
!sudo apt-get install -y fonts-nanum  
!sudo fc-cache -fv  
!rm ~/.cache/matplotlib -rf  
...
  
...  
sys_font=fm.findSystemFonts()  
print(f"sys_font number: {len(sys_font)}")  
...
  
...  
sys_font=fm.findSystemFonts()  
print(f"sys_font number: {len(sys_font)}")  
  
nanum_font = [f for f in sys_font if 'Nanum' in f]  
print(f"nanum_font number: {len(nanum_font)}")  
...
  
...  
nanum_font  
...
  
...  
import matplotlib.font_manager as fm  
fontpath = '/usr/share/fonts/truetype/nanum/NanumGothic.ttf'  
font = fm.FontProperties(fname=fontpath,size=10)  
...
  
# 기본글꼴 변경  
  
...  
import matplotlib as mp  
#mp._rebuild()  
mp.pyplot.rc('font', family='NanumGothic')  
...

# 시각화  
  
...  
import seaborn as sb  
import matplotlib.font_manager as fm  
  
fontpath = '/usr/share/fonts/truetype/nanum/NanumGothic.ttf'  
font = fm.FontProperties(fname=fontpath,size=10)  
sb.set(font="NanumGothic")  
...
  
...  
sb.pointplot(data=df, x="연도 (년)", y="추계인구(명)")  
...
  
# 선명하게 lineplot  
# 시각화  
  
...  
import seaborn as sb  
import matplotlib.pyplot as plt  
import matplotlib.font_manager as fm  
  
from IPython.display import set_matplotlib_formats  
set_matplotlib_formats("retina")  
  
sb.set(font="NanumGothic")  
...
  
...  
plt.figure(figsize=(15,4))  
plt.xticks(rotation=60) #각도  
sb.lineplot(data=df, x="연도 (년)", y="추계인구(명)")  
...
  
# 출생자 수  
...  
plt.figure(figsize=(15,4))  
plt.xticks(rotation=60) #각도  
sb.lineplot(data=df, x="연도 (년)", y="출생자수(명)")  
...
  
# 출생자 수와 사망자 수  
  
...  
plt.figure(figsize=(15,4))  
plt.xticks(rotation=60) #각도  
sb.lineplot(data=df, x="연도 (년)", y="출생자수(명)")  
sb.lineplot(data=df, x="연도 (년)", y="사망자수(명)")  
#sb.lineplot(data=df, x="연도 (년)", y="사망자수(명)", color='red')  
...
  
...  
df.columns  
...
  
...  
df[['연도 (년)',  '출생자수(명)', '사망자수(명)']]  
...
  
2. 기상청 API 데이터 가져오기
  
# Python3 샘플 코드
## 디코딩 키 사용
  
...  
import requests  
  
url = 'http://apis.data.go.kr/1360000/AsosHourlyInfoService/getWthrDataList'  
params ={'serviceKey' : '서비스키', 'pageNo' : '1', 'numOfRows' : '10', 'dataType' : 'XML', 'dataCd' : 'ASOS', 'dateCd' : 'HR', 'startDt' : '20100101', 'startHh' : '01', 'endDt' : '20100601', 'endHh' : '01', 'stnIds' : '108' }    
  
response = requests.get(url, params=params)  
print(response.content)  
...
