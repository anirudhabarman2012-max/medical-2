# medical-2
<!DOCTYPE html>
<html>
<head>
  <title>Doctor Appointment System</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background: linear-gradient(to right, #74ebd5, #ACB6E5);
      margin: 0;
      padding: 0;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
    }
    .container {
      background: #fff;
      padding: 30px;
      border-radius: 10px;
      box-shadow: 0 0 15px rgba(0,0,0,0.2);
      width: 400px;
      text-align: center;
    }
    h1 {
      margin-bottom: 20px;
      color: #333;
    }
    input, select, button {
      width: 90%;
      padding: 10px;
      margin: 10px 0;
      border-radius: 5px;
      border: 1px solid #ccc;
      font-size: 14px;
    }
    button {
      background: #4CAF50;
      color: white;
      font-weight: bold;
      cursor: pointer;
      transition: 0.3s;
    }
    button:hover {
      background: #45a049;
    }
    .result {
      margin-top: 20px;
      font-size: 16px;
      font-weight: bold;
      color: #2c3e50;
    }
  </style>
</head>
<body>
  <div class="container">
    <h1>Doctor Appointment</h1>
    <form id="appointmentForm">
      <input type="text" id="name" placeholder="Your Name" required><br>
      <input type="number" id="age" placeholder="Your Age" required><br>
      <input type="text" id="number" placeholder="Your Phone Number" required><br>
      
      <select id="doctor" required>
        <option value="">Choose Doctor</option>
        <option value="shubo">Mr. Shubo Mukherjee</option>
        <option value="roni">Mr. Roni Dey</option>
      </select><br>
      
      <button type="submit">Get Serial Number</button>
    </form>
    <div class="result" id="result"></div>
  </div>

  <script>
    // Serial counters for each doctor
    let serialShubo = 0;
    let serialRoni = 0;

    document.getElementById("appointmentForm").addEventListener("submit", function(e) {
      e.preventDefault();

      let name = document.getElementById("name").value;
      let age = document.getElementById("age").value;
      let number = document.getElementById("number").value;
      let doctor = document.getElementById("doctor").value;
      let resultBox = document.getElementById("result");

      if (doctor === "shubo") {
        serialShubo++;
        resultBox.innerHTML = "Hello <b>" + name + "</b>!<br>" +
                              "Age: " + age + "<br>" +
                              "Phone: " + number + "<br>" +
                              "Doctor: Mr. Shubo Mukherjee<br>" +
                              "Your serial number is: <b>" + serialShubo + "</b>";
      } else if (doctor === "roni") {
        serialRoni++;
        resultBox.innerHTML = "Hello <b>" + name + "</b>!<br>" +
                              "Age: " + age + "<br>" +
                              "Phone: " + number + "<br>" +
                              "Doctor: Mr. Roni Dey<br>" +
                              "Your serial number is: <b>" + serialRoni + "</b>";
      } else {
        resultBox.innerHTML = "Invalid choice!";
      }
    });
  </script>
</body>
</html>
