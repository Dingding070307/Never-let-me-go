<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Never Let Me Go - Analysis</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            line-height: 1.6;
            margin: 0;
            padding: 0;
            background: linear-gradient(to bottom, #ffdde1, #aec6ff); /* 粉蓝渐变背景 */
            color: #333;
        }
        header {
            background: #ff69b4;
            color: #fff;
            padding: 10px 20px;
            text-align: center;
        }
        main {
            padding: 20px;
            max-width: 800px;
            margin: auto;
            background: #fff;
            box-shadow: 0 2px 4px rgba(0,0,0,0.1);
            border-radius: 8px;
        }
        section {
            margin-bottom: 20px;
        }
        h1, h2, h3 {
            color: #444;
        }
        .quote {
            font-style: italic;
            margin: 10px 0;
            padding-left: 15px;
            border-left: 4px solid #ddd;
        }
        footer {
            text-align: center;
            padding: 10px;
            background: #ff69b4;
            color: #fff;
            margin-top: 20px;
        }
        #search-box {
            display: flex;
            justify-content: center;
            margin-bottom: 20px;
        }
        #search-input {
            width: 300px;
            padding: 10px;
            border: 1px solid #ccc;
            border-radius: 5px;
            margin-right: 10px;
        }
        #search-button {
            padding: 10px 20px;
            background: #ff69b4;
            color: #fff;
            border: none;
            border-radius: 5px;
            cursor: pointer;
        }
        #search-button:hover {
            background: #ff1493;
        }
        .highlight {
            background-color: yellow;
            font-weight: bold;
        }
    </style>
</head>
<body>
    <header>
        <h1>Never Let Me Go - Analysis</h1>
    </header>
    <main>
        <div id="search-box">
            <input type="text" id="search-input" placeholder="Enter keyword to search...">
            <button id="search-button">Search</button>
        </div>

        <section id="content">
            <h2>Hailsham</h2>
            <p><strong>“Hailsham. I bet that was a beautiful place.”</strong> (Ishiguro 7)</p>
            <div class="quote">The donor’s comment reflects how Hailsham is idealized by those who didn’t experience it, contrasting with the students’ complex feelings about their upbringing.</div>
            <p><strong>“You were at Hailsham, weren’t you? So is it really true?”</strong> (Page 200)</p>
            <div class="quote">Rumors about Hailsham closing reveal its symbolic importance as a failed attempt to humanize clones and the lingering effects of its legacy.</div>

            <h2>The Pond</h2>
            <p><strong>“Kath, I’ll tell you about it. I’ll be down at the pond after lunch. If you come down there, I’ll tell you.”</strong> (Page 24)</p>
            <div class="quote">The pond serves as a meeting point for private and meaningful conversations, reflecting the characters’ need for connection and trust.</div>

            <h2>Characters</h2>
            <h3>Kathy H.</h3>
            <p><strong>“My name is Kathy H. I’m thirty-one years old, and I’ve been a carer now for over eleven years.”</strong> (Page 4)</p>
            <div class="quote">Kathy’s introduction highlights her reflective and empathetic personality. Her role as a carer emphasizes her dedication to helping others, while also foreshadowing her eventual fate.</div>
        </section>
    </main>
    <footer>
        <p>&copy; 2025 Never Let Me Go Analysis</p>
    </footer>

    <script>
        // 关键词高亮功能
        document.getElementById('search-button').addEventListener('click', function () {
            const keyword = document.getElementById('search-input').value.trim();
            const contentElement = document.getElementById('content');

            if (keyword) {
                // 先移除所有高亮
                contentElement.innerHTML = contentElement.innerHTML.replace(/<span class="highlight">(.*?)<\/span>/g, '$1');

                // 用关键词添加高亮
                const regex = new RegExp(`(${keyword})`, 'gi');
                contentElement.innerHTML = contentElement.innerHTML.replace(regex, '<span class="highlight">$1</span>');
            }
        });
    </script>
</body>
</html>
