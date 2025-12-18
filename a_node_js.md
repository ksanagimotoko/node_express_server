## nodejs 설치

<br>
<br>
<br>
<br>
<br>

### npm init
\> npm init -y
<br>
<br>
<br>
<br>
<br>

### express package 설치
\> npm install express

<br>
<br>
<br>
<br>
<br>

### app.js
```javascript
const express = require('express');
const path = require('path');

const app = express();
const PORT = 3000;

// 정적 파일 제공 (public 폴더)
app.use(express.static(path.join(__dirname, 'public')));

// 루트 경로
app.get('/', (req, res) => {
    res.sendFile(path.join(__dirname, 'public', 'index.html'));
});

// 서버 시작
app.listen(PORT, () => {
    console.log(`서버가 http://localhost:${PORT} 에서 실행 중입니다.`);
    console.log('hello_express 출력을 확인하세요!');
});


```

<br>
<br>
<br>
<br>
<br>

### public/index.html
```html
<!DOCTYPE html>
<html lang="ko">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Hello Express</title>
    <link rel="stylesheet" href="/style.css">
</head>
<body>
    <div class="container">
        <h1 id="greeting">hello_express</h1>
    </div>
    <script src="/script.js"></script>
</body>
</html>




```
<br>
<br>
<br>
<br>
<br>

### public/script.js
```javascript
// 페이지 로드 시 실행
document.addEventListener('DOMContentLoaded', () => {
    const greeting = document.getElementById('greeting');
    
    // 콘솔에 출력
    console.log('hello_express');
    
    // 추가 효과 (선택사항)
    greeting.addEventListener('click', () => {
        greeting.style.transform = 'scale(1.1)';
        setTimeout(() => {
            greeting.style.transform = 'scale(1)';
        }, 200);
    });
    
    // CSS transition 추가
    greeting.style.transition = 'transform 0.2s ease';
});




```
<br>
<br>
<br>
<br>
<br>

### public/style.css
```css
// 페이지 로드 시 실행
document.addEventListener('DOMContentLoaded', () => {
    const greeting = document.getElementById('greeting');
    
    // 콘솔에 출력
    console.log('hello_express');
    
    // 추가 효과 (선택사항)
    greeting.addEventListener('click', () => {
        greeting.style.transform = 'scale(1.1)';
        setTimeout(() => {
            greeting.style.transform = 'scale(1)';
        }, 200);
    });
    
    // CSS transition 추가
    greeting.style.transition = 'transform 0.2s ease';
});

```




