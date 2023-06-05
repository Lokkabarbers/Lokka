
<html>
<head>
  <title>Løkka Barbers - Barber Website</title>
  <style>
    body {
      margin: 0;
      padding: 0;
      font-family: Arial, sans-serif;
      background-color: #000;
      color: #fff;
    }
    
    .container {
      max-width: 800px;
      margin: 0 auto;
      padding: 20px;
      text-align: center;
      background-color: #333;
      box-shadow: 0 2px 10px rgba(0, 0, 0, 0.3);
      border-radius: 5px;
    }
    
    h1 {
      text-align: center;
      font-weight: 500;
      font-size: 36px;
      margin-bottom: 20px;
      color: #fff;
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
      background-color: #ff0000;
      color: #fff;
      border: none;
      transition: background-color 0.3s ease;
      margin: 10px;
      width: 180px;
    }
    
    .haircut-option:hover {
      background-color: #c70000;
    }
    
    .haircut-option.selected {
      background-color: #ff6666;
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
      background-color: #ff3333;
      color: #fff;
      border: none;
      transition: background-color 0.3s ease;
      margin: 10px;
      width: 180px;
    }
    
    .barber-option:hover {
      background-color: #c70000;
    }
    
    .checkout-section {
      margin-top: 40px;
      display: none;
      background-color: #444;
      padding: 20px;
      border-radius: 5px;
    }
    
    .checkout-title {
      font-size: 24px;
      font-weight: 500;
      margin-bottom: 20px;
      color: #000;
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
      color: #000;
    }
    
    .form-field input[type="text"],
    .form-field input[type="date"] {
      width: 100%;
      padding: 12px;
      font-size: 16px;
      border-radius: 5px;
      border: 1px solid #ccc;
      transition: border-color 0.3s ease;
      color: #000;
    }
    
    .form-field input[type="text"]:focus,
    .form-field input[type="date"]:focus {
      outline: none;
      border-color: #ff3333;
    }
    
    .purchase-success {
      display: none;
      font-size: 24px;
      color: #00ff00;
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
      background-color: #ff3333;
      color: #fff;
      border: none;
      transition: background-color 0.3s ease;
      cursor: pointer;
    }
    
    .checkout-button:hover {
      background-color: #c70000;
    }
    
    .form-field label {
      display: block;
      font-size: 18px;
      font-weight: 500;
      margin-bottom: 10px;
      color: #000;
    }
    
    .form-field input[type="text"],
    .form-field input[type="date"] {
      width: 100%;
      padding: 12px;
      font-size: 16px;
      border-radius: 5px;
      border: 1px solid #ccc;
      transition: border-color 0.3s ease;
      color: #000;
    }
    
    .form-field input[type="text"]:focus,
    .form-field input[type="date"]:focus {
      outline: none;
      border-color: #ff3333;
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
    var selectedHaircut = null;
    
	function showBarberOptions(haircut) {
	  var selectedHaircutDisplay = document.getElementById("selected-haircut-display");
	  var selectedHaircutInput = document.getElementById("selected-haircut");
	
	  if (selectedHaircut) {
	    selectedHaircut.classList.remove("selected");
	  }
	
	  selectedHaircut = document.getElementById(haircut.replace(/\s+/g, '-').toLowerCase());
	  selectedHaircut.classList.add("selected");
	
	  selectedHaircutDisplay.innerHTML = "Selected Haircut: " + haircut;
	  selectedHaircutInput.value = haircut;
	
	  var barberOptions = document.getElementById("barber-options");
	  barberOptions.classList.add("fade-in");
	  barberOptions.style.display = "flex";
	}
    
function selectBarber(barber) {
  var haircutDetails = document.getElementById("haircut-details");
  var checkoutSection = document.getElementById("checkout-section");
  
  haircutDetails.innerHTML += "<br>Selected Barber: " + barber;
  checkoutSection.classList.add("fade-in");
  checkoutSection.style.display = "block";
  
  var selectedBarberDisplay = document.getElementById("selected-barber-display");
  selectedBarberDisplay.innerText = "Selected Barber: " + barber;
  document.getElementById("selected-barber").value = barber;
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
      <button id="boosie-fade" class="haircut-option" onclick="showBarberOptions('Boosie Fade')">Boosie Fade</button>
      <button id="R9 Fade" class="haircut-option" onclick="showBarberOptions('R9 Fade')">R9 Fade</button>
      <button id="skin-fade" class="haircut-option" onclick="showBarberOptions('Skin Fade')">Skin Fade</button>
      <button id="løkka-spesial" class="haircut-option" onclick="showBarberOptions('Løkka spesial')">Løkka spesial</button>
      <button id="fade-1" class="haircut-option" onclick="showBarberOptions('Fade 1')">Fade 1</button>
      <button id="Low Taper Fade" class="haircut-option" onclick="showBarberOptions('Low Taper Fade')">Low Taper Fade</button>
      <button id="Gabriel Garcialol" class="haircut-option" onclick="showBarberOptions('Gabriel Garcialol')">Gabriel Garcialol</button>
      <button id="Anders" class="haircut-option" onclick="showBarberOptions('Anders')">Anders</button>
      <button id="nigboss999" class="haircut-option" onclick="showBarberOptions('Nigboss999')">Nigboss999</button>
      <button id="Bart Simpson Moment" class="haircut-option" onclick="showBarberOptions('Bart Simpson Moment')">Bart Simpson Moment</button>
      <button id="earwax-1" class="haircut-option" onclick="showBarberOptions('Earwax 1')">Earwax 1</button>
      <button id="Dreadlocks" class="haircut-option" onclick="showBarberOptions('Dreadlocks')">Dreadlocks</button>
      <button id="bordtennis" class="haircut-option" onclick="showBarberOptions('Bordtennis')">Bordtennis</button>
      <button id="aljosa" class="haircut-option" onclick="showBarberOptions('Aljosa')">Aljosa</button>
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
      <form id="checkout-form" class="checkout-form" onsubmit="event.preventDefault(); submitCheckoutForm();">
	<input type="hidden" name="_captcha" value="false">
        <div class="form-field">
          <span id="Betaling" style="font-weight: bold;"></span>
        </div>
        <div class="form-field">
          <input type="hidden" id="selected-haircut" name="selected-haircut">
          <div id="selected-haircut-display" style="font-weight: bold;"></div>
        </div>
<div class="form-field">
  <input type="hidden" id="selected-barber" name="selected-barber">
  <div id="selected-barber-display" style="font-weight: bold;"></div>
</div>
        <div class="form-field">
          <label for="cost">Cost:</label>
          <input type="text" id="cost" name="cost" value="80 kr" readonly>
        </div>
        <div class="form-field">
          <label for="date">Dato:</label>
          <input type="text" id="date" name="date" required>
        </div>
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
