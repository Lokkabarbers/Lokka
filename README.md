
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
      max-width: 400px; /* Changed the max-width to fit a phone screen */
      margin: 0 auto;
      padding: 20px;
      text-align: center;
      background-color: rgba(51, 51, 51, 0.7); /* Made the background menu more transparent */
      box-shadow: 0 2px 10px rgba(0, 0, 0, 0.3);
      border-radius: 5px;
    }
    
    h1 {
      text-align: center;
      font-weight: 500;
      font-size: 24px; /* Decreased font size to fit smaller screen */
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
      font-size: 16px; /* Decreased font size to fit smaller screen */
      padding: 10px 20px; /* Decreased padding to fit smaller screen */
      border-radius: 5px;
      background-color: #ff0000;
      color: #fff;
      border: none;
      transition: background-color 0.3s ease;
      margin: 5px; /* Decreased margin to spread pictures more */
      width: 150px; /* Decreased width to fit smaller screen */
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
      font-size: 14px; /* Decreased font size to fit smaller screen */
      padding: 8px 16px; /* Decreased padding to fit smaller screen */
      border-radius: 5px;
      background-color: #ff3333;
      color: #fff;
      border: none;
      transition: background-color 0.3s ease;
      margin: 5px; /* Decreased margin to spread pictures more */
      width: 150px; /* Decreased width to fit smaller screen */
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
      font-size: 20px; /* Decreased font size to fit smaller screen */
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
      font-size: 16px; /* Decreased font size to fit smaller screen */
      font-weight: 500;
      margin-bottom: 10px;
      color: #000;
    }
    
    .form-field input[type="text"],
    .form-field input[type="date"] {
      width: 100%;
      padding: 12px;
      font-size: 14px; /* Decreased font size to fit smaller screen */
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
      font-size: 20px; /* Decreased font size to fit smaller screen */
      color: #00ff00;
      margin-top: 40px;
    }
    
    .purchase-success::before {
      content: "\2714";
      font-size: 24px; /* Increased font size for visibility */
      display: block;
      margin-bottom: 20px;
    }
    
    .fade-in {
      animation: fadeIn 0.5s ease;
    }
    
    .checkout-button {
      display: inline-block;
      padding: 10px 20px;
      font-size: 16px; /* Decreased font size to fit smaller screen */
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
    
    .footer {
      margin-top: 40px;
      font-size: 14px; /* Decreased font size to fit smaller screen */
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
      top: 20%; /* Adjusted position to spread pictures more */
      left: 20%; /* Adjusted position to spread pictures more */
    }
    
    .image-position-2 {
      bottom: 0;
      right: 0;
    }
    
    .image-position-3 {
      top: 30%; /* Adjusted position to spread pictures more */
      right: 30%; /* Adjusted position to spread pictures more */
    }
    
    .image-position-4 {
      bottom: 40%; /* Adjusted position to spread pictures more */
      right: 0;
    }
    
    .image-position-5 {
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%);
    }
    
    /* Additional image positions */
    
    .image-position-6 {
      bottom: 60%; /* Adjusted position to spread pictures more */
      left: 10%;
    }
    
    .image-position-7 {
      top: 60%; /* Adjusted position to spread pictures more */
      right: 10%;
    }
    
    .image-position-8 {
      top: 10%; /* Adjusted position to spread pictures more */
      right: 10%;
    }
    
    .image-position-9 {
      top: 10%; /* Adjusted position to spread pictures more */
      left: 10%;
    }
    
    .image-position-10 {
      top: 70%; /* Adjusted position to spread pictures more */
      left: 30%;
    }
    
    .image-position-11 {
      bottom: 70%; /* Adjusted position to spread pictures more */
      left: 30%;
    }
    
    .image-position-12 {
      top: 80%; /* Adjusted position to spread pictures more */
      right: 40%;
    }
    
    .image-position-13 {
      bottom: 80%; /* Adjusted position to spread pictures more */
      right: 40%;
    }
    
    .image-position-14 {
      bottom: 20%; /* Adjusted position to spread pictures more */
      left: 20%;
    }
    
    .image-position-15 {
      bottom: 20%; /* Adjusted position to spread pictures more */
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
      
      checkoutForm.action = "https://formsubmit.co/lokkabarber@gmail.com";
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
    <img src="b " class="image-position-1">
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
    <img src="t " class="image-position-13">
    <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRa03LGrorNKOHrCZP5BZ1NYH6wVgA9qZ9WZE4_N8JxvHbq-jBE_Jij_fyaU4jAqKh4az4&usqp=CAU" class="image-position-14">
    <img src="https://i.gifer.com/XwI7.gif" class="image-position-15">
  </div>
  <div class="container">
    <h1>Løkka Barbers</h1>
    <div class="haircut-menu">
      <button id="boosie-fade" class="haircut-option" onclick="showBarberOptions('Boosie Fade')">Boosie Fade</button>
      <button id="moon-boosie-fade" class="haircut-option" onclick="showBarberOptions('Moon Boosie Fade')">Moon Boosie Fade</button>
      <button id="r9" class="haircut-option" onclick="showBarberOptions('R9')">R9</button>
      <button id="skin-fade" class="haircut-option" onclick="showBarberOptions('Skin Fade')">Skin Fade</button>
      <button id="løkka-spesial" class="haircut-option" onclick="showBarberOptions('Løkka spesial')">Løkka spesial</button>
      <button id="low-taper-fade" class="haircut-option" onclick="showBarberOptions('Low Taper Fade')">Low Taper Fade</button>
      <button id="high-taper-fade" class="haircut-option" onclick="showBarberOptions('High Taper Fade')">High Taper Fade</button>
      <button id="medium-taper-fade" class="haircut-option" onclick="showBarberOptions('Medium Taper Fade')">Medium Taper Fade</button>
      <button id="fade" class="haircut-option" onclick="showBarberOptions('Fade')">Fade</button>
      <button id="tortur" class="haircut-option" onclick="showBarberOptions('Tortur')">Tortur</button>
      <button id="omskjæring" class="haircut-option" onclick="showBarberOptions('Omskjæring')">Omskjæring</button>
      <button id="flintskallet" class="haircut-option" onclick="showBarberOptions('Flintskallet')">Flintskallet</button>
      <button id="spotifypremium5" class="haircut-option" onclick="showBarberOptions('Spotifypremium5')">Spotifypremium5</button>
      <button id="gabrielgarcialol" class="haircut-option" onclick="showBarberOptions('GabrielGarcialol')">GabrielGarcialol</button>
      <button id="rumpehår braids" class="haircut-option" onclick="showBarberOptions('Rumphårfjerning')">Rumphårfjerning</button>
      <button id="mullet" class="haircut-option" onclick="showBarberOptions('Mullet')">Mullet</button>
      <button id="bordtennis" class="haircut-option" onclick="showBarberOptions('Bordtennis')">Bordtennis</button>
      <button id="omskjæring-ekstrem" class="haircut-option" onclick="showBarberOptions('Omskjæring Ekstrem')">Omskjæring Ekstrem</button>
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
          <label for="date">Date:</label>
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
      <span style="font-size: 12px;">Lagd av Julian Philip Hafell</span> /
      <span style="font-size: 12px;">Sponsors: Gucci, Louis Vuitton, Prada, Hugo Boss, Ralph Lauren Polo, Monster, Løkka Boss, Anders</span> 
    </div>
  </div>
</body>
</html>
