---
layout: page
title: Contact
permalink: /contact/
---

<form id="contactForm">
    <label for="name">Name:</label>
    <input type="text" id="name" name="name" required>
    
    <label for="email">Email:</label>
    <input type="email" id="email" name="email" required>
    
    <label for="message">Message:</label>
    <textarea id="message" name="message" rows="4" required></textarea>
    <br />
    <button type="button" onclick="sendEmail()">Send</button>
</form>

<div id="confirmationMessage" style="display: none; color: green; margin-top: 10px;"></div>

<script>
    function sendEmail() {
      var xhr = new XMLHttpRequest();
      var form = document.getElementById("contactForm");
      var confirmationMessage = document.getElementById("confirmationMessage");

      var apiUrl = "https://apim.workato.com/davidm397/blog-api-vv1/send-suggestion?api_token=23dc0561fa51f9b2562f6c1964cc45918cbd9cf8ba7553fbc4c686ca84af4f46";
      xhr.open("POST", apiUrl, true);
      xhr.setRequestHeader("Content-Type", "application/json");
    
      xhr.onreadystatechange = function () {
        if (xhr.readyState === 4) {
          if (xhr.status === 200) {
            // Display a success message or handle the response as needed
            console.log(xhr.responseText);
            confirmationMessage.innerText = "Message processed successfully!";
            confirmationMessage.style.display = "block";
            // Hide the form
            form.style.display = "none";
          } else {
            // Handle errors
            console.error("Error:", xhr.status, xhr.statusText);
            confirmationMessage.innerText = "Error processing the message. Please try again later.";
            confirmationMessage.style.color = "red";
            confirmationMessage.style.display = "block";
          }
        }
      };
    
      // Create a JavaScript object with form data
      var formData = new FormData(form);
      var jsonData = {};
      formData.forEach(function (value, key) {
        jsonData[key] = value;
      });
    
      // Convert the JavaScript object to a JSON string
      var jsonString = JSON.stringify(jsonData);
    
      // Send the JSON payload
      xhr.send(jsonString);
    }
</script>