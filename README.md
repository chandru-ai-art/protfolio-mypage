# protfolio-mypage

<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <link rel="stylesheet" href="../style.css/home.css">
  <script src="../script.js/home.js" defer></script>
  <link rel="icon" href="../all.images/myicon.png">
  <link href="https://fonts.googleapis.com/css?family=Montserrat:700,400&display=swap" rel="stylesheet">
  <title>Chandru AI Art</title>
</head>
<body>
  <div>
    <h1>Welcome's Chandru-AI-Art</h1>
  </div>
  <div>
    <form action="applicationForm">
    <fieldset>
      <legend>Application Form</legend>
      <label for="fristName">Frist Name :</label>
        <input type="text" name="fristName" id="fristName" placeholder="chandru" autocomplete required>
        <br><br>
      <label for="lastName">Last Name :</label>
        <input type="text" name="lastName" id="lastName" placeholder="M" autocomplete>
        <br><br>
      <label for="email">E-mail Address :</label>
        <input type="email" name="email" id="email" placeholder="chandrumani1825@gamil.com" autocomplete required>
        <br><br>
      <label for="phone">Phone :</label>
        <input type="tel" name="phone" id="phone" placeholder="8220319650" autocomplete required   minlength="10" maxlength="10" pattern="{0-9} {0-9} " inputmode="numeric" >
        <br><br>
      <label for="requirement">Requirement :</label>
        <textarea type="text" name="requirement" id="requirement" rows="5" minilength="500" placeholder=" I’m Chandru, a developer in the making — blending Applied Mathematics, Physics, and Computer Science into interactive, problem‑solving web applications. This section will soon tell my story, my skills, and my vision for the future." style="width:100%; resize:vertical;" ></textarea>
    </fieldset>
    <button type="submit" id="orderBtn">Place Your Order</button>
    </form>
  </div>
  <footer>
    <h1 id="contactUs">Contact Us</h1>
    <nav class="contactUs">
      <p id="contactName">Chandru M</p>
      <p id="contactEmail">chandrumani1825@gamil.com</p>
      <p id="contactPhone">8220319650</p>
    </nav>
  </footer>
</body>
</html>
