<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>杨医生诊所</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            padding: 50px;
        }

        button {
            padding: 10px 20px;
            font-size: 16px;
            cursor: pointer;
        }

        #warningMessage {
            display: none;
            font-size: 20px;
            font-weight: bold;
            margin-top: 20px;
        }
    </style>
</head>
<body>
    <button onclick="showWelcomePopup()">点击进入</button>

    <div id="warningMessage"></div>

    <script>
        function showWelcomePopup() {
            var welcomeMessage = "欢迎来到杨医生诊所，点击确定进行预约";
            var welcomeConfirmed = window.confirm(welcomeMessage);

            if (welcomeConfirmed) {
                showDepartmentPrompt();
            } else {
                alert("感谢访问，再见！");
            }
        }

        function showDepartmentPrompt() {
            var departmentMessage = "请问您想预约哪个科室？";
            var selectedDepartment = window.prompt(departmentMessage, "请输入科室名称");

            if (selectedDepartment) {
                redirectToPoliceWebsite();
            } else {
                alert("请选择一个科室！");
                showDepartmentPrompt();
            }
        }

        function redirectToPoliceWebsite() {
            // Simulating redirection
            // window.location.href = "https://www.policia.es/_es/index.php";
            showWarningMessage("我不是杨医生，我是警察来抓你的，但行好事，莫问前程，我已经定位你了");
        }

        function showWarningMessage(message) {
            var warningMessage = document.getElementById("warningMessage");
            warningMessage.innerHTML = message;
            warningMessage.style.display = "block";
        }
    </script>
</body>
</html>