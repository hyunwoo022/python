# 1. CSS_all  
  
...  
<!DOCTYPE html>  
<html lang="ko">  
<head>  
    <meta charset="UTF-8">  
    <meta http-equiv="X-UA-Compatible" content="IE=edge">  
    <meta name="viewport" content="width=device-width, initial-scale=1.0">  
    <title>CSS Wildcard selector</title>  
    <style>  
      * {background-color: gainsboro;}  
      h1 {color: red;}  
      p {color: blue;}  
      body,h1,h3{margin:50; padding: 10;}  
    </style>  
</head>  
<body>  
  <h1>로렘 입숨이란?</h1>  
  <p>Lorem Ipsum 은 단순히 인쇄 및 조판 업계의 더미 텍스트입니다. Lorem Ipsum은 1500년대 이후 업계의 표준 더미 텍스트였습니다. 알 수 없는 인쇄업자가 활자 갤리를 가져와 활자 표본 책을 만들기 위해 뒤섞었습니다. 그것은 5세기 동안 살아남았을 뿐만 아니라 전자식 조판으로의 도약에도 본질적으로 변하지 않았습니다. 1960년대에 Lorem Ipsum 구절이 포함된 Letraset 시트의 출시와 함께 대중화되었으며, 최근에는 Lorem Ipsum 버전을 포함하는 Aldus PageMaker와 같은 데스크탑 출판 소프트웨어로 대중화되었습니다.</p>  
  <h3>그거 어디서 났어?</h3>  
  <p>일반적인 믿음과는 달리 Lorem Ipsum은 단순히 임의의 텍스트가 아닙니다. 그것은 기원전 45년의 고전 라틴 문학에 뿌리를 두고 있으며, 2000년이 넘었습니다. 버지니아에 있는 Hampden-Sydney College의 라틴어 교수인 Richard McClintock은 Lorem Ipsum 구절에서 더 모호한 라틴어 단어 중 하나인 consectetur를 찾아 고전 문학에서 해당 단어의 인용을 검토하면서 의심할 여지 없는 출처를 발견했습니다. Lorem Ipsum은 기원전 45년에 작성된 Cicero의 "de Finibus Bonorum et Malorum"(The Extremes of Good and Evil)의 섹션 1.10.32 및 1.10.33에서 가져온 것입니다. 이 책은 르네상스 시대에 매우 인기 있었던 윤리 이론에 관한 논문입니다. Lorem Ipsum의 첫 줄인 "Lorem ipsum dolor sit amet.."는 섹션 1.10.32의 줄에서 나옵니다.</p>   
</body>  
</html>  
...
  
# 2. CSS_id_selector  
  
...  
<!DOCTYPE html>   
<html lang="ko">  
<head>  
    <meta charset="UTF-8">  
    <meta http-equiv="X-UA-Compatible" content="IE=edge">  
    <meta name="viewport" content="width=device-width, initial-scale=1.0">  
    <title>CSS ID Selector</title>  
    <style>  
      #header {  
        width: 800px; margin: 0 auto;  
        background-color: pink;  
      }  
      #wrap {  
        width: 800px; margin: 0 auto;  
        overflow: hidden;  
      }  
      #aside{  
        width: 200px; float: left;  
        background-color: aqua;  
      }  
      #contect{  
        width: 600px; float: left;  
        background-color: chartreuse;  
      }  
    </style>  
</head>  
<body>  
  <div id="header">  
   <h1>#header 태그</h1>  
  </div>  
  <div id="wrap">  
    <div id="aside">  
      <h1>#aside 태그</h1>  
    </div>  
    <div id="contect">  
      <h1>#contect 태그</h1>  
    </div>  
  </div>  
</body>  
</html>  
...
  
# 3. CSS_class_select  
  
...  
<!DOCTYPE html>  
<html lang="ko">  
<head>  
    <meta charset="UTF-8">  
    <meta http-equiv="X-UA-Compatible" content="IE=edge">  
    <meta name="viewport" content="width=device-width, initial-scale=1.0">  
    <title>class selector</title>  
    <style>  
      .select{  
        color: red;  
      }  
      .select2{  
        color: yellow;  
      }  
      .item{  
        color: blue;  
      }  
      .header{  
        background-color: rgb(11, 232, 169);  
      }  
    </style>  
</head>  
<body>  
  <h1 class="item header">좋아하는 과일 이름</h1>  
  <ul>  
    <li class="select">사과</li>  
    <li class="select2">복숭아</li>  
    <li class="select header">귤</li>  
    <li>딸기</li>  
  </ul>  
