<!DOCTYPE html>
<html lang="ko">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>인터랙티브 메시지 애니메이션</title>
    <style>
        body {
            font-family: 'Arial', sans-serif;
            margin: 0;
            padding: 0;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            overflow: hidden;
            background-color: #87CEEB;
            transition: background-color 0.5s;
        }
        .message {
            background-color: #FFD700;
            border-radius: 10px;
            padding: 8px 12px;
            margin: 5px;
            display: none;
            width: auto;
            max-width: 80%;
            word-wrap: break-word;
            position: absolute;
        }
        .input-area {
            position: fixed;
            bottom: 0;
            width: 100%;
            background-color: #fff;
            padding: 10px;
            box-sizing: border-box;
        }
        input[type="text"] {
            width: 75%;
            padding: 8px;
            border: 2px solid #ddd;
            border-radius: 5px;
            margin-right: 5px;
        }
        button {
            width: 20%;
            background-color: #87CEEB;
            border: none;
            padding: 10px;
            border-radius: 5px;
            color: white;
        }
        #heart {
            display: none;
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            font-size: 50px;
            color: #FF1493;
        }
    </style>
</head>
<body>
<div id="heart">❤️</div>
<div class="container">
    <div class="message">엄마</div>
    <div class="message">아빠</div>
    <div class="message">키워 주셔서</div>
    <div class="message">감사드립니다</div>
    <div class="message">벌써 성인이 된</div>
    <div class="message">김현지와</div>
    <div class="message">빵뗴</div>
    <div class="message">드림</div>
    <div class="message">내일 봐</div>
    <div class="message">그리고</div>
    <div class="message">나</div>
    <div class="message">밀면 먹고 싶어</div>
</div>
<div class="input-area">
    <input type="text" placeholder="메시지 입력...">
    <button>전송</button>
</div>

<script>
    const messages = document.querySelectorAll('.message');
    let currentMessage = 0;
    const body = document.body;
    const heart = document.getElementById('heart');

    function showNextMessage() {
        if (currentMessage < messages.length) {
            messages[currentMessage].style.display = 'block';
            currentMessage++;
        } else {
            messages.forEach(msg => msg.style.display = 'none');
            body.style.backgroundColor = '#FFB6C1';
            heart.style.display = 'block';
        }
    }

    document.body.addEventListener('click', showNextMessage);
</script>
</body>
</html>
