<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Login</title>
    <style>
      body {
        display: flex;
        justify-content: center;
        align-items: center;
        height: 100vh;
        margin: 0;
        font-family: Arial, sans-serif;
        background-color: #f0f0f0;
        background-image: url(b.jpg);
      }
      form {
        width: 400px;
        padding: 20px;
        background: #fff;
        border-radius: 8px;
        box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
      }
      h2 {
        text-align: center;
        margin-bottom: 20px;
        font-size: 1.5rem;
      }
      input {
        width: 100%;
        margin: 10px 0;
        padding: 10px;
        border: 1px solid #ddd;
        border-radius: 4px;
        box-sizing: border-box;
        font-size: 1rem;
      }
      button {
        width: 100%;
        padding: 10px;
        background-color: #007bff;
        color: #fff;
        border: none;
        border-radius: 4px;
        font-size: 1rem;
        cursor: pointer;
        margin-top: 10px;
      }
      button:hover {
        background-color: #0056b3;
      }
      a {
        display: inline-block;
        text-align: center;
        width: 100%;
        margin-top: 10px;
        color: #007bff;
        text-decoration: none;
        font-size: 0.9rem;
      }
      a:hover {
        text-decoration: underline;
      }
    </style>
  </head>
  <body>
    <form id="loginForm">
      <h2>Login</h2>
      <input type="text" id="username" placeholder="Username" required />
      <input type="password" id="password" placeholder="Password" required />
      <button type="submit">Login</button>
      <a href="register.html">Go to Register</a>
    </form>

    <script>
      document
        .getElementById("loginForm")
        .addEventListener("submit", function (event) {
          event.preventDefault();

          const username = document.getElementById("username").value.trim();
          const password = document.getElementById("password").value.trim();

          const user = localStorage.getItem(username);
          if (!user) {
            alert("User does not exist. Please register first.");
            return;
          }

          const userData = JSON.parse(user);

          if (userData.password !== password) {
            alert("Incorrect password. Please try again.");
            return;
          }

          alert("Login successful!");
          window.location.href = "project.html";
        });
    </script>
  </body>
</html>



