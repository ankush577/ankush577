<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Random Employee Greeting</title>
    <style>
        body {
            overflow: hidden;
            display: flex;
            align-items: center;
            justify-content: center;
            height: 100vh;
            margin: 0;
            color: white;
            font-family: 'Arial', sans-serif;
            text-align: center;
        }

        #message {
            background-color: rgba(0, 0, 0, 0.5);
            padding: 20px;
            border-radius: 10px;
        }

        video {
            position: fixed;
            top: 50%;
            left: 50%;
            min-width: 100%;
            min-height: 100%;
            width: auto;
            height: auto;
            z-index: -1;
            transform: translateX(-50%) translateY(-50%);
        }
    </style>
</head>
<body>
    <video autoplay muted loop>
        <source src="Video.mp4" type="video/mp4">
        Your browser does not support the video tag.
    </video>

    <div id="message">
        <h1>Hello <span id="employeeName"></span>,</h1>
        <p>We wish you a very happy Merry Christmas!</p>
    </div>

    <script>
        // Array of employee names
        var employeeNames = [
           "Rakesh Zanje",
            "Swapnil Devale",
            "Laxman Dige",
            "Rutuja Borkar",
            "Janet Bernard",
            "Saurabh Shinde",
            "Ramchandra Dige",
            "Prajwal Nirmal",
            "Pramod Dige",
            "Mohmmadsharif A Nadaf",
"Dhanashri Patil",
"Jayesh Waghmare",
"Ravi Anurkar",
"Abhay Singh",
"Namrata Bukshet",
"Prathmesh Sakpal",
"Sonal Palande",
"Prajakta Shendre",
"Deepa Pandey",
"Himanshi Swami",
"Tejas Sakhare" ,
"Simran Gupta ",
"Namrata Singh",
"Ritesh Pundkar",
"Nishtha Lamba",
"Snigdha Sinha ",
"Mahima Sambre",
"Sharmishtha Jatar",
"Shivani Zoting ",
"Ajit Bansod ",
"Swapna Gawale",
"Mayuri Naik ",
"Pooja Bhaisa",
"Akshay Maske",
"Ankita Kondalkar",
"Sandeep Shinde",
"Sanskruti Sathe",
"Abhishek Sable",
"Pooja Badare",
"Vinod Khandare",
"Rhea Gonsalves",
"Lakshay Jain",
"Sneha Vidhate",
"Adriel Mergulhao",
"Aditi Sangle",
"Prashant Jagtap",
"Himanshu Kadam",
"Ankush Deshmukh",
"Vyankatesh Joshi",
"Akshata Pawar",
"Sanket Gokhale",
"Nishita Bhavsar",
"Rajani Ramteke",
"Pradnya More"

            // Add all 50 employee names here
            // ...
        ];

        // Get the stored employee name and unique string from local storage
        var storedEmployeeName = localStorage.getItem("employeeName");
        var uniqueString = localStorage.getItem("uniqueString");

        // If there is no stored employee name, select a random one
        var randomEmployee;
        if (!storedEmployeeName) {
            // Create a unique string to ensure uniqueness
            uniqueString = Math.random().toString(36).substring(2, 15);

            // Select a random employee name
            randomEmployee = employeeNames[Math.floor(Math.random() * employeeNames.length)];

            // Combine the unique string and the random employee name
            randomEmployee = randomEmployee + " (" + uniqueString + ")";

            // Store the combined name in local storage
            localStorage.setItem("employeeName", randomEmployee);
            localStorage.setItem("uniqueString", uniqueString);
        } else {
            // Use the stored employee name
            randomEmployee = storedEmployeeName;
        }

        // Set the employee name in the HTML
        document.getElementById("employeeName").innerText = randomEmployee;
    </script>
</body>
</html>