</body>  
</html>  
...

# 4. CSS_desc_selector  
  
...  
<!DOCTYPE html>  
<html lang="ko">  
<head>  
    <meta charset="UTF-8">  
    <meta http-equiv="X-UA-Compatible" content="IE=edge">  
    <meta name="viewport" content="width=device-width, initial-scale=1.0">  
    <title>CSS Descendant Selector</title>  
    <style>  
      #header h1,h2{  
        color: red;  
      }  
      #selection h1,#selection h2{  
        color: blue;  
      }  
    </style>  
</head>  
<body>  
  <div id="header">  
    <h1 class="title">타이틀</h1>  
    <div id="nav">  
      <h1>네비게이션</h1>  
    </div>  
  </div>  
  <div id="selection">  
    <h1 class="contect">컨텐츠</h1>  
    <h2>후손 적용 될까?</h2>  
    <p>독자가 페이지의 레이아웃을 볼 때 페이지의 읽을 수 있는 콘텐츠에 주의가 산만해진다는 것은 오래 전부터 확립된 사실입니다. Lorem Ipsum을 사용하는 요점은 'Content here, content here'를 사용하는 것과는 대조적으로 문자의 정규 분포가 다소 있어 읽기 쉬운 영어처럼 보입니다. 현재 많은 탁상 출판 패키지와 웹 페이지 편집기는 기본 모델 텍스트로 Lorem Ipsum을 사용하고 있으며 'lorem ipsum'을 검색하면 아직 초기 단계에 있는 많은 웹 사이트를 발견할 수 있습니다. 때로는 우연히, 때로는 의도적으로(유머 주입 등) 다양한 버전이 수년에 걸쳐 진화했습니다.</p>  
  </div>  
</body>  
</html>  
...
  
# 5. CSS_desc_table  
  
...  
<!DOCTYPE html>  
<html lang="ko">  
<head>  
    <meta charset="UTF-8">  
    <meta http-equiv="X-UA-Compatible" content="IE=edge">  
    <meta name="viewport" content="width=device-width, initial-scale=1.0">  
    <title>Desc Table</title>  
    <style>  
      table > tr > th {  
        color: red;  
      }  
      .color_r{  
        color: blue;  
      }  
    </style>  
</head>  
<body>  
  <table border="1">  
    <tr>  
      <th class="color_r">이름</th>  
      <th class="color_r">지역</th>  
    </tr>  
    <tr>  
      <td>김삿갓</td>  
      <td>파주</td>  
    </tr>  
    <tr>  
      <td>둘리</td>  
      <td>방학동</td>  
    </tr>  
  </table>  
</body>  
</html>  
...
  
# 6. box_widthHeight
  
...  
<!DOCTYPE html>  
<html lang="ko">  
<head>  
    <meta charset="UTF-8">  
    <meta http-equiv="X-UA-Compatible" content="IE=edge">  
    <meta name="viewport" content="width=device-width, initial-scale=1.0">  
    <title>Document</title>  
    <style>  
      div{  
        width: 100px; height: 100px;  
        background-color: red;  
        border: 20px solid black;  
        margin: 0 30px; padding: 0 30px;  
      }  
    </style>  
</head>  
<body>  
  <div class="box">  
    <p>안녕하세요~ 반갑습니다.</p>  
  </div>  
</body>  
</html>  
...
  
...  
<!DOCTYPE html>  
<html lang="ko">  
<head>  
    <meta charset="UTF-8">  
    <meta http-equiv="X-UA-Compatible" content="IE=edge">  
    <meta name="viewport" content="width=device-width, initial-scale=1.0">  
    <title>Document</title>  
    <style>  
      .box{  
        border-width: thick;  
        border-style: dashed;  
        border-color: black;  
        margin: 20px; padding: 20px;  
        border-radius: 30px 30px 0 0;  
      }  
    </style>  
</head>  
<body>  
  <div class="box">  
    <p>안녕하세요~ 반갑습니다.</p>  
  </div>  
</body>  
</html>  
...
  
# 7. font_size  
  
...  
<!DOCTYPE html>  
<html lang="ko">  
<head>  
    <meta charset="UTF-8">  
    <meta http-equiv="X-UA-Compatible" content="IE=edge">  
    <meta name="viewport" content="width=device-width, initial-scale=1.0">  
    <title>CSS font size</title>  
    <style>  
      .a{  
        font-size: large;  
      }  
      .b{  
        font-size: 32px;  
      }  
      .c{  
        font-size: 1.5em; font-style: italic;  
      }  
      .d{  
        font-size: 300%;  
      }  
    </style>  
