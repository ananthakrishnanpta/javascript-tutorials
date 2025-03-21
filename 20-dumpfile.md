<!doctype html>
<html lang="en">
  <head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <title>Sign Up Page</title>
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-QWTKZyjpPEjISv5WaRU9OFeRpok6YctnYmDr5pNlyT2bRjXh0JMhjY6hW+ALEwIH" crossorigin="anonymous">
  </head>
  <body>
    <!-- Navbar -->
    <nav class="navbar navbar-expand-lg navbar-light bg-light">
      <div class="container-fluid">
        <a class="navbar-brand" href="#">MyApp</a>
        <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNav" aria-controls="navbarNav" aria-expanded="false" aria-label="Toggle navigation">
          <span class="navbar-toggler-icon"></span>
        </button>
        <div class="collapse navbar-collapse" id="navbarNav">
          <ul class="navbar-nav">
            <li class="nav-item">
              <a class="nav-link active" aria-current="page" href="#">Home</a>
            </li>
            <li class="nav-item">
              <a class="nav-link" href="#">Features</a>
            </li>
            <li class="nav-item">
              <a class="nav-link" href="#">Pricing</a>
            </li>
          </ul>
        </div>
      </div>
    </nav>

    <!-- Main Content -->
    <div class="container mt-5">
      <h2 class="text-center">Sign Up</h2>
      <form id="signup-form" novalidate>
        <div class="mb-3">
          <label for="username" class="form-label">Username</label>
          <input type="text" class="form-control" id="username" placeholder="Enter your username" required>
          <small id="username-error" class="text-danger"></small>
        </div>
        <div class="mb-3">
          <label for="email" class="form-label">Email</label>
          <input type="email" class="form-control" id="email" placeholder="Enter your email" required>
          <small id="email-error" class="text-danger"></small>
        </div>
        <div class="mb-3">
          <label for="password" class="form-label">Password</label>
          <input type="password" class="form-control" id="password" placeholder="Enter your password" required>
          <small id="password-error" class="text-danger"></small>
        </div>
        <div class="mb-3">
          <label for="confirm-password" class="form-label">Confirm Password</label>
          <input type="password" class="form-control" id="confirm-password" placeholder="Re-enter your password" required>
          <small id="confirm-password-error" class="text-danger"></small>
        </div>
        <button type="submit" class="btn btn-primary w-100">Sign Up</button>
      </form>
    </div>

    <script>
      document.addEventListener("DOMContentLoaded", () => {
        const form = document.getElementById("signup-form");
        const username = document.getElementById("username");
        const email = document.getElementById("email");
        const password = document.getElementById("password");
        const confirmPassword = document.getElementById("confirm-password");
        const usernameError = document.getElementById("username-error");
        const emailError = document.getElementById("email-error");
        const passwordError = document.getElementById("password-error");
        const confirmPasswordError = document.getElementById("confirm-password-error");

        form.addEventListener("submit", (event) => {
          let isValid = true;

          // Reset error messages
          usernameError.textContent = "";
          emailError.textContent = "";
          passwordError.textContent = "";
          confirmPasswordError.textContent = "";

          // Validate username
          if (!username.value.trim()) {
            usernameError.textContent = "Username is required.";
            isValid = false;
          } else if (username.value.trim().length < 3) {
            usernameError.textContent = "Username must be at least 3 characters.";
            isValid = false;
          }

          // Validate email
          const emailRegex = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
          if (!email.value.trim()) {
            emailError.textContent = "Email is required.";
            isValid = false;
          } else if (!emailRegex.test(email.value.trim())) {
            emailError.textContent = "Please enter a valid email.";
            isValid = false;
          }

          // Validate password
          if (!password.value.trim()) {
            passwordError.textContent = "Password is required.";
            isValid = false;
          } else if (password.value.trim().length < 6) {
            passwordError.textContent = "Password must be at least 6 characters.";
            isValid = false;
          }

          // Validate confirm password
          if (!confirmPassword.value.trim()) {
            confirmPasswordError.textContent = "Please confirm your password.";
            isValid = false;
          } else if (confirmPassword.value.trim() !== password.value.trim()) {
            confirmPasswordError.textContent = "Passwords do not match.";
            isValid = false;
          }

          // Prevent form submission if validation fails
          if (!isValid) {
            event.preventDefault();
          }
        });
      });
    </script>

    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/js/bootstrap.bundle.min.js" integrity="sha384-YvpcrYf0tY3lHB60NNkmXc5s9fDVZLESaAA55NDzOxhy9GkcIdslK1eN7N6jIeHz" crossorigin="anonymous"></script>
  </body>
</html>