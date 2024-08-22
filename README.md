<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Simulador de Avião Básico</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #e0e0e0;
            color: #333;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
        }
        .cockpit {
            background-color: #fff;
            border-radius: 8px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
            padding: 20px;
            max-width: 600px;
            width: 100%;
            text-align: center;
        }
        .button {
            background-color: #007BFF;
            color: #fff;
            border: none;
            padding: 10px;
            margin: 5px;
            border-radius: 4px;
            cursor: pointer;
            transition: background-color 0.3s;
        }
        .button:hover {
            background-color: #0056b3;
        }
        #status {
            margin-top: 20px;
            text-align: left;
            height: 100px;
            overflow-y: auto;
            border: 1px solid #ccc;
            padding: 10px;
            background-color: #f9f9f9;
            border-radius: 4px;
        }
    </style>
</head>
<body>
    <div class="cockpit">
        <h1>Simulador de Avião</h1>
        <button class="button" onclick="toggleEngine()">Ligar/Desligar Motor</button>
        <button class="button" onclick="toggleLandingGear()">Pouso/Decolagem</button>
        <button class="button" onclick="toggleLights()">Luzes</button>
        <button class="button" onclick="toggleFlaps()">Flaps</button>
        <div id="status">Status do Avião:</div>
    </div>

    <script>
        let engineOn = false;
        let landingGearDown = false;
        let lightsOn = false;
        let flapsExtended = false;

        function updateStatus() {
            const status = document.getElementById('status');
            status.innerHTML = `
                <p>Motor: ${engineOn ? 'Ligado' : 'Desligado'}</p>
                <p>Trenó de Pouso: ${landingGearDown ? 'Baixado' : 'Recolhido'}</p>
                <p>Luzes: ${lightsOn ? 'Ligadas' : 'Desligadas'}</p>
                <p>Flaps: ${flapsExtended ? 'Estendidos' : 'Recolhidos'}</p>
            `;
        }

        function toggleEngine() {
            engineOn = !engineOn;
            updateStatus();
        }

        function toggleLandingGear() {
            landingGearDown = !landingGearDown;
            updateStatus();
        }

        function toggleLights() {
            lightsOn = !lightsOn;
            updateStatus();
        }

        function toggleFlaps() {
            flapsExtended = !flapsExtended;
            updateStatus();
        }

        updateStatus();
    </script>
</body>
</html>
