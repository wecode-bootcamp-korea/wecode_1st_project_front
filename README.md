#### - BOX MODEL 분석
![](https://images.velog.io/images/minj9_6/post/2d141459-824e-41e3-93f4-2da5ea1bf4f2/image.png)

#### - 1차 HTML 마크업
>```
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=
  , initial-scale=1.0">
  <title>Document</title>
  <link href="https://fonts.googleapis.com/css2?family=Dancing+Script&display=swap" rel="stylesheet"> <!-- 구글 폰트 -->
  <link rel="stylesheet" href="styles/style.css">
</head>
<body>
  <section class="container">
    <header class="item">WeBucks</header>
    <form action="" id="loginBox" class="item">
      <input type="text" placeholder="전화번호, 사용자 이름 또는 이메일">
      <input type="password" placeholder="비밀번호">
      <button>로그인</button>
    </form>
    <a href="" class="item">비밀번호를 잊으셨나요?</a>
  </section>
</body>
</html>
```

#### 1차 CSS 작업
>
```
<style>
* {
  box-sizing: border-box;
}
body {
  background-color: #eeefef;
  margin: 50px auto;
  width: 35%;
  overflow: hidden; /* 스크롤 생김 방지 */
}
.container{
  background-color: white;
  border: 5px solid #e8e8e8;
  border-radius: 10px;
  margin: 80px auto;
  width: 100%;
  height: 750px;
  display: flex;
  flex-direction: column;
  text-align: center;
  padding: 0 80px
}
.item{
  flex:1 1 0;
}
.item:nth-child(1){
  flex: 0.75 1 0;
  /* header 태그 영역의 사이즈를 줄여준다 */
}
.item:nth-child(2){
  flex: 0.75 1 0;
  /* form 태그 영역의 사이즈를 줄여준다 */
}
header {
  display: flex;
  justify-content: center;
  align-items: center;
  font-family: 'Dancing Script', cursive;
  font-size: 75px;
  font-weight: bold;
}
#loginBox{
  display: flex;
  flex-direction: column;
  justify-content: space-around;
}
#loginBox input{
  background-color: #f7f7f7;
  border: 3px solid #eaeaea;
  border-radius: 5px;
  padding: 0 10px;
  height: 50px;
  color: rgb(122, 122, 122);
  font-size: 16.5px;
}
#loginBox button{
  height: 50px;
  background-color: #add3eb;
  border: 3px solid #add3eb;
  border-radius: 10px;
  font-size: 18px;
  color: white;
}
a{
  text-decoration: none;
  color: rgb(130, 164, 188);
  font-weight:bolder;
  align-self: center;
  position: relative;
  top: 200px;
}
</style>
```

-2차 JS 작업
>
```
<script>
const id = document.getElementById("loginId");
const psw = document.getElementById('loginPsw');
const loginBtn = document.getElementById('loginBtn')
const loginBox = document.getElementById('loginBox')
const linkListPage = (event) => { // 유효성 통과 후 버튼 클릭시 리스트 페이지로 가는 함수
  event.preventDefault();
  if(id.value.includes('@') && psw.value.length>=8) {
  return window.location.href="../list.html"
  }
}
const checkedIdNPsw = () => { // id와 psw 유효할시 로그인 창 투명해지도록 하는 함수
  if(id.value.includes('@') && psw.value.length>=8) {
    return loginBtn.style.opacity = 0.5;
  }
}
loginBox.addEventListener('input', checkedIdNPsw)
loginBtn.addEventListener('click', linkListPage)
</script>
```

#### - 모르는 점
>-돔 이벤트에 따른 파라미터 전달 e target 등
-input 태그의 값의 접근 value로 
-로그인 과정 더 찾아보기
-버튼의 기능을 막으면 유효성 검사를 구현할 수 없다(?!)

#### - 2차 HTML, CSS, JS 결과물
>![](https://images.velog.io/images/minj9_6/post/d67c8124-e141-4556-b586-0af2c7e9bceb/image.png)![](https://images.velog.io/images/minj9_6/post/8f98d9fc-0777-40a0-b67d-bdc8d7aefd3f/image.png)

----

#### - 3차 BOX BODEL 분석

![](https://images.velog.io/images/minj9_6/post/01d823f3-f1f1-4db2-8810-95c6170ff055/image.png)

#### 3차 HTML 마크업 작업 

>
```
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
  <link rel="stylesheet" href="styles/style.css">
  <link rel="stylesheet" href="styles/list.css">
  <link href="https://fonts.googleapis.com/css2?family=Dancing+Script&display=swap" rel="stylesheet"> <!-- 구글 폰트 -->
  <script async src="js/list.js"></script>
</head>
<body>
  <header>
    <span id="title">WeBucks</span>
    <div id='headerMenu'>
      <span>COFFEE</span>
      <span>MENU</span>
      <span>STORE</span>
      <span>WHAT'S NEW</span>
    </div>
  </header>
  <main>
    <section class="mainSection">
      <div class="sectionHeader">
        <span>콜드 브루 커피</span>
        <span> ☕ &nbsp디카페인 에스프레소 샷 추가 기능 (일부 음료 제외)</span>
      </div>
      <div class="sectionMain">
      </div>
    </section>
    <section class="mainSection">
      <div class="sectionHeader">
        <span>브루드 커피</span>
        <span> ☕ &nbsp디카페인 에스프레소 샷 추가 기능 (일부 음료 제외)</span>
      </div>
      <div class="sectionMain">
      </div>
    </section>
  </main>
</body>
</html>
```

#### - 3차 CSS 작업 

>
```
<style>
* {
  box-sizing: border-box;
}
body {
  margin: auto;
  width: 75%;
  background-color: white;
}
header {
  background-color: rgb(244, 244, 242);
  display: flex;
  justify-content: space-between;
  padding: 15px;
  margin-bottom: 20px;
}
#title{
  font-size: 20px;
  font-weight: bolder;
  font-family: 'Dancing Script', cursive;
}
#headerMenu{
  display: flex;
  justify-content: space-evenly;
  font-size: 15px;
  flex-basis: 300px;
  color: rgb(165, 165, 161);
}
.mainSection{
  margin-bottom: 20px; 
}
section {
  width: 100%;
}
.sectionHeader{
  background-color: rgb(246, 240, 245);
  padding: 15px;
  height: 48px;
}
.sectionHeader span:nth-child(1){
  font-weight: bolder;
}
.sectionHeader span:nth-child(2){
  font-size: 13px;
  padding-left: 20px;
}
.sectionMain{
  text-align: center;
  display: grid;
  height: auto;
  margin: 20px 0px; 
  grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
  grid-gap: 15px;
}
</style>
```

#### - 3차 JS 작업

>
```
<script>
const coldBrewCoffeeAndImg = [ // 콜드 브루 음료 커피이름과 이미지 모은 객체
  {
    img: "https://image.istarbucks.co.kr/upload/store/skuimg/2021/04/[9200000002487]_20210426091745467.jpg",
    title: "나이트로 바닐라 크림",
  },
  {
    img: "https://image.istarbucks.co.kr/upload/store/skuimg/2021/04/[9200000000479]_20210426091843897.jpg",
    title: "나이트로 콜드 브루",
  },
  {
    img: "https://image.istarbucks.co.kr/upload/store/skuimg/2021/04/[9200000002081]_20210415133656839.jpg",
    title: "돌체 콜드 브루",
  },
  {
    img: "https://image.istarbucks.co.kr/upload/store/skuimg/2021/04/[9200000000487]_20210430112319040.jpg",
    title: "벨벳 다크 모카 나이트로",
  },
  {
    img: "https://image.istarbucks.co.kr/upload/store/skuimg/2021/03/[9200000003509]_20210322093452399.jpg",
    title: " 바닐라 크림 콜드 브루",
  },
  {
    img: "https://image.istarbucks.co.kr/upload/store/skuimg/2020/09/[9200000002672]_20200921171223898.jpg",
    title: "제주 비자림 콜드 브루",
  },
  {
    img: "https://image.istarbucks.co.kr/upload/store/skuimg/2021/04/[9200000000038]_20210430113202458.jpg",
    title: "콜드 브루",
  },
  {
    img: "https://image.istarbucks.co.kr/upload/store/skuimg/2021/02/[9200000001636]_20210225093600536.jpg",
    title: "콜드 브루 몰트",
  },
  {
    img: "https://image.istarbucks.co.kr/upload/store/skuimg/2021/04/[9200000003285]_20210416154437069.jpg",
    title: "콜드 브루 오트 라떼",
  },
  {
    img: "https://image.istarbucks.co.kr/upload/store/skuimg/2021/02/[9200000001635]_20210225092236748.jpg",
    title: "콜드 브루 플로트",
  },
  {
    img: "https://image.istarbucks.co.kr/upload/store/skuimg/2021/03/[9200000003507]_20210322093414289.jpg",
    title: "프렌치 애플 타르트 나이트로",
  },
];
const firstMainSection = document.getElementsByClassName('sectionMain')[0]; // 그리드가 들어가는 첫번재 메인 섹션
for(let i = 0; i<coldBrewCoffeeAndImg.length; i++){ // 반복문을 돌며 이미지와 이름을 HTML에 태그로 추가한다.
const imgWrapper = document.createElement('div');
imgWrapper.setAttribute('class','imgWrapper')
let divTag = document.createElement('div')
divTag.setAttribute("class","bvgImg");
divTag.style.marginBottom = `15px`
let beverageImg = document.createElement('img');
beverageImg.style.marginBottom = '15px'
beverageImg.src = coldBrewCoffeeAndImg[i].img;
let beverageName = document.createElement('span');
beverageName.innerHTML = coldBrewCoffeeAndImg[i].title;
imgWrapper.appendChild(beverageImg)
divTag.appendChild(imgWrapper);
divTag.appendChild(beverageName);
firstMainSection.appendChild(divTag);
if(divTag){
  divTag.onmouseover = () => {
    setTimeout(function(){
      beverageImg.classList.add('magnifiedImg')
    },100)
  }
  divTag.onmouseout = () => {
    setTimeout(function(){
      beverageImg.classList.remove('magnifiedImg')
    },100)
  }
}
}
const secondMainSection = document.getElementsByClassName('sectionMain')[1];
const brewedCoffeeAndImg = [
  {
    img: "https://image.istarbucks.co.kr/upload/store/skuimg/2021/02/[9200000001635]_20210225092236748.jpg",
    title: "콜드 브루 플로트",
  },
  {
    img: "https://image.istarbucks.co.kr/upload/store/skuimg/2021/03/[9200000003507]_20210322093414289.jpg",
    title: "프렌치 애플 타르트 나이트로",
  },
]
for(let i = 0; i<brewedCoffeeAndImg.length; i++){
  const imgWrapper = document.createElement('div');
  imgWrapper.setAttribute('class','imgWrapper')
  let divTag = document.createElement('div');
  divTag.setAttribute("class","bvgImg");
  divTag.style.marginBottom = `15px`
  let beverageImg = document.createElement('img');
  beverageImg.setAttribute('class','bvgImg')
  beverageImg.style.marginBottom = '15px'
  beverageImg.src = brewedCoffeeAndImg[i].img;
  let beverageName = document.createElement('span');
  beverageName.innerHTML = brewedCoffeeAndImg[i].title;
  imgWrapper.appendChild(beverageImg)
  divTag.appendChild(imgWrapper);
  divTag.appendChild(beverageName);
  secondMainSection.appendChild(divTag)
  if(divTag){
    divTag.onmouseover = () => {
      setTimeout(function(){
        beverageImg.classList.toggle('magnifiedImg')
      },100)
    }
    divTag.onmouseout = () => {
      setTimeout(function(){
        beverageImg.classList.remove('magnifiedImg')
      },100)
    }
  }
}
</script> 
```

#### - 모르는 점
>- 문제를 똑바로 읽자, css, grid만 활용해서 만드는 거였다..!
- 이벤트를 태그 자체에 달아서 함수를 호출하는 법에 대해서
  
#### - 3차 HTML, CSS, JS 작업 결과물
>![](https://images.velog.io/images/minj9_6/post/90ccce62-82ee-48e9-b93f-bcf232dff05b/ALCA0CA.png)![](https://images.velog.io/images/minj9_6/post/dd6e8408-f385-4ddb-ae51-062ceaa3d9c0/image.png)
  
  ----
  
#### Refactoring
>- 단계별 진행
  -Semantic tag : nav 태그 활용, h1, h2와 같이 span 대체 할 수 있는 태그, article같이 의미를 가진 태그들이 많다.
  -img 태그 alt 필수로 입력하기
  
  
  
#### - 4차 BOX MODOE 분석


![](https://images.velog.io/images/minj9_6/post/1f385992-5181-4525-adf2-75949f534e3c/image.png)


#### - 4차 HTML 마크업
>
```
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
  <link rel="stylesheet" href="styles/detail.css">
  <link href="https://fonts.googleapis.com/css2?family=Dancing+Script&display=swap" rel="stylesheet"> <!-- 구글 폰트 -->
  <link rel="stylesheet" href="https://use.fontawesome.com/releases/v5.15.4/css/all.css"
    integrity="sha384-DyZ88mC6Up2uqS4h/KRgHuoeGwBcD4Ng9SiP4dIRy0EXTlnuz47vAwmeGwVChigm" crossorigin="anonymous">
  <script defer src="js/detail.js"></script>
</head>
<body>
  <div id='container'>
    <nav>
      <h1 id="title">WeBucks</h1>
      <ul id='headerMenu'>
        <li>COFFEE</li>
        <li>MENU</li>
        <li>STORE</li>
        <li>WHAT'S NEW</li>
        <li><a href="#" href="login.html" id="loginLink">LOGIN</a></li>
      </ul>
    </nav>
    <header id="coffeeCategory">
      <h2 id="coffeeType">콜드 브루</h2>
      <p id="categoryPath">홈 > MENU > 음료 > 에스프레스> 화이트 초콜릿 모카</p>
    </header>
    <main>
      <img id="selectedCoffeeImg"
        src="https://image.istarbucks.co.kr/upload/store/skuimg/2021/03/[9200000003507]_20210322093414289.jpg"
        alt="coffee-image">
      <aside id="mainAsideInfo">
        <section id="coffeeNameAndDetailsBox">
          <header id="coffeeNameAndDetailHeader">
            <h3 id="coffeeName">화이트 초콜릿 모카</h3>
            <h4 id="coffeeEngName">White Chocolate Mocha</h4>
            <i id="heartIcon" class="far fa-heart"></i>
          </header>
          <p id="coffeeDetailsInfo">달콤하고 부드러운 화이트 초콜릿 시럽과 에스프레소를 스팀 밀크와 섞어 휘핑크림으로 마무리한 음료로 달콤한 강렬한 에스프레소가 부드럽게 어우러진 커피
          </p>
        </section>
        <section id="coffeeNutritionBox">
          <header id="coffeeNutritionHeader">
            <h4 id="coffeeNutritionInfo">제품 영양 정보</h4>
            <h4 id="coffeeNutritionUnit">Tall(톨) / 355ml(12 fl oz)</h4>
          </header>
          <article id="coffeeNutritionDetail">
            <ul class="nutritionPartList">
              <li class="nutritionContents">
                <p>1회 제공량 (kcal)</p>
                <p>345</p>
              </li>
              <li class="nutritionContents">
                <p>포화지방 (g)</p>
                <p>11</p>
              </li>
              <li class="nutritionContents">
                <p>단백질 (g)</p>
                <p>11</p>
              </li>
            </ul>
            <ul class="nutritionPartList">
              <li class="nutritionContents">
                <p>나트륨 (kcal)</p>
                <p>150</p>
              </li>
              <li class="nutritionContents">
                <p>당류 (g)</p>
                <p>35</p>
              </li>
              <li class="nutritionContents">
                <p>카페인 (mg)</p>
                <p>75</p>
              </li>
            </ul>
          </article>
          <div id="coffeeAllergyStatus">알레르기 유발 요인 : 우유</div>
        </section>
        <section id="coffeeReviewBox">
          <header id="coffeeReviewHeader">
            <h4 id="reviewTitle">리뷰</h4>
          </header>
          <ul id="reviewStatus">
            <li>
              <span>coffee_lover</span>
              <span>너무 맛있어요!</span>
            </li>
            <li>
              <span>CHOCO7</span>
              <span>오늘도 하이트 초콜릿 모카를 마시러 갑니다.</span>
            </li>
            <li>
              <span>legend_dev</span>
              <span>진짜 화이트 초콜릿 모카는 전설이다. 진짜 화이트 초콜릿 모카는 전설이다. 진짜 화이트 초콜릿 모카는 전설이다</span>
            </li>
          </ul>
          <form action="">
            <input type="text" name="commentBox" id="commentChatBox" placeholder="리뷰를 입력하세요">
          </form>
        </section>
      </aside>
    </main>
  </div>
  <footer>
    <ul id="companyMenu">
      <h5>COMPANY</h5>
      <li><a href="#">한눈에 보기</a></li>
      <li><a href="#">스타벅스 소개</a></li>
      <li><a href="#">스타벅스 사명</a></li>
      <li><a href="#">국내 뉴스룸</a></li>
      <li><a href="#">세계의 스타벅스</a></li>
      <li><a href="#">글로벌 뉴스룸</a></li>
    </ul>
    <ul id="corporateSales">
      <h5>CORPORATE SALES</h5>
      <li><a href="#">단체 및 기업 구매 안내</a></li>
    </ul>
    <ul id="partnershipMenu">
      <h5>PARTNERSHIP</h5>
      <li><a href="#">신규 입점 제의</a></li>
      <li><a href="#">협력 고객사 등록 신청</a></li>
    </ul>
    <ul id="onlineCommnityMenu">
      <h5>ONLINE COMMUNITY</h5>
      <li><a href="#">페이스북</a></li>
      <li><a href="#">트위터</a></li>
      <li><a href="#">유튜브</a></li>
      <li><a href="#">블로그</a></li>
      <li><a href="#">인스타그램</a></li>
    </ul>
    <ul id="recuitMenu">
      <h5>RECUIT</h5>
      <li><a href="#">채용 소개</a></li>
      <li><a href="#">채용 지원하기</a></li>
    </ul>
    <ul id="webuckshomeMenu">
      <h5>WEBUCKS</h5>
    </ul>
  </footer>
</body>
</html>
  ```

#### - 4차 CSS 작업
>
```
<style>  
* {
  box-sizing: border-box;
}
body{
  margin: 0;
  padding: 0;
}
#container {
  margin: auto;
  width: 75%;
  background-color: white;
}
nav {
  background-color: rgb(244, 244, 242);
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 20px;
  height: 70px;
}
#title{
  font-size: 23px;
  font-weight: bolder;
  font-family: 'Dancing Script', cursive;
}
#headerMenu{
  display: flex;
  justify-content: space-evenly;
  flex-basis: 300px;
  color: rgb(165, 165, 161);
}
#headerMenu li{ 
  padding-left: 20px;
  white-space: nowrap;
  list-style: none;
}
#loginLink {
  text-decoration: none;
  color:rgb(165, 165, 161); 
}
#headerMenu li:hover {
  cursor:pointer;
  color: #1B3C35;  
}
#header li:nth-child(5) #loginLink:hover{
  color: #1B3C35;
}
#coffeeCategory{
  position: relative;
  height: 95px;
}
#categoryPath{
  position: absolute;
  right:0;
  bottom:-5px;
  font-size:15px;
  color:rgb(165, 165, 161);
}
#coffeeType {
  position: absolute;
  font-size:30px;
  font-weight: 600;  
  top: 15px;
  margin: 0;
}
main {
  margin-bottom: 100px;
}
#categortyPath {
  color:rgb(165, 165, 161);
  bottom:10px;
}
#selectedCoffeeImg {
  float: left;
  width: 590px;
  height: 550px;
}
#mainAsideInfo {
  padding-left: 40px;
  display:flex;
  flex-flow: column nowrap;
}
#coffeeNameAndDetailHeader{
  position:relative;
  border-bottom: 2.5px solid black;
  height: 80px;
}
#coffeeName{
  position: absolute;
  top: 0;
  margin:0;
  font-size: 23px;
}
#coffeeEngName{
  position: absolute;
  bottom:28px;
  margin: 0;
  font-weight: 500;
  font-size: 14px;
}
#heartIcon{
  position: absolute;
  right: 0;
  top:20px;
  font-size: 25px;
  color:  rgb(165, 165, 161);;;
}
#coffeeDetailsInfo{
  padding: 10px 0;
  font-weight:600;
  font-size: 15px;
}
#coffeeNutritionHeader{
  display: flex;
  justify-content: space-between;
  align-items: center;
  font-size: 20px;
  padding: 10px 15px;
  border-top: 2px solid rgb(207, 207, 207);
  border-bottom: 2px solid rgb(207, 207, 207);
  font-weight: 300;
  height: 80px;
}
#coffeeNutritionInfo{
}
#coffeeNutritionUnit{
}
#coffeeNutritionDetail{
  text-align:left;
  display:flex;
  justify-content: flex-start; 
  padding-bottom: 30px;
}
.nutritionPartList{
  list-style: none;
  flex: 1 1 0;
  padding: 0 10px;
  font-weight: 600;
}
.nutritionPartList:nth-child(1){
  border-right: 2px dashed rgb(207, 207, 207);
}
.nutritionContents {
  display:flex;
  flex-flow: row nowrap;
  justify-content: space-between;
}
.nutritionContents  p {
  margin:6.5px;
}
#coffeeAllergyStatus{
  background-color: rgb(239,239,239);  
  height: 48px;
  display: flex;
  justify-content: flex-start;
  align-items: center;
  padding: 0 15px;
  font-weight: 600;
  font-size: 15px;
}
#coffeeReviewBox{
  padding-top: 10px;
}
#coffeeReviewHeader{
  padding-bottom: 10px;
  border-bottom: 2px solid rgb(207, 207, 207);
  height: 60px;
}
#reviewTitle{
  font-size: 20px;
  margin: 21px 0; 
}
#reviewStatus{
  padding: 0;
  width: 100%;
}
#reviewStatus li{
  list-style: none;
  white-space: nowrap;
  overflow: hidden;
}
#reviewStatus li span:nth-child(1){
  font-weight: 900;
}
#reviewStatus li span:nth-child(2){
  text-overflow:ellipsis;
}
#commentChatBox{
  background-color: rgb(239,239,239);  
  border: none;
  outline: none; 
  height: 40px;
  padding: 5px 10px;
  width: 100%;
}
h2, h3, h4 {
  display: inline-block;
}
footer {
  height: 300px;
  background-color:rgb(51, 51, 51);
  width: 100%;
  display: flex;
  justify-content: space-around;
  font-size: 16.5px;
}
footer ul{
  color: white;
  list-style: none;
  display: flex;
  flex-flow: column nowrap; 
}
footer ul li {
  padding: 5px 0;
}
footer ul li a{
  text-decoration: none;
  color: white;
}
</style>  
```

#### - 5차 JS  


  
리팩토링 과정 1차
 - input txt = submit과  button 태그의 차이점
 - form 태그의 역할, action과 input, button과의 관계는
  
   
- live coding
  
 
  레이아웃을 짤때 큰 단위부터 시작하자
  form 태그 안에 h1, p태그를 다 넣어도 괜찮다.
  위에서 부터 5개의 요소가있고 세로 정렬을 할거다.
  레이아웃 짤 때 백그라운드 컬러를 입히고 가시적으로 보면서 하는게 좋다.
  
  레이아웃은 한개만 정해서 지정해주는게 좋다.
  
  이벤트는 사용자가 인풋에 입력을햇는가 - 이벤트
  이메일에 @, 8글자 이상을 적었는가 - 함수 
  이벤트 핸들러함수에는 인자로 이벤트 자체를 받을 수 있다.
  이벤트란 이벤트가 담긴 수많은 정보가 나온다.
  
  
 disable 속성
  
 인풋창 두개가 있고 비밀번호 변화를 감지하고 로그인 버튼에 변화를 준다,
  
 ****돔에 변수 담고 바로 콘솔로그 찍어보기
  
  >접근자 메소드 차이 알기
  get은 
  노드리스트를 반환해주고
  쿼리셀렉터와의 차이
  

  
  
  
 >event.target.value
  target은 이벤트 대상이며
  
  ㅇ이메일 인풋에 담긴 값을 target으로 이벤트 대상을 받아오고 속성 중 value를 넣어 받아준다.  
  target과 event 자체 공부하기
  
  
  인풋 이메일과 패스워드 둘다 맞는지 확을 계속 해줘야 한다. 
  
  함수명 적을 때
  
  isVaildInput
  
  js에서는 스타일 시트 관련된 내용은 따로 빼자
  toggle 활용
  
 클래스명 붙여서 쓰면 버튼 안에있는 클래스에 접근 가능
  btn.active
  삼항 연산자는 결과가 값으로 평가될때 간단한게쓸때만
  
  - bottton up 방식은
  
  - 가장 밖에 감싸주는 wrapper 태그는 높이를 주지 않는게 좋다.
  
  - form태그 안에 있는 요소들이 form 태그의 높이를 결정해야한다.
  유지보수에 있어 좋다.

  - a태그와 location.href 차이 찾아보기
   
  - 테이블로 표현할 수 있는거 표현하기dl dt활용?!
  
 - let은 값이 꼭 바뀌는 것만
  
 - if문 안에 false, true인 것만 넣기 (hearfill)
  
  
  -버튼태그의 타입 어트리뷰트 submit 버튼 태그 폼태그 안엥 있으면 submit 제출된다.
  
  -나의 코드를 누군가가 본다는 의미로 쓰자
  
  
>- form 태그와 button 태그에 관해서  
   - `<form>` 태그의 action 속성은 폼 데이터(form data)를 서버로 보낼 때 해당 데이터가 도착할 URL을 명시합니다.  `<form action="URL">`
- `type` 버튼의 행동 방식. 가능한 값은 다음과 같습니다.
   - `submit`: 버튼이 서버로 양식 데이터를 제출합니다. 지정하지 않은 경우 기본값이며, 유효하지 않은 값일 때도 사용합니다.  
 - `<button>` 태그의 disabled 속성
     - `<button>` 태그의 disabled 속성은 해당 버튼이 비활성화됨을 명시합니다.
  
> - 주의, if 문 안에 함수를 조건으로 넣을 때는 함수를 실행해서 넘겨야한다.
- stiky 와 fixed 차이
  -  fixed : 일반적으로 `뷰포트`에 고정됨을 의미 합니다. 위치를 지정하면 사용자가 스크롤할 때 그대로 유지됩니다  
     - fixed 프로퍼티 선언 시 주의할 점은, block 요소의 width는 inline 요소와 같이 content에 맞게 변화되므로 적절한 width를 지정하여야 한다는 점 
     - 대신 뷰포트의 초기 컨테이닝 블록을 기준으로 삼아 배치합니다. 단, 요소의 조상 중 하나가 transform, perspective, filter 속성 중 어느 하나라도 none이 아니라면 (CSS Transforms 명세 참조) 뷰포트 대신 그 조상을 컨테이닝 블록으로 삼습니다. 
  - sticky : `position: sticky` 속성을 적용한 박스는 평소에 문서 안에서 position: static 상태와 같이 일반적인 흐름에 따르지만 스크롤 위치가 임계점에 이르면 position: fixed와 같이 박스를 화면에 고정할 수 있는 속성입
  - fixed는 `viewport`에 고정 되어 있는 것이고 스크롤을 내려도 원하는 위치에 고정되어있다. 그에 반해 `sticky`는 스크롤을 따라 움직이다 내가 정한 offset에 닿으면 그 순간부터 fixed처럼 고정이 된다. 최초에 relative 속성처럼 동작하다가 스크롤이 특정 지점에 도달하면 fixed 속성으로 동작하는 것이다.
