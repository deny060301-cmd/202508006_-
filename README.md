cd projects
cd 202508006
cd weeks

vi add.js
아래 내용을 삽입

---
const express = require("express");
const path = require("path");
const app = express();
const PORT = 3000;
app.use(express.urlencoded({ extended: true }));
app.use(express.static(path.join(__dirname, "public")));
app.get("/time", (req, res) => {
 res.send(new Date().toLocaleString("ko-KR"));
});
app.listen(PORT, () => {
 console.log(`서버 실행 중: http://localhost:${PORT}`);
});
---

:wq

mkdir public
생성

vi index.html
아래 내용 삽입

---
<!DOCTYPE html>
<html>
<head>
 <meta charset="UTF-8">
 <title>손현우 개인 프로필</title>
 <link rel="stylesheet" href="style.css">
</head>
<body>
 <h1>손현우</h1>
 <h2>개인 프로필</h2>
 <p>안녕하세요. 손현우입니다.</p>
 <p>IT 관련 공부를 하고 있습니다.</p>
 <h3>전공</h3>
 <p>정보통신공학</p>
 <h3>관심 분야</h3>
 <p>게임</p>
 <p>운동</p>
 <h3>학습 내용</h3>
 <p>HTML, JavaScript, Node.js, Express</p>
 <h3>서버 기능</h3>
 <p><a href="/time">현재 시간 확인</a></p>
</body>
</html>
---

:wq

그 후
vi style.css
아래 내용 삽입

---
body {
 width: 700px;
 margin: 50px auto;
 font-family: Arial, sans-serif;
}
h1 {
 text-align: center;
}
h2, h3 {
 margin-top: 25px;
}
p {
 font-size: 16px;
}
---

:wq

뒤로 가기
cd ..

node app.js
실행

크롬에

http://localhost:3000

입력 시 결과 출력

