# ChatBot
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Life Skills Chatbot</title>
    <style>
        body {
            font-family: Times New Roman, sans-serif;
            color: #FFFFFF;
            text-align: center;
            margin: 0;
            padding: 0;
            background-color: #000000;
        }
        #chat-container {
            max-width: 600px;
            margin: 20px auto;
            padding: 20px;
            background-color: #000000;
            border-radius: 8px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
        }
        #chat-container h1 {
            margin-top: 0;
            color: #FF0000;
        }
        #chatbox {
            height: 300px;
            overflow-y: auto;
            border: 3px solid #FF0000;
            padding: 10px;
            border-radius: 5px;
            background-color: #454545;
            color: #FFFFFF;
        }
        #user-input {
            width: calc(100% - 15px);
            margin-right: 10px;
            padding: 5px;
            border: 1px solid #FF0000;
            border-radius: 5px;
            font-size: 16px;
            background-color: #000000;
            color: #FFFFFF;
        }
        #send-btn {
            padding: 8px 15px;
            border: none;
            border-radius: 5px;
            background-color: #FF0000;
            color: #fff;
            cursor: pointer;
            font-size: 16px;
            font-family: Times New Roman
        }
        #send-btn:hover {
            background-color: #FF3333;
        }
        footer {
            margin-top: 20px;
            color: #FFFFFF;
        }
    </style>
</head>
<body>
    <div id="chat-container">
        <h1>Welcome to AI Parents</h1>
        <p>Ask me anything about life skills!!</p>
        <div id="chatbox"></div>
        <div>
            <input type="text" id="user-input" placeholder="Type your message...">
            <button id="send-btn">Send</button>
        </div>
        <footer>
            <p>Feel free to contact me if you receive an error!!!</p>
            <p>Email: <a href="mailto:abhijith2005iibe@gmail.com">abhijith2005iibe@gmail.com</a></p>
        </footer>
    </div>

    <script>
        const chatbox = document.getElementById('chatbox');
        const userInput = document.getElementById('user-input');
        const sendBtn = document.getElementById('send-btn');

        function appendMessage(sender, message) {
            const messageElement = document.createElement('div');
            messageElement.innerHTML = `<strong>${sender}: </strong>${message}`;
            chatbox.appendChild(messageElement);
            chatbox.scrollTop = chatbox.scrollHeight;
        }

        function handleUserInput(userMessage) {
            const lowerCaseMessage = userMessage.toLowerCase();
            if (lowerCaseMessage.includes('time management') || lowerCaseMessage.includes('manage time')) {
                appendMessage('Chatbot', 'Time management is essential for success. Prioritize tasks, set goals, and use tools like planners or apps to organize your schedule.');
            } else if (lowerCaseMessage.includes('communication') || lowerCaseMessage.includes('communicate effectively')) {
                appendMessage('Chatbot', 'Improving communication skills is a great way to prepare for the real world! You can practice public speaking, participate in group discussions, or join a debate club.');
            } else if (lowerCaseMessage.includes('problem solving') || lowerCaseMessage.includes('solve problems')) {
                appendMessage('Chatbot', 'Get hands-on experience by working on real-life projects. Identify challenges, brainstorm solutions, and collaborate with others.');
            } else if (lowerCaseMessage.includes('college') || lowerCaseMessage.includes('preparing for college')) {
                appendMessage('Chatbot', 'College is a big change for people, and it is important to approach it at the right angle. I would recommend paying attention, working on time management skills, staying organized , and having a place to go when stress.');
            } else if (lowerCaseMessage.includes('hello') || lowerCaseMessage.includes('hey')) {
                appendMessage('Chatbot', 'Hello!! What do you need help with today?');
            } else if (lowerCaseMessage.includes('job interviews') || lowerCaseMessage.includes('job')) {
                appendMessage('Chatbot', 'At job interviews, it is important to show your best self. Make sure you dress nicely and look confident. Use positive body language and active listening skills when you are not speaking. When you speak make sure to go at an even pace and do not rush through your points. It is okay to be nervous on the inside, but you can do this!!!');
            } else if (lowerCaseMessage.includes('relationships') || lowerCaseMessage.includes('healthy relationships')) {
                appendMessage('Chatbot', 'Healthy Relationships are the foundation of life for many people, and it is essential in keeping your life stable. The first tip in forming healthy relationships is good communication. Communicating can be difficult, but expressing yourself can make your relationships more positive. Another way to form healthy relationships is by creating boundaries, so you do not upset your friends or family by making them think you’re untrustworthy. This goes both ways because you have to create boundaries too and let people know what bothers you. These boundaries led to trust in relationships making them better and healthier. The final reason why healthy relationships are important is that people in them tend to be in a happier place of mind and are not constantly stressing out because they have someone in their lives, they trust.');
            } else if (lowerCaseMessage.includes('healthy diet') || lowerCaseMessage.includes('diet')) {
                appendMessage('Chatbot', 'As a human, it is crucial to maintain a healthy diet. One key factor in maintaining a healthy diet is not skipping breakfast; many people do this to lose weight, but instead, they miss out on essential nutrients that can come from a healthy breakfast. An example of a healthy breakfast would be a lower-sugar cereal with skimmed milk and topped with fruits. Also, reduce saturated fats and sugars as they can increase your cholesterol. The final way to improve your health is by exercising as it reduces your risk of serious health conditions');
            } else if (lowerCaseMessage.includes('budget') || lowerCaseMessage.includes('money')) {
                appendMessage('Chatbot', 'Maintaining a steady income can be challenging, but it is crucial to living a full life. The first step would be creating a budget so you use your money wisely and do not spend on unnecessary things. Secondly, you should put money into a savings account every paycheck so you do not need to take it out of your checking account if unexpected expenses pop up. Thirdly, when you take out loans make sure to pay them back on time so you do not have to worry about paying it back at a higher interest rate. Make sure to keep track of your credit score because you do not want a bad credit score because lenders will see you as a risk.');
            } else {
                // Default response for other questions
                appendMessage('Chatbot', 'I\'m sorry, I don\'t have information on that topic. Feel free to ask me about time management, communication, or other life skills.');
            }
        }

        sendBtn.addEventListener('click', () => {
            const userMessage = userInput.value.trim();
            if (userMessage !== '') {
                appendMessage('You', userMessage);
                handleUserInput(userMessage);
                userInput.value = '';
            }
        });

        // Optional: Allow pressing Enter key to send message
        userInput.addEventListener('keypress', (e) => {
            if (e.key === 'Enter') {
                sendBtn.click();
            }
        });
    </script>
</body>
</html>
