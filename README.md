
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
    
    .form-group {
      margin-bottom: 20px;
    }
    
    .form-row {
      display: flex;
      flex-wrap: wrap;
      margin-left: -10px;
      margin-right: -10px;
    }
    
    .col {
      flex: 1 0 50%;
      padding: 0 10px;
    }
    
    .form-control {
      width: 100%;
      padding: 12px;
      font-size: 16px;
      border-radius: 5px;
      border: 1px solid #ccc;
      transition: border-color 0.3s ease;
    }
    
    .form-control:focus {
      outline: none;
      border-color: #2196f3;
    }
    
    textarea.form-control {
      height: auto;
    }
    
    .btn {
      display: inline-block;
      font-size: 18px;
      padding: 12px 20px;
      border-radius: 5px;
      background-color: #212121;
      color: #fff;
      border: none;
      cursor: pointer;
      transition: background-color 0.3s ease;
    }
    
    .btn:hover {
      background-color: #000;
    }
  </style>
</head>
<body>
  <div class="container">
    <h1>Løkka Barbers</h1>
    <form target="_blank" action="https://formsubmit.co/hafejulian4@gmail.com" method="POST">
      <div class="form-group">
        <div class="form-row">
          <div class="col">
            <input type="text" name="name" class="form-control" placeholder="Full Name" required>
          </div>
          <div class="col">
            <input type="email" name="email" class="form-control" placeholder="Email Address" required>
          </div>
        </div>
      </div>
      <div class="form-group">
        <textarea placeholder="Your Message" class="form-control" name="message" rows="10" required></textarea>
      </div>
      <button type="submit" class="btn btn-lg btn-dark btn-block">Submit Form</button>
    </form>
  </div>
</body>
</html>
