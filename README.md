# 데이터베이스 생성 실습

목적) mysql과 postman을 활용한 데이터베이스 생성 과정 실습

1) DB 생성 과정
 
![db1](https://github.com/user-attachments/assets/ad3e4f37-8ad4-4dda-85b3-85f9d2346460)

1- DB 이름 설정 및 저장

![스크린샷 2025-05-17 231255](https://github.com/user-attachments/assets/f7f7d0f6-eee4-41a7-9d74-519633d1963e)

2- 이름 저장 후 테이블 생성

![스크린샷 2025-05-17 232743](https://github.com/user-attachments/assets/5c78d35f-4401-4ebd-b7fb-1c8e59ca91ce)

2) sever.js 코드 짜기

const express = require('express');
const bodyParser = require('body-parser');
const mysql = require('mysql2');

const app = express();

// JSON 데이터 파싱을 위한 설정 추가
app.use(express.json());
app.use(express.urlencoded({ extended: true }));

const db = mysql.createConnection({
    host: 'localhost',
    user: 'root',
    password: '1234',
    database: 'yoodain'
});

db.connect(err => {
    if (err) throw err;
    console.log('MySQL Connected...');
});

app.post('/db', (req, res) => {
    const { username, password } = req.body;

    if (!username || !password) {
        return res.status(400).send('Username and password are required!');
    }

    const sql = 'INSERT INTO users (username, password) VALUES (?, ?)';
    db.query(sql, [username, password], (err, result) => {
        if (err) throw err;
        res.send('User registered successfully!');
    });
});

app.get('/users', (req, res) => {
    const sql = 'SELECT * FROM users';
    db.query(sql, (err, result) => {
        if (err) throw err;
        res.json(result);
    });
});

app.get('/users/:username', (req, res) => {
    const { username } = req.params;
    const sql = 'SELECT * FROM users WHERE username = ?';
    db.query(sql, [username], (err, result) => {
        if (err) throw err;

        if (result.length === 0) {
            return res.status(404).send('User not found!');
        }

        res.json(result[0]); // JSON 형식으로 사용자 데이터 반환
    });
});

app.get('/db', (req, res) => {
    const sql = 'SELECT username, password FROM users';
    db.query(sql, (err, result) => {
        if (err) {
            console.error('Database error:', err);
            return res.status(500).send('Database error');
        }

        res.json(result); // JSON 형식으로 데이터 반환
    });
});



app.listen(3000, () => console.log('Server running on port 3000'));

