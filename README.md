# mywebsite11
<!DOCTYPE html>
<html lang="uk">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Мій сайт</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <header>
        <h1>Ласкаво просимо на мій сайт!</h1>
    </header>

    <main>
        <p>карти онлайн .</p>
    </main>

    <footer>
        <p>© 2024 </p>
    </footer>
</body>
</html>
<!DOCTYPE html>

<html lang="en" xmlns="http://www.w3.org/1999/xhtml">
<head>
    <meta charset="utf-8" />
    <title></title>
</head>
<body>

</body>
</html>
<!DOCTYPE html>
<html lang="uk">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Мій сайт з картою</title>
    <link rel="stylesheet" href="styles.css">
    <script src="https://maps.googleapis.com/maps/api/js?key=AIzaSyBzugdppwpG0ngM4OKKHyJoDvzp4DCs5kw&callback=initMap" async defer></script>
    <style>
        #map {
            height: 400px; /* Висота карти */
            width: 100%; /* Ширина карти */
        }
    </style>
</head>
<body>
    <header>
        <h1>Мапа та маркери</h1>
    </header>

    <main>
        <div id="map"></div>
    </main>

    <footer>
        <p>© 2024 Мій сайт</p>
    </footer>

    <script>// Ініціалізація карти
        function initMap() {
            // Створюємо об'єкт карти, вказуємо центр та рівень масштабування
            const mapOptions = {
                center: { lat: 50.4501, lng: 30.5236 }, // Київ
                zoom: 12, // Початковий рівень масштабування
            };

            // Створення карти
            const map = new google.maps.Map(document.getElementById('map'), mapOptions);

            // Додавання маркерів
            const locations = [
                { lat: 50.4501, lng: 30.5236, title: 'Київ' }, // Київ
                { lat: 50.4454, lng: 30.5142, title: 'Майдан Незалежності' }, // Майдан
            ];

            locations.forEach(location => {
                const marker = new google.maps.Marker({
                    position: { lat: location.lat, lng: location.lng },
                    map: map,
                    title: location.title
                });

                // Додавання інформаційного вікна при натисканні на маркер
                const infoWindow = new google.maps.InfoWindow({
                    content: `<h3>${location.title}</h3>`
                });

                marker.addListener('click', () => {
                    infoWindow.open(map, marker);
                });
            });
        }</script>
</body>
</html>

