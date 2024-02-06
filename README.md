<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link rel="stylesheet" href="style.css">
    <link rel="stylesheet" href="fontawesome-free-6.4.2-web\css\all.css">
    <script src="fontawesome-free-6.4.2-web\css\all.css" crossorigin="anonymous"></script>
    
    <title>form validation</title>
</head>
<body>
    <div class="container">
        <form action="#" method="post">
            <i class="fas fa-paper-plane"></i>
            <div class="input-group">
                <label for="">Full name</label>
                <input name="name" type="text" placeholder="enter your name" id="contact-name" onkeyup="validateName()">
                <span id="name-error"></span>
            </div>
            <div class="input-group">
                <label for="">Phone No.</label>
                <input name="phone" type="tel" placeholder="123 456 7890" id="contact-phone" onkeyup="validatePhone()">
                <span id="phone-error"></span>
            </div>
            <div class="input-group">
                <label for="">Email id</label>
                <input name="email" type="email" placeholder="enter email" id="contact-email" onkeyup="validateEmail()">
                <span id="email-error"></span>
            </div>
            <div class="input-group">
                <label for="">Your message</label>
                <textarea name="message" rows="5" placeholder="enter your message" id="contact-message" onkeyup="validateMessage()"></textarea>
                <span id="message-error"></span>
            </div>
            <button onclick="return validateForm()" name="submit">submit</button>
            <span id="submit-error"></span>
        </form>
    </div>
    <script src="script.js"></script>
</body>
</html>
<?php
$name = "";
$phone = "";
$email = "";
$message = "" ;

if ($_SERVER["REQUEST_METHOD"] == "POST") {
  $name = test_input($_POST["name"]);
  $phone = test_input($_POST["phone"]);
  $email = test_input($_POST["email"]);
  $message = test_input($_POST["message"]); 
}
function test_input($data) {
    $data = trim($data);
    $data = stripslashes($data);
    $data = htmlspecialchars($data);
    return $data;
  }
  ?>
  <?php
echo "<h2>Your Input:</h2>";
echo "Your Name;".$name;
echo "Your phone;".$phone;
echo "Your email;".$email;
echo "Your message;".$message;
?>