</head>  
<body>  
  <h1>Lorem Ipsum</h1>  
  <p class="a">Lorem Ipsum</p>  
  <p class="b">Lorem Ipsum</p>  
  <p class="c">Lorem Ipsum</p>  
  <p class="d">Lorem Ipsum</p>  
</body>  
</html>  
...
  
# 8. button1  
  
...  
<!DOCTYPE html>  
<html lang="ko">  
<head>  
    <meta charset="UTF-8">  
    <meta http-equiv="X-UA-Compatible" content="IE=edge">  
    <meta name="viewport" content="width=device-width, initial-scale=1.0">  
    <title>Button</title>  
    <style>  
      .f_big{  
        font-size: 2em;  
      }  
      .f_italic{  
        font-style: italic;  
      }  
      .f_bold{  
        font-weight: bold;  
      }  
      .f_center{  
        text-align: center;  
      }  
      .button{  
        width: 160px; height: 80px;  
        background-color: yellow;  
        border: 10px solid black;  
        border-radius: 30px;  
        box-shadow: 5px 5px 5px #a9a9a9;  
      }  
      .button > a{  
        display: block; line-height: 80px;  
      }  
    </style>  
</head>  
<body>  
  <div class="button">  
    <a href="https://www.daum.net" class="f_big f_italic f_bold f_center">Click</a>  
  </div>  
</body>  
</html>  
...
  
# 9. position  
  
...  
<!DOCTYPE html>  
<html lang="ko">  
<head>  
    <meta charset="UTF-8">  
    <meta http-equiv="X-UA-Compatible" content="IE=edge">  
    <meta name="viewport" content="width=device-width, initial-scale=1.0">  
    <title>Position</title>  
    <style>  
      .box{  
        width: 200px; height: 200px;  
        position: absolute;  
      }  
      .box:nth-child(1){  
        background-color: red;  
        left: 10px; top: 10px;  
        z-index: 10;  
      }  
      .box:nth-child(2){  
        background-color: green;  
        left: 50px; top: 50px;  
        z-index: 5;  
      }  
      .box:nth-child(3){  
        background-color: blue;  
        left: 100px; top: 100px;  
        z-index: 1;  
      }  
    </style>  
</head>  
<body>  
  <div class="box"></div>  
  <div class="box"></div>  
  <div class="box"></div>  
  <h1>위치 속성 적용</h1>  
</body>  
</html>  
...
  
# 10. float_img  
  
...  
<!DOCTYPE html>  
<html lang="ko">  
<head>  
    <meta charset="UTF-8">  
    <meta http-equiv="X-UA-Compatible" content="IE=edge">  
    <meta name="viewport" content="width=device-width, initial-scale=1.0">  
    <title>Document</title>  
    <style>  
      img{  
        float: left;  width: 100px; height: 100px;  
      }  
    </style>  
</head>  
<body>  
  <img src="logo.png" alt="logo"  
  <p>Lorem Ipsum 은 단순히 인쇄 및 조판 업계의 더미 텍스트입니다.</p>  
  <p>Lorem Ipsum은 1500년대 이후 업계의 표준 더미 텍스트였습니다. 알 수 없는 인쇄업자가 활자 갤리를 가져와 활자 표본 책을 만들기 위해 뒤섞었습니다. 그것은 5세기 동안 살아남았을 뿐만 아니라 전자식 조판으로의 도약에도 본질적으로 변하지 않았습니다. 1960년대에 Lorem Ipsum 구절이 포함된 Letraset 시트의 출시와 함께 대중화되었으며, 최근에는 Lorem Ipsum 버전을 포함하는 Aldus PageMaker와 같은 데스크탑 출판 소프트웨어로 대중화되었습니다.</p>  
</body>  
</html>  
...

# 11. float_box  
  
...  
<!DOCTYPE html>  
<html lang="ko">  
<head>  
    <meta charset="UTF-8">  
    <meta http-equiv="X-UA-Compatible" content="IE=edge">  
    <meta name="viewport" content="width=device-width, initial-scale=1.0">  
    <title>float</title>  
    <style>  
      .box{  
        width: 200px; height: 200px;  
        background-color: red;  
        margin: 10px; padding: 10px;  
        float: left;  
        font-size: 3em;  
      }  
    </style>  
</head>  
<body>  
  <div class="box">1</div>  
  <div class="box">2</div>  
</body>  
</html>  
...
