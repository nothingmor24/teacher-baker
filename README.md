<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>تسجيل الدخول | teacher Baker</title>
    <style>
        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }

        body {
            min-height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            background: linear-gradient(135deg, #4158D0 0%, #C850C0 46%, #FFCC70 100%);
            padding: 20px;
        }

        .card {
            background: rgba(255, 255, 255, 0.95);
            padding: 40px 30px;
            border-radius: 20px;
            box-shadow: 0 15px 35px rgba(0, 0, 0, 0.2);
            width: 100%;
            max-width: 420px;
            text-align: center;
            backdrop-filter: blur(10px);
        }

        h2 {
            margin-bottom: 20px;
            color: #333;
        }

        .form-group {
            margin-bottom: 15px;
            text-align: right;
        }

        label {
            display: block;
            margin-bottom: 5px;
            color: #666;
            font-size: 14px;
        }

        input {
            width: 100%;
            padding: 12px 15px;
            border: 2px solid #e0e0e0;
            border-radius: 10px;
            font-size: 15px;
            outline: none;
            transition: 0.3s;
        }

        input:focus {
            border-color: #C850C0;
        }

        button {
            width: 100%;
            padding: 12px;
            background: linear-gradient(135deg, #4158D0, #C850C0);
            border: none;
            color: white;
            font-size: 16px;
            font-weight: bold;
            border-radius: 10px;
            cursor: pointer;
            transition: 0.3s;
            margin-top: 10px;
        }

        button:hover {
            opacity: 0.9;
            transform: translateY(-2px);
        }

        .toggle-btn {
            background: none;
            border: none;
            color: #4158D0;
            margin-top: 15px;
            font-size: 14px;
            cursor: pointer;
            text-decoration: underline;
        }

        /* صفحة النتيجة */
        .result-screen {
            display: none;
            color: white;
            text-align: center;
            animation: fadeIn 0.8s ease-in-out;
        }

        .result-screen h1 {
            font-size: 42px;
            margin-bottom: 15px;
            text-shadow: 2px 4px 10px rgba(0,0,0,0.3);
        }

        .result-screen p {
            font-size: 20px;
            letter-spacing: 1px;
            background: rgba(255, 255, 255, 0.2);
            padding: 15px 25px;
            border-radius: 50px;
            display: inline-block;
            backdrop-filter: blur(5px);
        }

        @keyframes fadeIn {
            from { opacity: 0; transform: scale(0.9); }
            to { opacity: 1; transform: scale(1); }
        }
    </style>
</head>
<body>

    <!-- نموذج التسجيل / إنشاء حساب -->
    <div class="card" id="authCard">
        <h2 id="formTitle">تسجيل الدخول</h2>
        <form id="authForm" onsubmit="handleSubmit(event)">
            <div class="form-group">
                <label>البريد الإلكتروني</label>
                <input type="email" id="email" placeholder="example@mail.com" required>
            </div>
            <div class="form-group">
                <label>كلمة السر</label>
                <input type="password" id="password" placeholder="••••••••" required>
            </div>
            <button type="submit" id="submitBtn">دخول</button>
        </form>
        <button class="toggle-btn" onclick="toggleMode()" id="toggleBtn">ما عندك حساب؟ أنشئ حساب جديد</button>
    </div>

    <!-- صفحة النتيجة عند اكتمال التسجيل -->
    <div class="result-screen" id="resultScreen">
        <h1>Welcome Back!</h1>
        <p>Prepared with quality by <strong>teacher Baker</strong></p>
    </div>

    <script>
        let isSignUp = false;

        function toggleMode() {
            isSignUp = !isSignUp;
            const title = document.getElementById('formTitle');
            const submitBtn = document.getElementById('submitBtn');
            const toggleBtn = document.getElementById('toggleBtn');

            if (isSignUp) {
                title.innerText = 'حساب جديد';
                submitBtn.innerText = 'إنشاء حساب وتسجيل';
                toggleBtn.innerText = 'عندك حساب بالفعل؟ سجل دخولك';
            } else {
                title.innerText = 'تسجيل الدخول';
                submitBtn.innerText = 'دخول';
                toggleBtn.innerText = 'ما عندك حساب؟ أنشئ حساب جديد';
            }
        }

        function handleSubmit(e) {
            e.preventDefault();
            // إخفاء كرت التسجيل وإظهار صفحة النتيجة
            document.getElementById('authCard').style.display = 'none';
            document.getElementById('resultScreen').style.display = 'block';
        }
    </script>

</body>
</html>
