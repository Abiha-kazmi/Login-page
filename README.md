#<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1" />
<title>Login Form</title>
<style>
  @import url('https://fonts.googleapis.com/css2?family=Montserrat:wght@400;600&display=swap');

  * {
    box-sizing: border-box;
  }

  body {
    height: 100vh;
    margin: 0;
    font-family: 'Montserrat', sans-serif;
    background: linear-gradient(135deg, #667eea, #764ba2);
    display: flex;
    justify-content: center;
    align-items: center;
    color: #fff;
  }

  .login-container {
    background: rgba(255, 255, 255, 0.1);
    padding: 40px 50px;
    border-radius: 12px;
    width: 320px;
    box-shadow: 0 8px 32px rgba(0,0,0,0.3);
    backdrop-filter: blur(10px);
  }

  .login-container h2 {
    margin: 0 0 25px;
    font-weight: 600;
    font-size: 1.8rem;
    text-align: center;
  }

  .form-group {
    margin-bottom: 25px;
  }

  label {
    display: block;
    margin-bottom: 8px;
    font-weight: 600;
  }

  input[type="text"],
  input[type="password"] {
    width: 100%;
    padding: 12px 15px;
    border-radius: 8px;
    border: none;
    font-size: 1rem;
    outline: none;
    transition: box-shadow 0.3s ease;
  }

  input[type="text"]:focus,
  input[type="password"]:focus {
    box-shadow: 0 0 10px 3px #a890f0;
  }

  .btn-login {
    width: 100%;
    background: #6b5bff;
    color: #fff;
    padding: 14px;
    font-weight: 700;
    font-size: 1rem;
    border: none;
    border-radius: 8px;
    cursor: pointer;
    transition: background 0.3s ease;
  }

  .btn-login:hover {
    background: #8a74ff;
  }

  .message {
    margin-top: 15px;
    text-align: center;
    font-weight: 600;
    font-size: 0.9rem;
    color: #ff6b6b;
  }
</style>
</head>
<body>

<div class="login-container">
  <h2>Login</h2>
  <form id="loginForm" novalidate>
    <div class="form-group">
      <label for="username">Username or Email</label>
      <input type="text" id="username" name="username" placeholder="Enter username or email" required />
    </div>
    <div class="form-group">
      <label for="password">Password</label>
      <input type="password" id="password" name="password" placeholder="Enter password" required />
    </div>
    <button type="submit" class="btn-login">Sign In</button>
    <div class="message" id="message"></div>
  </form>
</div>

<script>
  const form = document.getElementById('loginForm');
  const messageDiv = document.getElementById('message');

  form.addEventListener('submit', function(event) {
    event.preventDefault();
    messageDiv.textContent = '';

    const username = form.username.value.trim();
    const password = form.password.value.trim();

    if (!username) {
      messageDiv.textContent = 'Please enter your username or email.';
      form.username.focus();
      return;
    }

    if (!password) {
      messageDiv.textContent = 'Please enter your password.';
      form.password.focus();
      return;
    }

    // For demo purposes, simply display a success message.
    messageDiv.style.color = '#90ee90';
    messageDiv.textContent = 'Login successful! (Demo only)';
  });
</script>

</body>
</html>

