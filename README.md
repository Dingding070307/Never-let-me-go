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
            background-color: #ffe4e1; /* 粉色背景 */
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
            <p>“Hailsham. I bet that was a beautiful place.” (Ishiguro 7)</p>
            <div class="quote">The donor’s comment reflects how Hailsham is idealized by those who didn’t experience it, contrasting with the students’ complex feelings about their upbringing.</div>
            <p>“You were at Hailsham, weren’t you? So is it really true?” (Page 200)</p>
            <div class="quote">Rumors about Hailsham closing reveal its symbolic importance as a failed attempt to humanize clones and the lingering effects of its legacy.</div>
        </section>

        <section>
            <h2>The Pond</h2>
            <p>“Kath, I’ll tell you about it. I’ll be down at the pond after lunch. If you come down there, I’ll tell you.” (Page 24)</p>
            <div class="quote">The pond serves as a meeting point for private and meaningful conversations, reflecting the characters’ need for connection and trust.</div>
        </section>
    </main>
    <footer>
        <p>&copy; 2025 Never Let Me Go Analysis</p>
    </footer>

    <script>
        // 关键词高亮功能
        document.getElementById('search-button').addEventListener('click', function() {
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
