# Kurjuuden-maksimointi
Kurjuuden maksimointi budjettisäästö

<!DOCTYPE html>
<html lang="fi">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Kurjuuden Maksimointi</title>
    <script src="https://cdn.tailwindcss.com"></script>
</head>
<body class="bg-gray-100 flex items-center justify-center min-h-screen">
    <div class="bg-white p-6 rounded-lg shadow-lg w-full max-w-md">
        <h1 class="text-2xl font-bold text-center mb-4">Kurjuuden Maksimointi</h1>
        <p class="text-center mb-6">Valitse kategoria, ja appi arpoo sinulle budjetin!</p>
        
        <div class="mb-4">
            <label for="category" class="block text-sm font-medium text-gray-700">Valitse kategoria:</label>
            <select id="category" class="mt-1 block w-full p-2 border border-gray-300 rounded-md">
                <option value="kioski">Kioski (2€ - 7€)</option>
                <option value="kauppareissu">Kauppareissu (20€ - 30€)</option>
                <option value="isompi_ostos">Isompi ostos (50€ - 100€)</option>
            </select>
        </div>
        
        <button onclick="arvoBudjetti()" class="w-full bg-blue-500 text-white p-2 rounded-md hover:bg-blue-600">
            Arvo budjetti
        </button>
        
        <div id="tulos" class="mt-6 text-center text-lg font-semibold"></div>
    </div>

    <script>
        function arvoBudjetti() {
            const category = document.getElementById('category').value;
            let min, max;

            if (category === 'kioski') {
                min = 2;
                max = 7;
            } else if (category === 'kauppareissu') {
                min = 20;
                max = 30;
            } else if (category === 'isompi_ostos') {
                min = 50;
                max = 100;
            }

            const budjetti = Math.floor(Math.random() * (max - min + 1)) + min;
            document.getElementById('tulos').innerText = `Sinun budjettisi: ${budjetti}€`;
        }
    </script>
</body>
</html>
