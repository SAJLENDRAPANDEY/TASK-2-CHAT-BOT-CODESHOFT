<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Basic Chatbot</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f0f0f0;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
        }
        #chatbox {
            width: 400px;
            padding: 20px;
            background-color: white;
            border-radius: 10px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
        }
        #messages {
            height: 200px;
            overflow-y: auto;
            border: 1px solid #ccc;
            padding: 10px;
            margin-bottom: 10px;
        }
        #userInput {
            width: 100%;
            padding: 10px;
            border-radius: 5px;
            border: 1px solid #ccc;
        }
        button {
            width: 100%;
            padding: 10px;
            background-color: #4CAF50;
            color: white;
            border: none;
            border-radius: 5px;
            margin-top: 10px;
            cursor: pointer;
        }
        button:hover {
            background-color: #45a049;
        }
    </style>
</head>
<body>

<div id="chatbox">
    <div id="messages"></div>
    <input type="text" id="userInput" placeholder="Type a message..." />
    <button onclick="sendMessage()">Send</button>
</div>

<script>
    const responses = {
        'hello': 'Hi there!',
        'how are you': 'I\'m doing great, thank you!',
        'bye': 'Goodbye! Have a nice day!',
        'default': 'Sorry, I don\'t understand that.'
    };

    function sendMessage() {
        const userInput = document.getElementById('userInput').value.toLowerCase();
        const messageBox = document.getElementById('messages');

        const userMessage = document.createElement('div');
        userMessage.textContent = 'You: ' + userInput;
        messageBox.appendChild(userMessage);

        const botResponse = document.createElement('div');
        botResponse.textContent = 'Bot: ' + (responses[userInput] || responses['default']);
        messageBox.appendChild(botResponse);

        document.getElementById('userInput').value = '';
        messageBox.scrollTop = messageBox.scrollHeight;
    }
</script>

</body>
</html>
