# Create  the index file 

```
<!DOCTYPE html>
<html>
<head>
	<title>Form Submission</title>
	<link rel="stylesheet" href="style.css">
</head>
<body>
<center><h1>Form Submission</h1></center>
<form action="verify.php" method="POST">
	<label for="name">Name:</label>
	<input type="text" id="name" name="username"><br><br>
	<label for="email">Email:</label>
	<input type="email" id="email" name="email" placeholder="xyz@mail.com"><br><br>
	<label for="password">Password</label>
	<input type="password" name="password"><br><br>
	<input type="submit" value="Submit">
</form>
</body>
</html>
```




 ## Create an external css file (named style.css)
 ``` 
 form {
	max-width: 500px;
	margin: 0 auto;
	background: #f2f2f2;
	padding: 20px;
	border-radius: 5px;
	box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
}

label {
	display: block;
	margin-bottom: 5px;
}

input[type="text"],
input[type="email"],
input[type="password"],
textarea {
	width: 100%;
	padding: 10px;
	border-radius: 5px;
	border: none;
	margin-bottom: 20px;
}

input[type="submit"] {
	background: #4CAF50;
	color: white;
	border: none;
	padding: 10px 20px;
	border-radius: 5px;
	cursor: pointer;
}

input[type="submit"]:hover {
	background: #3e8e41;
}
```

## Create a  simple  php file 
```
<?php

// Hardcoded username and password
$username = "anyone";
$password = "password123";
$email = "anyone@mail.com";

// Check if the form has been submitted
if ($_SERVER['REQUEST_METHOD'] == 'POST') {

  // Get the submitted username and password
  $submittedUsername = $_POST['username'];
  $submittedPassword = $_POST['password'];
  $submittedmail = $_POST['email'];

  // Verify the username and password
  if ($submittedUsername == $username && $submittedPassword == $password && $submittedmail== $email) {
    // Successful login
    echo "Welcome, " . $username . "!";
  } else {
    // Invalid login
    echo "Invalid username or password.";
  }
}

?>

```

## To containerize our application ,create a dockerfile

Name file *Dockerfile*

```
FROM php:7.2-apache
COPY . /var/www/html/
```





 
