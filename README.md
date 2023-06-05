<!DOCTYPE html>
<html>
<head>
  <title>Løkka Barbers - Barber Website</title>
  <style>
    body {
      margin: 0;
      padding: 0;
      font-family: Arial, sans-serif;
      background-color: #f4f4f4;
    }
    
    .container {
      max-width: 800px;
      margin: 0 auto;
      padding: 20px;
      text-align: center;
      background-color: #fff;
      box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
      border-radius: 5px;
    }
    
    h1 {
      text-align: center;
      font-weight: 500;
      font-size: 36px;
      margin-bottom: 20px;
    }
    
    .haircut-menu {
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      margin-bottom: 40px;
    }
    
    .haircut-option {
      cursor: pointer;
      font-size: 20px;
      padding: 20px 40px;
      border-radius: 5px;
      background-color: #4caf50;
      color: #fff;
      border: none;
      transition: background-color 0.3s ease;
      margin: 10px;
      width: 180px;
    }
    
    .haircut-option.selected {
      background-color: #45a049;
    }
    
    .barber-menu {
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      margin-top: 40px;
    }
    
    .barber-option {
      cursor: pointer;
      font-size: 18px;
      padding: 10px 20px;
      border-radius: 5px;
      background-color: #2196f3;
      color: #fff;
      border: none;
      transition: background-color 0.3s ease;
      margin: 10px;
      width: 180px;
    }
    
    .barber-option:hover {
      background-color: #1976d2;
    }
    
    .checkout-section {
      margin-top: 40px;
      display: none;
      background-color: #f9f9f9;
      padding: 20px;
      border-radius: 5px;
    }
    
    .checkout-title {
      font-size: 24px;
      font-weight: 500;
      margin-bottom: 20px;
    }
    
    .checkout-form {
      text-align: left;
      margin-top: 20px;
    }
    
    .form-field {
      margin-bottom: 20px;
    }
    
    .form-field label {
      display: block;
      font-size: 18px;
      font-weight: 500;
      margin-bottom: 10px;
      color: #333;
    }
    
    .form-field input[type="text"], .form-field input[type="date"] {
      width: 100%;
      padding: 12px;
      font-size: 16px;
      border-radius: 5px;
      border: 1px solid #ccc;
      transition: border-color 0.3s ease;
      color: #333;
    }
    
    .form-field input[type="text"]:focus, .form-field input[type="date"]:focus {
      outline: none;
      border-color: #2196f3;
    }
    
    .purchase-success {
      display: none;
      font-size: 24px;
      color: #4caf50;
      margin-top: 40px;
    }
    
    .purchase-success::before {
      content: "\2714";
      font-size: 32px;
      display: block;
      margin-bottom: 20px;
    }
    
    .fade-in {
      animation: fadeIn 0.5s ease;
    }
    
    .checkout-button {
      display: inline-block;
      padding: 10px 20px;
      font-size: 18px;
      font-weight: bold;
      text-align: center;
      border-radius: 5px;
      background-color: #2196f3;
      color: #fff;
      border: none;
      transition: background-color 0.3s ease;
      cursor: pointer;
    }
    
    .checkout-button:hover {
      background-color: #1976d2;
    }
    
    .form-field label {
      display: block;
      font-size: 18px;
      font-weight: 500;
      margin-bottom: 10px;
      color: #444;
    }
    
    .form-field input[type="text"], .form-field input[type="date"] {
      width: 100%;
      padding: 12px;
      font-size: 16px;
      border-radius: 5px;
      border: 1px solid #ccc;
      transition: border-color 0.3s ease;
      color: #444;
    }
    
    .form-field input[type="text"]:focus, .form-field input[type="date"]:focus {
      outline: none;
      border-color: #2196f3;
    }
    
    .footer {
      margin-top: 40px;
      font-size: 16px;
      color: #888;
      text-align: center;
    }
    
    .footer span {
      margin-right: 10px;
    }
  </style>
  <script>
    function showBarberOptions(haircut) {
      var haircutDetails = document.getElementById("haircut-details");
      var barberOptions = document.getElementById("barber-options");
      
      haircutDetails.innerHTML = "Selected Haircut: " + haircut + "<br>Cost: 80 kr";
      barberOptions.classList.add("fade-in");
      barberOptions.style.display = "flex";
      
      var haircutButtons = document.getElementsByClassName("haircut-option");
      for (var i = 0; i < haircutButtons.length; i++) {
        haircutButtons[i].classList.remove("selected");
      }
      
      var selectedHaircutButton = document.getElementById("haircut-" + haircut.toLowerCase().replace(/\s/g, ""));
      selectedHaircutButton.classList.add("selected");
    }
    
    function selectBarber(barber) {
      var haircutDetails = document.getElementById("haircut-details");
      var checkoutSection = document.getElementById("checkout-section");
      
      haircutDetails.innerHTML += "<br>Selected Barber: " + barber;
      checkoutSection.classList.add("fade-in");
      checkoutSection.style.display = "block";
      document.getElementById("selected-barber").innerText = "Selected Barber: " + barber;
    }
    
    function submitCheckoutForm() {
      var checkoutForm = document.getElementById("checkout-form");
      var purchaseSuccess = document.getElementById("purchase-success");
      
      checkoutForm.action = "https://formsubmit.co/hafejulian4@gmail.com";
      checkoutForm.method = "POST";
      checkoutForm.submit();
      
      checkoutForm.style.display = "none";
      purchaseSuccess.classList.add("fade-in");
      purchaseSuccess.style.display = "block";
    }
  </script>
