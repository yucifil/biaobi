# biaobi
<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>表白小页面</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f9f9f9;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
        }
        .container {
            text-align: center;
            background-color: #fff;
            padding: 20px;
            border-radius: 10px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
        }
        h1 {
            font-size: 24px;
            margin-bottom: 20px;
        }
        button {
            padding: 10px 20px;
            font-size: 16px;
            margin: 10px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            transition: background-color 0.3s;
        }
        #yesButton {
            background-color: #4CAF50;
            color: white;
        }
        #noButton {
            background-color: #f44336;
            color: white;
        }
        #yesButton:hover {
            background-color: #45a049;
        }
        #noButton:hover {
            background-color: #e53935;
        }
        #message {
            margin-top: 20px;
            font-size: 20px;
            font-weight: bold;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>我喜欢你！你的选择是？</h1>
        <button id="yesButton">1. 我也喜欢你</button>
        <button id="noButton">2. 我不喜欢你</button>
        <div id="message"></div>
    </div>

    <script>
        // 获取元素
        const yesButton = document.getElementById('yesButton');
        const noButton = document.getElementById('noButton');
        const message = document.getElementById('message');

        // 定义颜色数组
        const colors = ['#FF0000', '#FF7F00', '#FFFF00', '#00FF00', '#0000FF', '#4B0082', '#9400D3'];

        // 动态表白逻辑
        let intervalId;

        function startConfession() {
            let index = 0;
            intervalId = setInterval(() => {
                message.style.color = colors[index];
                message.textContent = '我喜欢你！';
                index = (index + 1) % colors.length;
            }, 500);
        }

        // 绑定按钮事件
        yesButton.addEventListener('click', () => {
            message.textContent = '我也喜欢你！';
            clearInterval(intervalId); // 停止之前的动态效果
            startConfession(); // 开始动态表白
        });

        noButton.addEventListener('click', () => {
            message.textContent = '好吧，我退出……';
            clearInterval(intervalId); // 停止动态效果
            message.style.color = '#000'; // 重置颜色
        });
    </script>
</body>
</html>
