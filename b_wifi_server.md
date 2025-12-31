### 동일한 wifi안에서 제공하기 
#### app.js 수정하기

```javascript
const express = require('express');
const path = require('path');
const os = require('os');

const app = express();
const PORT = 3000;

// 정적 파일 제공 (public 폴더)
app.use(express.static(path.join(__dirname, 'public')));

// 루트 경로
app.get('/', (req, res) => {
    res.sendFile(path.join(__dirname, 'public', 'index.html'));
});

// 로컬 IP 주소 가져오기
function getLocalIPAddress() {
    const interfaces = os.networkInterfaces();
    for (const name of Object.keys(interfaces)) {
        for (const iface of interfaces[name]) {
            // IPv4이고 내부 주소가 아닌 경우
            if (iface.family === 'IPv4' && !iface.internal) {
                return iface.address;
            }
        }
    }
    return 'localhost';
}

// 서버 시작 (0.0.0.0으로 바인딩하여 모든 네트워크 인터페이스에서 접근 가능)
app.listen(PORT, '0.0.0.0', () => {
    const localIP = getLocalIPAddress();
    console.log(`서버가 실행 중입니다!`);
    console.log(`로컬: http://localhost:${PORT}`);
    console.log(`네트워크: http://${localIP}:${PORT}`);
    console.log('같은 와이파이의 다른 기기에서도 접근 가능합니다.');
    console.log('hello_express 출력을 확인하세요!');
});





```
