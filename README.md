<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>FireSafety Pro - Your Safety Resource</title>
    <style>
        /* === Global Styles === */
        :root {
            --primary: #E74C3C;
            --primary-dark: #C0392B;
            --secondary: #3498DB;
            --secondary-dark: #2980B9;
            --accent: #F39C12;
            --accent-dark: #E67E22;
            --light: #ECF0F1;
            --dark: #2C3E50;
            --gray: #95A5A6;
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        body {
            line-height: 1.6;
            color: #333;
        }
        
        .container {
            width: 90%;
            max-width: 1200px;
            margin: 0 auto;
        }
        
        /* === Header & Navigation === */
        header {
            background: white;
            box-shadow: 0 2px 10px rgba(0,0,0,0.1);
            position: sticky;
            top: 0;
            z-index: 100;
        }
        
        nav {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 15px 0;
        }
        
        .logo {
            display: flex;
            align-items: center;
            gap: 10px;
            font-weight: bold;
            font-size: 1.2rem;
        }
        
        .logo i {
            color: var(--primary);
        }
        
        .nav-links {
            display: flex;
            gap: 20px;
            list-style: none;
        }
        
        .nav-links a {
            text-decoration: none;
            color: var(--dark);
            font-weight: 600;
        }
        
        .nav-links a:hover {
            color: var(--primary);
        }
        
        .ai-btn {
            background: var(--accent);
            color: white !important;
            padding: 8px 16px;
            border-radius: 4px;
        }
        
        /* === Hero Section === */
        .hero {
            background: var(--light);
            padding: 60px 0;
        }
        
        .hero-content {
            max-width: 600px;
        }
        
        .hero h1 {
            font-size: 2.5rem;
            margin-bottom: 20px;
            color: var(--dark);
        }
        
        .hero p {
            font-size: 1.1rem;
            margin-bottom: 30px;
            color: var(--gray);
        }
        
        .btn {
            display: inline-block;
            padding: 12px 24px;
            border-radius: 4px;
            font-weight: 600;
            text-decoration: none;
            margin-right: 10px;
        }
        
        .btn-primary {
            background: var(--primary);
            color: white;
        }
        
        .btn-secondary {
            background: var(--secondary);
            color: white;
        }
        
        /* === AI Assistant Section === */
        .ai-assistant {
            padding: 60px 0;
            background: white;
        }
        
        .ai-container {
            max-width: 800px;
            margin: 0 auto;
            border: 1px solid #ddd;
            border-radius: 8px;
            overflow: hidden;
        }
        
        .ai-chat {
            height: 400px;
            padding: 20px;
            overflow-y: auto;
            background: #f9f9f9;
        }
        
        .ai-input {
            display: flex;
            padding: 15px;
            border-top: 1px solid #ddd;
        }
        
        .ai-input textarea {
            flex: 1;
            padding: 12px;
            border: 1px solid #ddd;
            border-radius: 4px;
            resize: none;
        }
        
        .ai-input button {
            margin-left: 10px;
            padding: 0 20px;
            background: var(--primary);
            color: white;
            border: none;
            border-radius: 4px;
            cursor: pointer;
        }
        
        /* === Responsive Design === */
        @media (max-width: 768px) {
            .nav-links {
                display: none;
            }
            
            .hero h1 {
                font-size: 2rem;
            }
            
            .btn {
                display: block;
                width: 100%;
                margin-bottom: 10px;
            }
        }
    </style>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css">
</head>
<body>
    <!-- Header -->
    <header>
        <div class="container">
            <nav>
                <div class="logo">
                    <i class="fas fa-fire-extinguisher"></i>
                    <span>FireSafety Pro</span>
                </div>
                <ul class="nav-links">
                    <li><a href="#">Home</a></li>
                    <li><a href="#">Basics</a></li>
                    <li><a href="#">Emergency</a></li>
                    <li><a href="#">Equipment</a></li>
                    <li><a href="#">FAQs</a></li>
                    <li><a href="#" class="ai-btn">AI Assistant</a></li>
                </ul>
            </nav>
        </div>
    </header>

    <!-- Hero Section -->
    <section class="hero">
        <div class="container">
            <div class="hero-content">
                <h1>Fire Safety Made Simple</h1>
                <p>Learn how to protect yourself, your family, and your property with our easy-to-understand guides.</p>
                <div class="cta-buttons">
                    <a href="#" class="btn btn-primary">Learn Basics</a>
                    <a href="#ai-assistant" class="btn btn-secondary">Ask AI Assistant</a>
                </div>
            </div>
        </div>
    </section>

    <!-- AI Assistant Section -->
    <section class="ai-assistant" id="ai-assistant">
        <div class="container">
            <h2>Fire Safety AI Assistant</h2>
            <p>Ask any fire safety question and get expert advice in simple language.</p>
            
            <div class="ai-container">
                <div class="ai-chat" id="chat-messages">
                    <div class="ai-welcome">
                        <p><strong>AI Assistant:</strong> Hello! I'm your Fire Safety Assistant. Ask me anything about fire prevention, emergency procedures, or safety equipment.</p>
                    </div>
                </div>
                
                <div class="ai-input">
                    <textarea id="user-input" placeholder="Type your fire safety question..."></textarea>
                    <button id="send-btn">Send</button>
                </div>
            </div>
        </div>
    </section>

    <script>
        // AI Integration
        const API_KEY = "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";
        
        document.getElementById('send-btn').addEventListener('click', async function() {
            const userInput = document.getElementById('user-input');
            const chatMessages = document.getElementById('chat-messages');
            
            if (userInput.value.trim() === '') return;
            
            // Add user message to chat
            chatMessages.innerHTML += `
                <div class="user-message">
                    <p><strong>You:</strong> ${userInput.value}</p>
                </div>
            `;
            
            const question = userInput.value;
            userInput.value = '';
            
            // Show typing indicator
            chatMessages.innerHTML += `
                <div class="ai-typing">
                    <p><strong>AI Assistant:</strong> Thinking...</p>
                </div>
            `;
            chatMessages.scrollTop = chatMessages.scrollHeight;
            
            try {
                const response = await fetch('https://api.openai.com/v1/chat/completions', {
                    method: 'POST',
                    headers: {
                        'Content-Type': 'application/json',
                        'Authorization': `Bearer ${API_KEY}`
                    },
                    body: JSON.stringify({
                        model: "gpt-3.5-turbo",
                        messages: [
                            {
                                role: "system",
                                content: "You are a Fire Safety Expert. Provide clear, simple advice about fire prevention, emergency procedures, and safety equipment. Use easy-to-understand language for beginners."
                            },
                            {
                                role: "user",
                                content: question
                            }
                        ],
                        temperature: 0.7
                    })
                });
                
                const data = await response.json();
                const aiResponse = data.choices[0].message.content;
                
                // Remove typing indicator and add AI response
                document.querySelector('.ai-typing').remove();
                chatMessages.innerHTML += `
                    <div class="ai-message">
                        <p><strong>AI Assistant:</strong> ${aiResponse}</p>
                    </div>
                `;
                
                chatMessages.scrollTop = chatMessages.scrollHeight;
            } catch (error) {
                console.error('Error:', error);
                document.querySelector('.ai-typing').remove();
                chatMessages.innerHTML += `
                    <div class="ai-error">
                        <p><strong>AI Assistant:</strong> Sorry, I'm having trouble responding. Please try again later.</p>
                    </div>
                `;
            }
        });
        
        // Allow pressing Enter to send message
        document.getElementById('user-input').addEventListener('keypress', function(e) {
            if (e.key === 'Enter') {
                e.preventDefault();
                document.getElementById('send-btn').click();
            }
        });
    </script>
</body>
</html>
