<html lang="ko">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>메시지 순차적 표시</title>
    <style>
        body {
            background-color: #87CEEB;
            font-family: 'Arial', sans-serif;
            margin: 0;
            padding: 0;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            flex-direction: column;
            overflow: hidden;
            transition: background-color 0.5s;
        }
        .messages {
            flex-grow: 1;
            display: flex;
            flex-direction: column-reverse;
            justify-content: flex-end;
            align-items: center;
            width: 100%;
            overflow: auto;
            padding: 10px;
        }
        .message {
            background-color: #FFD700;
            border-radius: 10px;
            padding: 8px 12px;
            margin: 5px;
            display: none;
            max-width: 80%;
            word-wrap: break-word;
        }
        .input-area {
            width: 100%;
            padding: 10px;
            box-sizing: border-box;
            background-color: #fff;
            display: flex;
            justify-content: center;
            align-items: center;
        }
        input[type="text"] {
            flex-grow: 1;
            padding: 10px;
            border: 2px solid #ddd;
            border-radius: 5px;
            margin-right: 10px;
        }
        button {
            padding: 10px 20px;
            background-color: #87CEEB;
            border: none;
            color: white;
            border-radius: 5px;
            font-size: 16px;
        }
        #heart {
            display: none;
            font-size: 50px;
            color: #FF1493;
        }
    </style>
</head>
<body>
<div class="messages" id="message-container">
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
<div id="heart">❤️</div>

<script>
    const messages = document.querySelectorAll('.message');
    let currentMessage = 0;
    const body = document.body;
    const heart = document.getElementById('heart');
    const container = document.getElementById('message-container');

    function showNextMessage() {
        if (currentMessage < messages.length) {
            messages[currentMessage].style.display = 'block';
            currentMessage++;
        } else {
            body.style.backgroundColor = '#FFB6C1';
            container.style.display = 'none';
            heart.style.display = 'block';
        }
    }

    document.body.addEventListener('click', showNextMessage);
</script>
</body>
</html>
