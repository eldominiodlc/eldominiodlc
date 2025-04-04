- 👋 Hi, I’m @eldominiodlc
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...

<!---
eldominiodlc/eldominiodlc is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Asistente Anticorrupción</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            padding: 20px;
            background-color: #f4f4f4;
        }
        .container {
            max-width: 600px;
            margin: auto;
            background: white;
            padding: 20px;
            border-radius: 10px;
            box-shadow: 0px 0px 10px rgba(0, 0, 0, 0.1);
        }
        button {
            padding: 10px 15px;
            border: none;
            background: #007BFF;
            color: white;
            cursor: pointer;
            border-radius: 5px;
        }
        button:hover {
            background: #0056b3;
        }
        #output {
            margin-top: 20px;
            font-weight: bold;
        }
    </style>
</head>
<body>
    <div class="container">
        <h2>Asistente Anticorrupción</h2>
        <p>Presiona el botón y describe tu dilema ético.</p>
        <button onclick="startListening()">Hablar</button>
        <p id="output"></p>
    </div>
    
    <script>
        function startListening() {
            const recognition = new (window.SpeechRecognition || window.webkitSpeechRecognition)();
            recognition.lang = 'es-ES';
            recognition.start();
            
            recognition.onresult = function(event) {
                let speechResult = event.results[0][0].transcript;
                document.getElementById("output").innerText = `Pregunta: ${speechResult}`;
                respond(speechResult);
            };
        }
        
        function respond(text) {
            let response = "Es importante actuar con integridad. Siempre elige la transparencia y la ética.";
            const speech = new SpeechSynthesisUtterance(response);
            speech.lang = 'es-ES';
            window.speechSynthesis.speak(speech);
            document.getElementById("output").innerText += `\nRespuesta: ${response}`;
        }
    </script>
</body>
</html>
