<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Rastreio - Plenitude Sabores da Roça</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #ffffff;
            color: #333;
            margin: 0;
            padding: 0;
        }
        .header {
            background-color: #FF914C; /* Cor principal */
            padding: 20px;
            text-align: center;
            color: white;
        }
        .header h1 {
            margin: 0;
            font-size: 32px;
        }
        .container {
            width: 100%;
            max-width: 600px;
            margin: 50px auto;
            padding: 20px;
            text-align: center;
            border-radius: 8px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
            background-color: #fff;
        }
        .input-container {
            margin-bottom: 20px;
        }
        input[type="text"] {
            width: 80%;
            padding: 10px;
            font-size: 16px;
            border: 1px solid #FF914C;
            border-radius: 5px;
            outline: none;
            color: #333;
        }
        input[type="text"]:focus {
            border-color: #FF914C;
        }
        .button {
            background-color: #FF914C;
            color: white;
            padding: 10px 20px;
            font-size: 18px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            transition: background-color 0.3s ease;
        }
        .button:hover {
            background-color: #e5803c;
        }
        .footer {
            margin-top: 50px;
            font-size: 14px;
            color: #777;
        }
        .footer a {
            color: #FF914C;
            text-decoration: none;
        }
        .footer a:hover {
            text-decoration: underline;
        }
    </style>
</head>
<body>

    <div class="header">
        <h1>Rastreio de Encomenda</h1>
        <p>Plenitude Sabores da Roça</p>
    </div>

    <div class="container">
        <h2>Informe seu código de rastreio</h2>
        <div class="input-container">
            <input type="text" id="tracking-number" placeholder="Número de rastreio" />
        </div>
        <button class="button" onclick="trackPackage()">Rastrear</button>
        <p id="error-message" style="color: red; display: none;">Por favor, insira um número de rastreio válido.</p>
    </div>

    <div class="footer">
        <p>Se você tiver algum problema, entre em contato com o suporte <a href="https://wa.me/553191442863">aqui</a>.</p>
    </div>

    <script>
        function trackPackage() {
            var trackingNumber = document.getElementById('tracking-number').value.trim();
            var errorMessage = document.getElementById('error-message');
            
            if (trackingNumber === "") {
                errorMessage.style.display = "block";
                return;
            }

            errorMessage.style.display = "none";

            // Redireciona para o site dos Correios ou outra transportadora com o número de rastreio
            var url = "https://www2.correios.com.br/sistemas/rastreamento/default.jsp?objetos=" + trackingNumber;
            window.open(url, "_blank");
        }
    </script>

</body>
</html>
