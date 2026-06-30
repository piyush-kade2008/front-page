# front-page
login page
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>PIYUSH MANOHARRAO KADE</title>
    <link href="https://fonts.googleapis.com/css2?family=Plus+Jakarta+Sans:wght@400;500;600;700&display=swap" rel="stylesheet">
    <style>
        * { box-sizing: border-box; margin: 0; padding: 0; font-family: 'Plus Jakarta Sans', sans-serif; }
        body {
            background: radial-gradient(circle at 10% 20%, rgba(99, 102, 241, 0.15), transparent 40%),
                        radial-gradient(circle at 90% 80%, rgba(168, 85, 247, 0.15), transparent 40%), #0b0f19;
            color: #fff; display: flex; align-items: center; justify-content: center; min-height: 100vh;
        }
        .card {
            background: rgba(255, 255, 255, 0.03); backdrop-filter: blur(16px); -webkit-backdrop-filter: blur(16px);
            border: 1px solid rgba(255, 255, 255, 0.08); border-radius: 24px; padding: 40px; width: 100%; max-width: 400px;
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.3); text-align: center; margin: 20px;
        }
        .card h2 { font-size: 26px; font-weight: 700; margin-bottom: 8px; background: linear-gradient(135deg, #fff, #a5b4fc); -webkit-background-clip: text; -webkit-text-fill-color: transparent; }
        .card p { color: #9ca3af; font-size: 14px; margin-bottom: 24px; }
        .input-group { position: relative; margin-bottom: 20px; text-align: left; }
        .input-group label { display: block; font-size: 13.5px; color: #9ca3af; margin-bottom: 6px; font-weight: 500; }
        .input-group input {
            width: 100%; padding: 12px 16px; background: rgba(255, 255, 255, 0.04);
            border: 1px solid rgba(255, 255, 255, 0.08); border-radius: 12px; color: #fff; font-size: 14px; outline: none; transition: all 0.2s;
        }
        .input-group input:focus { border-color: #6366f1; box-shadow: 0 0 0 3px rgba(99, 102, 241, 0.2); }
        .toggle-pwd { position: absolute; right: 14px; top: 38px; cursor: pointer; color: #9ca3af; font-size: 14px; }
        .options { display: flex; justify-content: space-between; align-items: center; margin-bottom: 24px; font-size: 13px; color: #9ca3af; }
        .options label { display: flex; align-items: center; gap: 6px; cursor: pointer; }
        .options a { color: #6366f1; text-decoration: none; font-weight: 500; }
        .btn {
            width: 100%; padding: 14px; background: linear-gradient(135deg, #6366f1, #a855f7); border: none;
            border-radius: 12px; color: #fff; font-size: 15px; font-weight: 600; cursor: pointer; transition: 0.2s;
        }
        .btn:hover { opacity: 0.9; transform: translateY(-1px); }
        .divider { display: flex; align-items: center; margin: 20px 0; color: rgba(255,255,255,0.15); font-size: 11px; text-transform: uppercase; letter-spacing: 0.5px; }
        .divider::before, .divider::after { content: ''; flex: 1; border-bottom: 1px solid rgba(255,255,255,0.08); }
        .divider:not(:empty)::before { margin-right: 12px; }
        .divider:not(:empty)::after { margin-left: 12px; }
        .socials { display: flex; gap: 12px; }
        .social-btn {
            flex: 1; padding: 12px; background: rgba(255,255,255,0.02); border: 1px solid rgba(255,255,255,0.08);
            border-radius: 12px; color: #fff; font-size: 14px; cursor: pointer; transition: 0.2s; display: flex; align-items: center; justify-content: center; gap: 8px;
        }
        .social-btn:hover { background: rgba(255,255,255,0.06); }
        .footer { font-size: 13.5px; margin-top: 24px; color: #9ca3af; }
        .footer a { color: #6366f1; text-decoration: none; font-weight: 600; }
        .alert { background: rgba(239, 68, 68, 0.1); border: 1px solid rgba(239, 68, 68, 0.2); color: #fca5a5; padding: 10px 14px; border-radius: 10px; font-size: 13px; margin-bottom: 16px; display: none; text-align: left; }
    </style>
</head>
<body>
    <div class="card">
        <h2>PIYUSH MANOHARRAO KADE</h2>
        <p>Enter your details to access your account</p>
        <div class="alert" id="alert"></div>
        <form id="loginForm" onsubmit="handleSubmit(event)">
            <div class="input-group">
                <label>Email Address</label>
                <input type="email" id="email" placeholder="name@example.com" required>
            </div>
            <div class="input-group">
                <label>Password</label>
                <input type="password" id="password" placeholder="••••••••" required>
                <span class="toggle-pwd" onclick="togglePassword()">👁️</span>
            </div>
            <div class="options">
                <label><input type="checkbox"> Remember me</label>
                <a href="#">Forgot password?</a>
            </div>
            <button type="submit" class="btn">Sign In</button>
        </form>
        <div class="divider">Or continue with</div>
        <div class="socials">
            <button class="social-btn">🌐 Google</button>
            <button class="social-btn">🍎 Apple</button>
        </div>
        <div class="footer">Don't have an account? <a href="#">Sign up</a></div>
    </div>
    <script>
        function togglePassword() {
            const pwd = document.getElementById('password');
            pwd.type = pwd.type === 'password' ? 'text' : 'password';
        }
        function handleSubmit(e) {
            e.preventDefault();
            const email = document.getElementById('email').value;
            const pass = document.getElementById('password').value;
            const alert = document.getElementById('alert');
            if (pass.length < 6) {
                alert.style.color = "#fca5a5"; alert.style.background = "rgba(239, 68, 68, 0.1)"; alert.style.borderColor = "rgba(239, 68, 68, 0.2)";
                alert.textContent = "Password must be at least 6 characters."; alert.style.display = "block";
            } else {
                alert.style.color = "#10b981"; alert.style.background = "rgba(16, 185, 129, 0.1)"; alert.style.borderColor = "rgba(16, 185, 129, 0.2)";
                alert.textContent = `Success! Logging in ${email}...`; alert.style.display = "block";
            }
        }
    </script>
</body>
</html>