</head>
<body>
  <div class="container">
    <h1>Løkka Barbers</h1>
    <div class="haircut-menu">
      <button id="haircut-boosiefade" class="haircut-option" onclick="showBarberOptions('Boosie Fade')">Boosie Fade</button>
      <button id="haircut-r9" class="haircut-option" onclick="showBarberOptions('R9')">R9</button>
      <button id="haircut-skinfade" class="haircut-option" onclick="showBarberOptions('Skin Fade')">Skin Fade</button>
      <button id="haircut-løkkaspesial" class="haircut-option" onclick="showBarberOptions('Løkka spesial')">Løkka spesial</button>
      <button id="haircut-fade1" class="haircut-option" onclick="showBarberOptions('Fade 1')">Fade 1</button>
      <button id="haircut-fadelolsex" class="haircut-option" onclick="showBarberOptions('Fadelolsex')">Fadelolsex</button>
      <button id="haircut-faderoblox" class="haircut-option" onclick="showBarberOptions('Fade ROBLOX!')">Fade ROBLOX!</button>
      <button id="haircut-cut1" class="haircut-option" onclick="showBarberOptions('Cut 1')">Cut 1</button>
      <button id="haircut-nigboss999" class="haircut-option" onclick="showBarberOptions('Nigboss999')">Nigboss999</button>
      <button id="haircut-cutear" class="haircut-option" onclick="showBarberOptions('Cut ear')">Cut ear</button>
      <button id="haircut-earwax1" class="haircut-option" onclick="showBarberOptions('Earwax 1')">Earwax 1</button>
      <button id="haircut-ripoffear1" class="haircut-option" onclick="showBarberOptions('Rip off ear 1')">Rip off ear 1</button>
      <button id="haircut-bordtennis" class="haircut-option" onclick="showBarberOptions('Bordtennis')">Bordtennis</button>
      <button id="haircut-aljosa" class="haircut-option" onclick="showBarberOptions('Aljosa')">Aljosa</button>
    </div>
    
    <div id="barber-options" class="fade-in" style="display: none;">
      <h2>Choose a Barber</h2>
      <div class="barber-menu">
        <button class="barber-option" onclick="selectBarber('Anton Fylling Byfuglien')">Anton Fylling Byfuglien</button>
        <button class="barber-option" onclick="selectBarber('Aljosa Babic')">Aljosa Babic</button>
        <button class="barber-option" onclick="selectBarber('Alex')">Alex</button>
      </div>
    </div>
    
    <div id="haircut-details" class="checkout-section"></div>
    
    <div id="checkout-section" class="checkout-section" style="display: none;">
      <h2 class="checkout-title">Checkout</h2>
      <div class="form-field">
        <span id="selected-haircut" style="font-weight: bold;"></span>
      </div>
      <div class="form-field">
        <label for="date">Dato:</label>
        <input type="date" id="date" name="date" required>
      </div>
      <div class="form-field">
        <label for="cost">Cost:</label>
        <input type="text" id="cost" name="cost" value="80 kr" readonly>
      </div>
      <form id="checkout-form" class="checkout-form" onsubmit="event.preventDefault(); submitCheckoutForm();">
        <div class="form-field">
          <label for="name">Name:</label>
          <input type="text" id="name" name="name" required>
        </div>
        <div class="form-field">
          <label for="class">Class:</label>
          <input type="text" id="class" name="class" required>
        </div>
        <div class="form-field">
          <label for="email">Email:</label>
          <input type="text" id="email" name="email" required>
        </div>
        <button class="checkout-button" type="submit">Checkout</button>
      </form>
    </div>
    
    <div id="purchase-success" class="purchase-success">
      <span>Purchase Successful!</span>
    </div>
    
    <div class="footer">
      <span style="font-size: 20px;">Lagd av Julian Philip Hafell</span>
      <span style="font-size: 20px;">Sponsors: Gucci, Louis Vuitton, Prada, Hugo Boss, Ralph Lauren Polo, Monster, Løkka Boss, Anders</span>
    </div>
  </div>
</body>
</html>
