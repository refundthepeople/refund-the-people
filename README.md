<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <title>FOIA Request Generator</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background: #f5f5f5;
      color: #222;
      padding: 30px;
    }
    .container {
      max-width: 600px;
      margin: auto;
      background: white;
      padding: 20px;
      border-radius: 8px;
    }
    label {
      font-weight: bold;
      display: block;
      margin-top: 15px;
    }
    input, textarea {
      width: 100%;
      padding: 10px;
      margin-top: 5px;
      border: 1px solid #ccc;
      border-radius: 5px;
    }
    button {
      margin-top: 20px;
      padding: 10px 15px;
      background: #222;
      color: white;
      border: none;
      border-radius: 5px;
      cursor: pointer;
    }
    textarea {
      margin-top: 20px;
    }
  </style>
</head>
<body>
  <div class="container">
    <h1>FOIA Request Generator</h1>
    
    <label for="agency">Target Agency:</label>
    <input type="text" id="agency" placeholder="e.g. IRS, Huntington PD">
    
    <label for="topic">Request Topic:</label>
    <input type="text" id="topic" placeholder="e.g. COVID funds, asset forfeiture">
    
    <label for="name">Your Full Name:</label>
    <input type="text" id="name" placeholder="John Doe">
    
    <label for="address">Your Address:</label>
    <input type="text" id="address" placeholder="123 Liberty St, WV 25705">
    
    <label for="email">Your Email:</label>
    <input type="email" id="email" placeholder="you@example.com">
    
    <button onclick="generateLetter()">Generate FOIA Request</button>
    
    <textarea id="output" rows="20" placeholder="Your FOIA request will appear here..."></textarea>
  </div>

  <script>
    function generateLetter() {
      const agency = document.getElementById('agency').value;
      const topic = document.getElementById('topic').value;
      const name = document.getElementById('name').value;
      const address = document.getElementById('address').value;
      const email = document.getElementById('email').value;

      const today = new Date().toLocaleDateString();

      const letter = `
${today}

To: ${agency}
From: ${name}
Address: ${address}
Email: ${email}

Subject: Freedom of Information Act Request – ${topic}

To Whom It May Concern,

Pursuant to the Freedom of Information Act (5 U.S.C. § 552), I hereby request access to the following records:

All documents, communications, expenditures, and internal memos related to: **${topic}**.

I request that the information be provided in electronic format, and I agree to pay any reasonable fees up to $25. Please inform me if the cost exceeds that amount.

If my request is denied in whole or in part, please justify all deletions by reference to specific exemptions.

Thank you for your time and cooperation.

Sincerely,  
${name}  
${email}
`;

      document.getElementById('output').value = letter.trim();
    }
  </script>
</body>
</html>