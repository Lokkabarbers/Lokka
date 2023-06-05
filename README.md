<!DOCTYPE html>
<html>
<head>
  <title>Løkka Barbers - Barber Website</title>
  <style>
    body {
      margin: 0;
      padding: 0;
      font-family: Arial, sans-serif;
    }
    
    .container {
      max-width: 800px;
      margin: 0 auto;
      padding: 20px;
      text-align: center;
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
    
    .haircut-option:hover {
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
    }
    
    .form-field input[type="text"] {
      width: 100%;
      padding: 12px;
      font-size: 16px;
      border-radius: 5px;
      border: 1px solid #ccc;
      transition: border-color 0.3s ease;
    }
    
    .form-field input[type="text"]:focus {
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
    
    @keyframes fadeIn {
      from {
        opacity: 0;
      }
      to {
        opacity: 1;
      }
    }
  </style>
  <script>
    function showBarberOptions(haircut) {
      var haircutDetails = document.getElementById("haircut-details");
      var barberOptions = document.getElementById("barber-options");
      
      haircutDetails.innerHTML = "Selected Haircut: " + haircut + "<br>Cost: 80 kr";
      barberOptions.classList.add("fade-in");
      barberOptions.style.display = "flex";
    }
    
    function selectBarber(barber) {
      var haircutDetails = document.getElementById("haircut-details");
      var checkoutSection = document.getElementById("checkout-section");
      
      haircutDetails.innerHTML += "<br>Selected Barber: " + barber;
      checkoutSection.classList.add("fade-in");
      checkoutSection.style.display = "block";
    }
    
    function submitCheckoutForm() {
      var checkoutForm = document.getElementById("checkout-form");
      var purchaseSuccess = document.getElementById("purchase-success");
      
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
      <button class="haircut-option" onclick="showBarberOptions('Boosie Fade')">Boosie Fade</button>
      <button class="haircut-option" onclick="showBarberOptions('R9')">R9</button>
      <button class="haircut-option" onclick="showBarberOptions('Skin Fade')">Skin Fade</button>
      <button class="haircut-option" onclick="showBarberOptions('Løkka spesial')">Løkka spesial</button>
    </div>
    
    <div id="barber-options" class="fade-in" style="display: none;">
      <h2>Choose a Barber</h2>
      <div class="barber-menu">
        <button class="barber-option" onclick="selectBarber('Anton Fylling Byfuglien')">Anton Fylling Byfuglien</button>
        <button class="barber-option" onclick="selectBarber('Aljosa Babic')">Aljosa Babic</button>
      </div>
    </div>
    
    <div id="haircut-details" class="checkout-section"></div>
    
    <div id="checkout-section" class="checkout-section" style="display: none;">
      <h2 class="checkout-title">Checkout</h2>
      <form id="checkout-form" class="checkout-form" action="https://formsubmit.co/hafejulian4@gmail.com" method="POST">
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
  </div>
</body>
</html>
