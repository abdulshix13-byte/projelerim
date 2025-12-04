<!DOCTYPE html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Lamba Kontrolü</title>
    <script>
        function toggleLamp() {
            // Lamba açma/kapama API'sine isteği gönderiyoruz
            fetch('http://your-api-endpoint/lamba', {
                method: 'POST', 
                body: JSON.stringify({ action: 'toggle' }), // Toggle (aç/kapalı) işlemi
                headers: {
                    'Content-Type': 'application/json'
                }
            })
            .then(response => response.json())
            .then(data => {
                if (data.status === 'success') {
                    alert('Lamba başarılı bir şekilde kontrol edildi!');
                } else {
                    alert('Bir hata oluştu!');
                }
            })
            .catch(error => alert('Bağlantı hatası: ' + error));
        }
    </script>
</head>
<body>
    <h1>Lamba Kontrolü</h1>
    <button onclick="toggleLamp()">Lambayı Aç/Kapat</button>
</body>
</html>
