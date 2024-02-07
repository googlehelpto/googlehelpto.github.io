<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My Personal Website</title>
</head>
<body>
    <h1>Welcome to My Website!</h1>
    <p id="location"></p>

    <script>
        function showLocation(position) {
            const latitude = position.coords.latitude;
            const longitude = position.coords.longitude;

            const locationElement = document.getElementById("location");
            locationElement.textContent = `Your current location is: Latitude ${latitude}, Longitude ${longitude}`;
        }

        function showError(error) {
            const locationElement = document.getElementById("location");
            locationElement.textContent = `Unable to retrieve your location: ${error.message}`;
        }

        // Check if geolocation is supported by the browser
        if (navigator.geolocation) {
            // Get the user's current position
            navigator.geolocation.getCurrentPosition(showLocation, showError);
        } else {
            const locationElement = document.getElementById("location");
            locationElement.textContent = "Geolocation is not supported by your browser.";
        }
    </script>
</body>
</html>

