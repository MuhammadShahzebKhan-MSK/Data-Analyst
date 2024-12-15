<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Muhammad Shahzeb Khan - Portfolio</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: Arial, sans-serif;
        }
        body {
            color: white;
            text-align: center;
            overflow: hidden;
            height: 100vh;
            display: flex;
            flex-direction: column;
            justify-content: center;
        }
        .background {
            position: fixed;
            top: 0; left: 0;
            width: 100%; height: 100%;
            background: linear-gradient(135deg, #ff9a9e, #fad0c4, #fbc2eb, #a18cd1);
            background-size: 400% 400%;
            animation: gradientAnimation 10s ease infinite;
            z-index: -1;
        }
        @keyframes gradientAnimation {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }
        .welcome {
            padding: 10%;
        }
        .enter-button {
            background: white;
            color: black;
            padding: 15px 30px;
            font-size: 1.5em;
            border: none;
            cursor: pointer;
            border-radius: 5px;
            animation: pulse 2s infinite;
        }
        @keyframes pulse {
            0% { transform: scale(1); }
            50% { transform: scale(1.1); }
            100% { transform: scale(1); }
        }
        .main-content {
            display: none;
            opacity: 0;
            transition: opacity 1s ease-in-out;
        }
        .nav {
            display: flex;
            justify-content: center;
            gap: 30px;
            margin: 20px 0;
        }
        .nav a {
            text-decoration: none;
            color: white;
            font-size: 1.5em;
            padding: 10px 20px;
            border: 2px solid white;
            border-radius: 5px;
            transition: all 0.3s ease;
        }
        .nav a:hover {
            background: white;
            color: black;
        }
        .content {
            display: none;
            padding: 50px;
        }
        .active {
            display: block !important;
        }
    </style>
</head>
<body>
    <div class="background"></div>
    <div class="welcome">
        <h1>Welcome to My Portfolio!</h1>
        <h2>This is Muhammad Shahzeb Khan</h2>
        <button class="enter-button" onclick="enterPortfolio()">Enter the World</button>
    </div>

    <div class="main-content" id="mainContent">
        <div class="nav">
            <a href="#home" onclick="showContent('home')">Home</a>
            <a href="#about" onclick="showContent('about')">About Me</a>
            <a href="#projects" onclick="showContent('projects')">My Projects</a>
            <a href="#contact" onclick="showContent('contact')">Contact</a>
        </div>

        <div id="home" class="content active">
            <h2>Home</h2>
            <p>Explore my journey in Data Analysis and AWS-based Data Engineering.</p>
        </div>

        <div id="about" class="content">
            <h2>About Me</h2>
            <p>I am Muhammad Shahzeb Khan, a passionate data analyst with hands-on experience in AWS services like S3, Glue, Athena, and more.</p>
        </div>

        <div id="projects" class="content">
            <h2>My Projects</h2>
            <p>Discover my exciting data projects, including the AWS Data Analytics Pipeline for Free and Low-Cost Food Programs.</p>
        </div>

        <div id="contact" class="content">
            <h2>Contact</h2>
            <p>Get in touch via email or LinkedIn for collaborations and opportunities.</p>
        </div>
    </div>

    <script>
        function enterPortfolio() {
            document.querySelector('.welcome').style.display = 'none';
            const mainContent = document.getElementById('mainContent');
            mainContent.style.display = 'block';
            setTimeout(() => {
                mainContent.style.opacity = 1;
            }, 100);
        }
        function showContent(sectionId) {
            const sections = document.querySelectorAll('.content');
            sections.forEach(section => section.classList.remove('active'));
            document.getElementById(sectionId).classList.add('active');
        }
    </script>
</body>
</html>
