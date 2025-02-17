<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>图片与按钮页面</title>
    <style>
        /* 全局样式重置 */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        /* 页面主体样式 */
        body {
            padding: 20px;
            padding-bottom: 80px; /* 预留底部按钮空间，防止遮挡 */
            text-align: center; /* 让内容居中 */
        }

        /* 图片容器样式 */
        .image-container {
            width: 100%;
            margin-bottom: 20px; /* 图片与按钮的间隔 */
        }

        /* 主图片样式 */
        .main-image {
            width: 100%; /* 让图片自适应容器宽度 */
            height: 300px; /* 固定高度 */
            object-fit: cover; /* 保持图片比例 */
            border-radius: 10px; /* 让图片四角圆润 */
        }

        /* 按钮容器样式 */
        .buttons-container {
            display: flex;
            flex-wrap: wrap; /* 允许按钮换行 */
            justify-content: center; /* 让按钮居中 */
            gap: 20px; /* 按钮之间的间距 */
        }

        /* 按钮行样式 */
        .button-row {
            display: flex;
            justify-content: center; /* 让按钮在一行中居中 */
            gap: 50px; /* 按钮之间的间距 */
            width: 100%; /* 让按钮行宽度占满 */
        }

        /* 按钮样式 */
        .button {
            width: 220px; /* 统一按钮宽度 */
            padding: 15px; /* 设定按钮的内边距 */
            background-color: #4CAF50; /* 绿色背景 */
            color: white; /* 按钮文字颜色 */
            border: none; /* 去掉边框 */
            border-radius: 6px; /* 让按钮圆润 */
            cursor: pointer; /* 鼠标悬停时显示手型指针 */
            font-size: 16px; /* 设置按钮文本大小 */
            text-align: center; /* 让按钮文字居中 */
        }

        /* 鼠标悬停时按钮变色 */
        .button:hover {
            background-color: #45a049;
        }

        /* 底部导航栏样式 */
        .bottom-nav {
            position: fixed; /* 让底部导航始终固定 */
            bottom: 0;
            left: 0;
            right: 0;
            background-color: #f1f1f1; /* 灰色背景 */
            padding: 15px;
            display: flex;
            justify-content: space-around; /* 让两个按钮均匀分布 */
        }

        /* 底部导航按钮样式 */
        .nav-button {
            padding: 10px 30px; /* 设定内边距 */
            background-color: #555; /* 深色背景 */
            color: white; /* 文字颜色 */
            border: none;
            border-radius: 5px; /* 圆角 */
            cursor: pointer; /* 鼠标指针 */
        }
    </style>
</head>
<body>

    <!-- 图片区域 -->
    <div class="image-container">
        <img src="C:\Users\28768\Desktop\TH木线二维码\TH商标.jpg" class="main-image">
    </div>

    <!-- 按钮区域 -->
    <div id="buttons-container" class="buttons-container">
        <!-- 初始状态下，主页面按钮会动态加载进来 -->
    </div>

    <!-- 底部导航 -->
    <div class="bottom-nav">
        <button class="nav-button" onclick="loadHomePage()">首页</button>
        <button class="nav-button" onclick="loadHomePage()">返回</button>
    </div>

    <script>
        /**
         * 加载主页面（默认显示4个按钮）
         */
         function loadHomePage() {
    let buttonsContainer = document.getElementById("buttons-container");
    let mainImage = document.querySelector(".main-image"); // 获取主图片元素

    // 重新填充按钮内容
    buttonsContainer.innerHTML = `
        <div class="button-row">
            <button class="button" onclick="showTHSeries()">TH石膏线系列</button>
        </div>
        <div class="button-row">
            <button class="button" onclick="showTCSeries()">TC实木涂油线系列</button>
        </div>
        <div class="button-row">
            <button class="button" onclick="showTFSeries()">TF石膏线 不涂底</button>
        </div>
        <div class="button-row">
            <button class="button" onclick="showBrazilSeries()">巴西白木木线系列</button>
        </div>
    `;

    // 恢复首页的默认图片
    mainImage.src = "C:\\Users\\28768\\Desktop\\TH木线二维码\\TH商标.jpg"; // 修改为首页对应的图片路径
}


       /**
 * 点击 "TH石膏线系列" 按钮，显示6个按钮，每行2个
 */
function showTHSeries() {
    let buttonsContainer = document.getElementById("buttons-container");
    let mainImage = document.querySelector(".main-image");

    // 重新填充按钮内容，变成6个按钮，每行2个
    buttonsContainer.innerHTML = `
        <div class="button-row">
            <button class="button">石膏线 A</button>
            <button class="button">石膏线 B</button>
        </div>
        <div class="button-row">
            <button class="button">石膏线 C</button>
            <button class="button">石膏线 D</button>
        </div>
        <div class="button-row">
            <button class="button">石膏线 E</button>
            <button class="button">石膏线 F</button>
        </div>
    `;

    // 更新图片
    mainImage.src = "TH实木石膏线.jpg"; // 修改为对应的图片路径
}


        /**
         * 点击 "TC实木涂油线系列" 按钮，显示8个按钮，每行2个
         */
        function showTCSeries() {
            let buttonsContainer = document.getElementById("buttons-container");

            // 重新填充按钮内容，变成8个按钮，每行2个
            buttonsContainer.innerHTML = `
                <div class="button-row">
                    <button class="button">TC系列 1</button>
                    <button class="button">TC系列 2</button>
                </div>
                <div class="button-row">
                    <button class="button">TC系列 3</button>
                    <button class="button">TC系列 4</button>
                </div>
                <div class="button-row">
                    <button class="button">TC系列 5</button>
                    <button class="button">TC系列 6</button>
                </div>
                <div class="button-row">
                    <button class="button">TC系列 7</button>
                    <button class="button">TC系列 8</button>
                </div>
            `;
        }

        /**
         * 点击 "TF石膏线 不涂底" 按钮，显示6个按钮，每行2个
         */
        function showTFSeries() {
            let buttonsContainer = document.getElementById("buttons-container");

            // 重新填充按钮内容，变成6个按钮，每行2个
            buttonsContainer.innerHTML = `
                <div class="button-row">
                    <button class="button">TF系列 1</button>
                    <button class="button">TF系列 2</button>
                </div>
                <div class="button-row">
                    <button class="button">TF系列 3</button>
                    <button class="button">TF系列 4</button>
                </div>
                <div class="button-row">
                    <button class="button">TF系列 5</button>
                    <button class="button">TF系列 6</button>
                </div>
            `;
        }

        /**
         * 点击 "巴西白木木线系列" 按钮，显示5个按钮，每行2个
         */
        function showBrazilSeries() {
            let buttonsContainer = document.getElementById("buttons-container");

            // 重新填充按钮内容，变成5个按钮，每行2个
            buttonsContainer.innerHTML = `
                <div class="button-row">
                    <button class="button">巴西系列 1</button>
                    <button class="button">巴西系列 2</button>
                </div>
                <div class="button-row">
                    <button class="button">巴西系列 3</button>
                    <button class="button">巴西系列 4</button>
                </div>
                <div class="button-row">
                    <button class="button">巴西系列 5</button>
                </div>
            `;
        }

        // 确保页面加载时，默认显示主页面按钮
        window.onload = loadHomePage;
    </script>

</body>
</html>
