<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Share Location</title>
</head>
<body>
    <h1>Ek Click Mein Location Bhejo</h1>
    <button onclick="shareLocation()">Location Share Karo</button>

    <script>
        function shareLocation() {
            if (navigator.geolocation) {
                navigator.geolocation.getCurrentPosition(
                    function(position) {
                        let lat = position.coords.latitude;
                        let lon = position.coords.longitude;
                        let whatsappNumber = "919876543210"; // YAHAN APNA NUMBER DAALO (91 ke saath)
                        let message = `My%20location:%20https://maps.google.com/?q=${lat},${lon}`;
                        let url = `https://wa.me/${whatsappNumber}?text=${message}`;
                        window.open(url, '_blank');
                    },
                    function(error) {
                        alert("Location access nahi mila: " + error.message);
                    }
                );
            } else {
                alert("Yeh browser location support nahi karta.");
            }
        }
    </script>
</body>
</html>
