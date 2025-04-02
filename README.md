<!DOCTYPE html>
<html lang="en">
<heahd>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>VIT Mess Feedback</title>
    <link rel="stylesheet" href="styles.css">
    <link rel="icon" href="https://i.ibb.co/6RXYKDsV/VIT-LOGO-BLACK-removebg-preview.png">
</head>
<body>

    <!-- Navigation -->
    <nav class="navbar">
        <a href="#feedback-form">Feedback</a>
        <a href="#mess-timings">Mess Timings</a>
        <a href="#mess-rules">Mess Rules & Regulations</a>
        <a href="#contact">Contact</a>
    </nav>

    <div class="container">
        <!-- Logo -->
        <img src="https://i.ibb.co/6RXYKDsV/VIT-LOGO-BLACK-removebg-preview.png" alt="VIT Logo" class="logo">
        
        <!-- Feedback Heading -->
        <h1>Help us improve your mess experience by sharing your feedback.</h1>

        <!-- Feedback Form -->
        <section id="feedback-form">
            <form id="feedbackForm" method="POST" action="https://script.google.com/macros/s/AKfycbygVwqIWFjsQBfiTJE6PIkQlltfPOpWx-8WKhDeQFIrXOgPaBu7a7Jn9V2NZki4VZ3l/exec">
                
                <label for="registerNumber">Register Number:</label>
                <input type="text" id="registerNumber" name="register_number" required>

                <label for="studentName">Name of the Student:</label>
                <input type="text" id="studentName" name="student_name" required>

                <label for="blockRoom">Block and Room Number:</label>
                <input type="text" id="blockRoom" name="room_number" required>

                <label for="messName">Name of the Mess:</label>
                <input type="text" id="messName" name="mess_name" required>

                <label for="messType">Type of Mess:</label>
                <select id="messType" name="mess_type" required>
                    <option value="Veg">Veg</option>
                    <option value="Non-Veg">Non-Veg</option>
                    <option value="Special">Special</option>
                    <option value="Night Mess">Night Mess</option>
                </select>

                <label for="category">Category:</label>
                <select id="category" name="category" required>
                    <option value="Quality">Quality</option>
                    <option value="Quantity">Quantity</option>
                    <option value="Hygiene">Hygiene</option>
                    <option value="Mess Timing">Mess Timing</option>
                    <option value="Others">Others</option>
                </select>

                <label for="feedback">Suggestions/Feedback:</label>
                <textarea id="feedback" name="suggestions" rows="4" required></textarea>

              <label for="file">Attach File (JPG, PNG, PDF):</label>

            <input type="file" id="uplofile" name="file" accept=".jpg,.jpeg,.png,.pdf">

                <button type="submit">Submit Your Feedback</button>
            </form>
        </section>

        <!-- Mess Timings -->
        <section id="mess-timings" class="mess-section">
            <h2>Mess Timings</h2>
            <ul>
                <li>Breakfast: 7:00 AM - 9:00 AM</li>
                <li>Lunch: 12:00 PM - 2:00 PM</li>
                <li>Snacks: 4:30 PM - 6:00 PM</li>
                <li>Dinner: 7:00 PM - 9:00 PM</li>
            </ul>
        </section>

        <!-- Mess Rules & Regulations -->
        <section id="mess-rules" class="mess-section">
            <h2>Mess Rules & Regulations</h2>
            <ul>
                <li>Carry your ID card while dining.</li>
                <li>Maintain cleanliness in the mess area.</li>
                <li>Timely arrival for meals is mandatory.</li>
                <li>Wastage of food is strictly discouraged.</li>
                <li>Misconduct with mess staff will result in disciplinary action.</li>
            </ul>
        </section>

        <!-- Contact Section -->
        <section id="contact">
            <h2>Contact Us</h2>
            <p>Email: <a href="mailto:support@vitmess.com">support@vitmess.com</a></p>
            <p>Address: VIT Campus, Mess Office</p>
        </section>

        <!-- Thank You Message (Hidden Initially) -->
        <div id="thankYouMessage" style="display: none;">
            <h2>Thank you for your feedback!</h2>
        </div>
    </div>

    <!-- Footer -->
    <footer>
        <p>© 2025 VIT MESS Suggestions. All rights reserved.</p>
    </footer>

    <script>
       document.getElementById("feedbackForm").addEventListener("submit", function(event) {
    event.preventDefault(); // Prevent default form submission

    let formData = new FormData(this);
    const fileInput = document.getElementById("uplofile").files[0]; // Corrected file input reference

    if (fileInput) {
        const reader = new FileReader();
        reader.readAsDataURL(fileInput);
        reader.onload = function () {
            formData.append("file", reader.result.split(',')[1]); // Convert to Base64
            formData.append("filename", fileInput.name);
            formData.append("filetype", fileInput.type);

            sendData(formData); // Send data after file conversion
        };
    } else {
        sendData(formData); // Send data if no file is selected
    }
});

function sendData(formData) {
    fetch("https://script.google.com/macros/s/AKfycbygVwqIWFjsQBfiTJE6PIkQlltfPOpWx-8WKhDeQFIrXOgPaBu7a7Jn9V2NZki4VZ3l/exec", {  
        method: "POST",
        body: formData
    })
    .then(response => response.json())
    .then(data => {
        if (data.status === "success") {
            document.getElementById("feedbackForm").reset();
            document.getElementById("feedback-form").style.display = "none";
            document.getElementById("thankYouMessage").style.display = "block";
        } else {
            alert("Submission failed: " + data.message);
        }
    })
    .catch(error => {
        console.error("Error:", error);
        alert("Something went wrong! Please try again.");
    });
}


    </script>

</body>
</html>
