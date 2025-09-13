<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Chandru AI Art</title>
  <link rel="stylesheet" href="https://fonts.googleapis.com/css?family=Montserrat:700,400&display=swap">
  <link rel="icon" href="../all.images/myicon.png">
  <style>
    * {
        margin: 0;
        padding: 0;
        box-sizing: border-box;
    }

    body {
        min-height: 100vh;
        padding: 1rem;
        background: linear-gradient(135deg, #090a0f 0%, #001f3f 100%) scroll;
        color: #f5f7fa;
        font-family: 'Montserrat', 'Segoe UI', Arial, sans-serif;
        position: relative;
        overflow: auto;
        letter-spacing: 0.02em;
    }

    /* Star effect */
    body::before {
        content: "";
        position: absolute;
        top: 0; left: 0; right: 0; bottom: 0;
        z-index: 0;
        pointer-events: none;
        background: 
            radial-gradient(white 1px, transparent 1px),
            radial-gradient(white 1px, transparent 1px),
            radial-gradient(white 1px, transparent 1px);
        background-size: 80px 80px, 120px 120px, 160px 160px;
        background-position: 0 0, 40px 60px, 80px 120px;
        opacity: 0.18;
    }

    /* Planets, asteroids, astronaut */
    .planet {
        position: absolute;
        border-radius: 50%;
        z-index: 2;
        opacity: 0.85;
        box-shadow: 0 0 40px 10px #2228;
    }
    .planet1 {
        width: 80px; height: 80px;
        top: 15vh; left: 8vw;
        background: radial-gradient(circle at 30% 30%, #ffe066 70%, #bfa600 100%);
        border: 4px solid #fffbe7;
    }
    .planet2 {
        width: 50px; height: 50px;
        bottom: 18vh; right: 12vw;
        background: radial-gradient(circle at 60% 40%, #6ec6ff 70%, #003366 100%);
        border: 3px solid #e0f7fa;
    }
    .asteroid {
        position: absolute;
        background: #b0a08f;
        border-radius: 50% 60% 55% 45% / 60% 50% 55% 45%;
        z-index: 2;
        opacity: 0.7;
        box-shadow: 0 0 12px 2px #2226;
    }
    .asteroid1 {
        width: 32px; height: 22px;
        top: 40vh; left: 25vw;
        transform: rotate(-18deg);
    }
    .asteroid2 {
        width: 22px; height: 16px;
        bottom: 30vh; right: 30vw;
        transform: rotate(12deg);
    }
    .astronaut {
        position: absolute;
        bottom: 10vh; left: 7vw;
        width: 38px; height: 70px;
        z-index: 3;
    }
    .astronaut::before {
        content: "";
        position: absolute;
        left: 10px; top: 0;
        width: 18px; height: 18px;
        background: #fff;
        border-radius: 50%;
        border: 2px solid #b0e0e6;
        box-shadow: 0 0 8px #fff;
    }
    .astronaut::after {
        content: "";
        position: absolute;
        left: 14px; top: 18px;
        width: 10px; height: 32px;
        background: #e0e6f0;
        border-radius: 6px;
        border: 2px solid #b0e0e6;
    }

    /* Headings */
    h1, h2, h3 {
        font-family: 'Montserrat', 'Segoe UI', Arial, sans-serif;
        font-weight: 700;
        text-transform: uppercase;
        letter-spacing: 0.08em;
        color: #ffffff;
        text-shadow: 0 0 8px #00bfff33, 0 0 16px #001f4d33;
        margin-bottom: 1rem;
        z-index: 1;
        text-align: center;
        padding: 2rem 0 0.5rem 0;
    }

    /* Form styling */
    form, fieldset {
        background: rgba(10, 18, 30, 0.85);
        border-radius: 12px;
        box-shadow: 0 4px 32px #001f3f44;
        padding: 2rem 2.5rem;
        margin: 2rem auto;
        max-width: 420px;
        z-index: 2;
        border: none;
    }

    label {
        font-size: 1.1rem;
        color: #aee7ff;
        margin-bottom: 0.3rem;
        display: block;
        font-weight: 500;
    }

    input, textarea {
        width: 100%;
        padding: 0.7rem 1rem;
        margin-bottom: 1.2rem;
        border-radius: 6px;
        border: 1px solid #003366;
        background: #0a1120;
        color: #e0e6f0;
        font-size: 1rem;
        font-family: inherit;
        transition: border 0.2s;
    }
    input:focus, textarea:focus {
        border: 1.5px solid #00bfff;
        outline: none;
    }

    /* Button */
    button {
        background: linear-gradient(90deg, #003366 0%, #00bfff 100%);
        color: #fff;
        border: none;
        padding: 0.9rem 2.2rem;
        border-radius: 8px;
        font-size: 1.15rem;
        font-weight: 700;
        box-shadow: 0 0 12px #00bfff55, 0 0 24px #001f4d33;
        cursor: pointer;
        transition: background 0.3s, box-shadow 0.3s;
        z-index: 1;
        margin-top: 0.5rem;
        letter-spacing: 0.04em;
    }
    button:hover {
        background: linear-gradient(90deg, #00bfff 0%, #003366 100%);
        box-shadow: 0 0 24px #00bfff99;
    }

    /* Footer */
    footer {
        background: rgba(0, 10, 30, 0.85);
        color: #aee7ff;
        text-align: center;
        padding: 1.5rem 0 1rem 0;
        margin-top: 2rem;
        font-size: 1.1rem;
        letter-spacing: 0.04em;
        border-top: 1px solid #003366;
        z-index: 2;
        position: relative;
    }
  </style>
</head>
<body>
  <!-- Space objects -->
  <div class="planet planet1"></div>
  <div class="planet planet2"></div>
  <div class="asteroid asteroid1"></div>
  <div class="asteroid asteroid2"></div>
  <div class="astronaut"></div>

  <div>
    <h1>Welcome's Chandru-AI-Art</h1>
  </div>
  <div>
    <form id="applicationForm">
      <fieldset>
        <legend>Application Form</legend>
        <label for="fristName">First Name :</label>
        <input type="text" name="fristName" id="fristName" placeholder="Chandru" required autofocus>
        <label for="lastName">Last Name :</label>
        <input type="text" name="lastName" id="lastName" placeholder="AI" required>
        <label for="email">Email :</label>
        <input type="email" name="email" id="email" placeholder="you@example.com" required>
        <label for="phone">Phone :</label>
        <input type="tel" name="phone" id="phone" placeholder="822031965012345" required minlength="15" maxlength="15" pattern="\d{15}" inputmode="numeric">
        <small>Enter a 15-digit phone number (numbers only).</small>
        <label for="requirement">Requirement :</label>
        <textarea name="requirement" id="requirement" rows="8" maxlength="500" placeholder="I’m Chandru, a developer in the making — blending Applied Mathematics, Physics, and Computer Science into interactive, problem‑solving web applications. This section will soon tell my story, my skills, and my vision for the future." style="width:100%; resize:vertical;"></textarea>
        <button type="submit" id="orderBtn">Place Your Order</button>
      </fieldset>
    </form>
    <div id="responseBox" style="margin:20px 0; color:green;"></div>
  </div>
  <footer>
    <h1 id="contactUs">Contact Us</h1>
    <nav class="contactUs">
      <p id="contactEmail">chandrumani1825@gamil.com</p>
      <p id="contactPhone">8220319650</p>
    </nav>
  </footer>
  <script>
    // Save user details and fetch from httpbin on submit
    document.addEventListener("DOMContentLoaded", function() {
      const orderBtn = document.getElementById("orderBtn");
      const responseBox = document.getElementById("responseBox");
      const form = document.getElementById("applicationForm");

      form.addEventListener("submit", function(e) {
        e.preventDefault();

        // Get user details from form
        const firstName = document.getElementById("fristName")?.value || "";
        const lastName = document.getElementById("lastName")?.value || "";
        const email = document.getElementById("email")?.value || "";
        const phone = document.getElementById("phone")?.value || "";
        const requirement = document.getElementById("requirement")?.value || "";

        // Save details to localStorage
        const userDetails = {
          firstName,
          lastName,
          email,
          phone,
          requirement
        };
        localStorage.setItem("userDetails", JSON.stringify(userDetails));

        // Update contact info
        document.getElementById("contactEmail").textContent = email;
        document.getElementById("contactPhone").textContent = phone;

        // Fetch from httpbin and show response
        fetch("https://httpbin.org/get")
          .then(response => response.json())
          .then(data => {
            responseBox.textContent = "Response: " + JSON.stringify(data, null, 2);
          })
          .catch(error => {
            responseBox.textContent = "Error: " + error;
          });
      });

      // Only allow numbers in phone input
      document.getElementById('phone').addEventListener('input', function (e) {
        this.value = this.value.replace(/\D/g, '').slice(0, 15);
      });
    });
  </script>
</body>
</html>
