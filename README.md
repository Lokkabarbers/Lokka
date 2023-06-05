<!DOCTYPE html>
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
    
    /* Background images */
    
    .background-images {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      z-index: -1;
    }
    
    .background-images img {
      position: absolute;
      max-width: 100%;
      max-height: 100%;
      object-fit: cover;
    }
    
    /* Image positions */
    
    .image-position-1 {
      top: 25%;
      left: 25%;
    }
    
    .image-position-2 {
      bottom: 0;
      right: 0;
    }
    
    .image-position-3 {
      top: 35%;
      right: 35%;
    }
    
    .image-position-4 {
      bottom: 45%;
      right: 0;
    }
    
    .image-position-5 {
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%);
    }
    
    /* Additional image positions */
    
    .image-position-6 {
      bottom: 60%;
      left: 10%;
    }
    
    .image-position-7 {
      top: 60%;
      right: 10%;
    }
    
    .image-position-8 {
      top: 10%;
      right: 10%;
    }
    
    .image-position-9 {
      top: 10%;
      left: 10%;
    }
    
    .image-position-10 {
      top: 70%;
      left: 30%;
    }
    
    .image-position-11 {
      bottom: 70%;
      left: 30%;
    }
    
    .image-position-12 {
      top: 80%;
      right: 40%;
    }
    
    .image-position-13 {
      bottom: 80%;
      right: 40%;
    }
    
    .image-position-14 {
      bottom: 20%;
      left: 20%;
    }
    
    .image-position-15 {
      bottom: 20%;
      right: 20%;
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
  <div class="background-images">
    <img src="data:image/jpeg;base64,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" class="image-position-1">
    <img src="https://media.tenor.com/_X08GvNjovQAAAAC/skull-spinning-skull.gif" class="image-position-2">
    <img src="https://media.tenor.com/7_ZjV-cIL9YAAAAd/skull-grin.gif" class="image-position-3">
    <img src="https://i.gifer.com/XwI7.gif" class="image-position-4">
    <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTUUYrjwzwZopOtODzwrcb3sAsTzBnOrQs1PQ&usqp=CAU" class="image-position-5">
    <img src="https://i.pinimg.com/originals/90/93/fb/9093fb23e005aabe2ec21015befdef40.gif" class="image-position-6">
    <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTUUYrjwzwZopOtODzwrcb3sAsTzBnOrQs1PQ&usqp=CAU" class="image-position-7">
    <img src="https://media.tenor.com/7_ZjV-cIL9YAAAAd/skull-grin.gif" class="image-position-8">
    <img src="https://i.gifer.com/XwI7.gif" class="image-position-9">
    <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTUUYrjwzwZopOtODzwrcb3sAsTzBnOrQs1PQ&usqp=CAU" class="image-position-10">
    <img src="https://media.tenor.com/_X08GvNjovQAAAAC/skull-spinning-skull.gif" class="image-position-11">
    <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRa03LGrorNKOHrCZP5BZ1NYH6wVgA9qZ9WZE4_N8JxvHbq-jBE_Jij_fyaU4jAqKh4az4&usqp=CAU" class="image-position-12">
    <img src="data:image/jpeg;base64,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" class="image-position-13">
    <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRa03LGrorNKOHrCZP5BZ1NYH6wVgA9qZ9WZE4_N8JxvHbq-jBE_Jij_fyaU4jAqKh4az4&usqp=CAU" class="image-position-14">
    <img src="https://i.gifer.com/XwI7.gif" class="image-position-15">
  </div>
  <div class="container">
    <h1>Løkka Barbers</h1>
    <div class="haircut-menu">
      <button id="boosie-fade" class="haircut-option" onclick="showBarberOptions('Boosie Fade')">Boosie Fade</button>
      <button id="r9" class="haircut-option" onclick="showBarberOptions('R9')">R9</button>
      <button id="skin-fade" class="haircut-option" onclick="showBarberOptions('Skin Fade')">Skin Fade</button>
      <button id="løkka-spesial" class="haircut-option" onclick="showBarberOptions('Løkka spesial')">Løkka spesial</button>
      <button id="fade" class="haircut-option" onclick="showBarberOptions('Fade')">Fade</button>
      <button id="fadelolsex" class="haircut-option" onclick="showBarberOptions('Fadelolsex')">Fadelolsex</button>
      <button id="omskjæring" class="haircut-option" onclick="showBarberOptions('Omskjæring')">Omskjæring</button>
      <button id="flintskallet" class="haircut-option" onclick="showBarberOptions('flintskallet')">flintskallet</button>
      <button id="spotifypremium5" class="haircut-option" onclick="showBarberOptions('spotifypremium5')">spotifypremium5</button>
      <button id="gabrielgarcialol" class="haircut-option" onclick="showBarberOptions('GabrielGarcialol')">GabrielGarcialol</button>
      <button id="earwax-1" class="haircut-option" onclick="showBarberOptions('Earwax 1')">Earwax 1</button>
      <button id="mullet" class="haircut-option" onclick="showBarberOptions('Mullet')">Mullet</button>
      <button id="bordtennis" class="haircut-option" onclick="showBarberOptions('Bordtennis')">Bordtennis</button>
      <button id="aljosa" class="haircut-option" onclick="showBarberOptions('Aljosa')">Aljosa</button>
    </div>
    
    <div id="barber-options" class="fade-in" style="display: none;">
      <h2>Choose a Barber</h2>
      <div class="barber-menu">
        <button class="barber-option" onclick="selectBarber('Anton Fylling Byfuglien')">Anton Fylling Byfuglien</button>
        <button class="barber-option" onclick="selectBarber('Aljosa Babic')">Aljosa Babic</button>
        <button class="barber-option" onclick="selectBarber('Anders Behring Breivik')">Alex</button>
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
