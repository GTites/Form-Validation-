const form = document.getElementById('registrationForm');
const username = document.getElementById('username');
const email = document.getElementById('email');
const password = document.getElementById('password');
const password2 = document.getElementById('password2');

form.addEventListener('submit', (e) => {
  e.preventDefault(); // Prevent default submit

  checkInputs();
});

function checkInputs() {
  const usernameValue = username.value.trim();
  const emailValue = email.value.trim();
  const passwordValue = password.value.trim();
  const password2Value = password2.value.trim();

  // Username
  if (usernameValue === '') {
    setError(username, 'Username is required');
  } else {
    setSuccess(username);
  }

  // Email
  if (emailValue === '') {
    setError(email, 'Email is required');
  } else if (!isValidEmail(emailValue)) {
    setError(email, 'Email is not valid');
  } else {
    setSuccess(email);
  }

  // Password
  if (passwordValue === '') {
    setError(password, 'Password is required');
  } else if (passwordValue.length < 6) {
    setError(password, 'Password must be at least 6 characters');
  } else {
    setSuccess(password);
  }

  // Confirm Password
  if (password2Value === '') {
    setError(password2, 'Please confirm your password');
  } else if (passwordValue !== password2Value) {
    setError(password2, 'Passwords do not match');
  } else {
    setSuccess(password2);
  }
}

function setError(input, message) {
  const formControl = input.parentElement;
  const small = formControl.querySelector('small');
  formControl.className = 'form-control error';
  small.innerText = message;
}

function setSuccess(input) {
  const formControl = input.parentElement;
  formControl.className = 'form-control success';
}

function isValidEmail(email) {
  return /^[^\s@]+@[^\s@]+\.[^\s@]+$/.test(email);
}
