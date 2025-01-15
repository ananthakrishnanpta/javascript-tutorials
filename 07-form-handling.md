# **Signup Page with Address - HTML, CSS, Bootstrap & Pure JavaScript**
  ### Go back to [JavaScript Tutorial](README.md)
---

In this project, we will create a **Signup Page** with a form that accepts user details, including their **name**, **email**, **password**, and **address**. The form will include validation to ensure the user inputs are correct.

### **1. Project Setup**

We will structure the project with the following files:

```
signup-project/
├── index.html
├── styles.css
└── script.js
```

### **2. HTML Structure (index.html)**

The **index.html** file will contain the structure of our signup form, utilizing **Bootstrap** for responsive styling and form elements.

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Signup Form</title>
  <!-- Link to Bootstrap CSS -->
  <link href="https://stackpath.bootstrapcdn.com/bootstrap/4.5.2/css/bootstrap.min.css" rel="stylesheet">
  <link rel="stylesheet" href="styles.css">
</head>
<body>
  <div class="container mt-5">
    <h2 class="text-center">Signup Form</h2>
    <form id="signup-form" class="mt-4">
      <!-- Full Name Input -->
      <div class="form-group">
        <label for="fullName">Full Name</label>
        <input type="text" class="form-control" id="fullName" placeholder="Enter full name" required>
        <small id="name-error" class="form-text text-danger"></small>
      </div>

      <!-- Email Input -->
      <div class="form-group">
        <label for="email">Email address</label>
        <input type="email" class="form-control" id="email" placeholder="Enter email" required>
        <small id="email-error" class="form-text text-danger"></small>
      </div>

      <!-- Password Input -->
      <div class="form-group">
        <label for="password">Password</label>
        <input type="password" class="form-control" id="password" placeholder="Enter password" required>
        <small id="password-error" class="form-text text-danger"></small>
      </div>

      <!-- Address Input -->
      <div class="form-group">
        <label for="address">Address</label>
        <textarea class="form-control" id="address" placeholder="Enter address" rows="3" required></textarea>
        <small id="address-error" class="form-text text-danger"></small>
      </div>

      <!-- Submit Button -->
      <button type="submit" class="btn btn-primary btn-block">Signup</button>
    </form>
  </div>

  <!-- Link to Bootstrap JS and jQuery -->
  <script src="https://code.jquery.com/jquery-3.5.1.slim.min.js"></script>
  <script src="https://cdn.jsdelivr.net/npm/@popperjs/core@2.9.3/dist/umd/popper.min.js"></script>
  <script src="https://stackpath.bootstrapcdn.com/bootstrap/4.5.2/js/bootstrap.min.js"></script>
  <script src="script.js"></script>
</body>
</html>
```

### **Explanation:**
- **Bootstrap 4** is used for responsive design and UI components such as form groups, buttons, and layout.
- **Input Fields:** We have **Full Name**, **Email**, **Password**, and **Address** fields.
- **Small error messages** (`<small>`) are used to display error messages for validation.

### **3. CSS Styling (styles.css)**

In the **styles.css**, we will customize the form layout and ensure good visual presentation.

```css
/* Centering the form on the page */
body {
  background-color: #f8f9fa;
}

.container {
  max-width: 500px;
  margin-top: 50px;
  padding: 30px;
  background-color: white;
  box-shadow: 0px 4px 6px rgba(0, 0, 0, 0.1);
}

/* Style for form error messages */
.form-text.text-danger {
  font-size: 0.9em;
  color: #e74a3b;
}
```

### **Explanation:**
- We center the form on the page using `margin-top` and `max-width`.
- The form is given a **white background** and a subtle **box-shadow** for a clean and professional look.
- Error messages are styled to be red and slightly smaller than the regular text.

### **4. JavaScript Functionality (script.js)**

The **script.js** will handle **form validation** and show any validation errors. It will also prevent form submission if the form data is invalid.

```javascript
// Selecting the form and input elements
const signupForm = document.getElementById('signup-form');
const fullName = document.getElementById('fullName');
const email = document.getElementById('email');
const password = document.getElementById('password');
const address = document.getElementById('address');

// Error message elements
const nameError = document.getElementById('name-error');
const emailError = document.getElementById('email-error');
const passwordError = document.getElementById('password-error');
const addressError = document.getElementById('address-error');

// Form submit event
signupForm.addEventListener('submit', function(event) {
  event.preventDefault();

  let isValid = true;

  // Clear previous error messages
  nameError.textContent = '';
  emailError.textContent = '';
  passwordError.textContent = '';
  addressError.textContent = '';

  // Validate Full Name
  if (fullName.value.trim() === '') {
    nameError.textContent = 'Full Name is required.';
    isValid = false;
  }

  // Validate Email
  const emailPattern = /^[a-zA-Z0-9._%+-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,}$/;
  if (!emailPattern.test(email.value.trim())) {
    emailError.textContent = 'Please enter a valid email.';
    isValid = false;
  }

  // Validate Password
  if (password.value.length < 6) {
    passwordError.textContent = 'Password must be at least 6 characters.';
    isValid = false;
  }

  // Validate Address
  if (address.value.trim() === '') {
    addressError.textContent = 'Address is required.';
    isValid = false;
  }

  // If all inputs are valid, log the data
  if (isValid) {
    const userData = {
      fullName: fullName.value.trim(),
      email: email.value.trim(),
      password: password.value.trim(),
      address: address.value.trim(),
    };

    console.log('Form Data Submitted:', userData);
    alert('Signup Successful!');
    
    // You can proceed with sending this data to a backend API or localStorage
  }
});
```

### **Explanation:**
- **Form Selection:** The script begins by selecting the form and input elements using `getElementById`.
- **Event Listener:** An event listener is added to the form, which prevents the default submission and triggers validation when the user clicks the "Signup" button.
- **Form Validation:**
  - The **Full Name** field must not be empty.
  - The **Email** field must match the standard email pattern.
  - The **Password** must be at least 6 characters long.
  - The **Address** must not be empty.
- **Error Handling:** If validation fails, an error message is shown next to the corresponding field. If all validations pass, the user data is logged to the console, and an alert is shown.

---

## **5. How the Project Works**

1. The user fills out the **Signup Form** with their **Full Name**, **Email**, **Password**, and **Address**.
2. The form is **validated** using JavaScript. If any field is invalid, an error message is displayed under the respective field.
3. If the form passes validation, it is processed, and a confirmation message is shown, logging the user data to the console.

---

## **6. Deployment**

To deploy this application, you can use **GitHub Pages** or any static file hosting service.

### **Steps to Deploy:**

1. **Push your code to GitHub**.
2. **Go to GitHub Pages** in your repository settings.
3. Set the source as the `main` branch or `gh-pages` branch.
4. Visit the URL provided by GitHub to access your deployed project.

---
