### public/contact.html
```html
<!DOCTYPE html>
<html lang="ko">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Contact</title>
    <link rel="stylesheet" href="/style.css">
    <style>
        .contact-container {
            max-width: 600px;
            width: 100%;
        }
        .contact-info {
            margin-top: 2rem;
        }
        .email {
            font-size: 1.5rem;
            color: #667eea;
            margin-top: 1rem;
            word-break: break-all;
        }
        .email a {
            color: #667eea;
            text-decoration: none;
            transition: color 0.3s;
        }
        .email a:hover {
            color: #764ba2;
            text-decoration: underline;
        }
        .back-link {
            margin-top: 2rem;
        }
        .back-link a {
            color: #667eea;
            text-decoration: none;
            font-size: 1rem;
            transition: color 0.3s;
        }
        .back-link a:hover {
            color: #764ba2;
            text-decoration: underline;
        }
    </style>
</head>
<body>
    <div class="container contact-container">
        <h1>Contact</h1>
        <div class="contact-info">
            <p>이메일 주소:</p>
            <div class="email">
                <a href="mailto:abc@gmail.com">abc@gmail.com</a>
            </div>
        </div>
        <div class="back-link">
            <a href="/">← 홈으로 돌아가기</a>
        </div>
    </div>
</body>
</html>

```

<br>
<br>
<br>
<br>
<br>

### app.js 수정하기 

수정후 웹 브라우저에서 localhost:3000/contact 접속해보기 

```javascript
// 루트 경로
app.get('/', (req, res) => {
    res.sendFile(path.join(__dirname, 'public', 'index.html'));
});

// Contact 페이지
app.get('/contact', (req, res) => {
    res.sendFile(path.join(__dirname, 'public', 'contact.html'));
});


```
