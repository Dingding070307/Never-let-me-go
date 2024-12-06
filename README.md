<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document Search</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f4f4f4;
        }
        header {
            background-color: #333;
            color: white;
            padding: 10px;
            text-align: center;
        }
        .content {
            padding: 20px;
            background-color: white;
            margin: 20px;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
        }
        .chapter {
            margin-bottom: 20px;
        }
        .chapter h2 {
            color: #333;
        }
        .chapter p {
            font-size: 16px;
        }
        #search-box {
            margin: 20px;
            padding: 10px;
            width: 80%;
            font-size: 16px;
        }
        .highlight {
            background-color: yellow;
        }
    </style>
</head>
<body>
    <header>
        <h1>Document Content Search</h1>
    </header>
    
    <input type="text" id="search-box" placeholder="Enter search keyword..." oninput="searchDocument()">
    
    <div class="content" id="document-content">
        <div class="chapter" id="chapter1">
            <h2>Chapter 1 - Introduction</h2>
            <p>This is the content of the first chapter, which contains basic introductory information. Pages are marked accordingly.</p>
        </div>
        <div class="chapter" id="chapter2">
            <h2>Chapter 2 - In-Depth Analysis</h2>
            <p>In this chapter, we dive deep into key issues. Here is the content for the second chapter.</p>
        </div>
        <div class="chapter" id="chapter3">
            <h2>Chapter 3 - Conclusion</h2>
            <p>This is the content of the third chapter, summarizing the previous sections.</p>
        </div>
    </div>

    <script>
        function searchDocument() {
            const query = document.getElementById("search-box").value.toLowerCase();
            const chapters = document.querySelectorAll(".chapter p");
            
            chapters.forEach(chapter => {
                let text = chapter.innerHTML.toLowerCase();
                if (query && text.includes(query)) {
                    chapter.innerHTML = highlightText(chapter.innerHTML, query);
                } else {
                    chapter.innerHTML = chapter.innerHTML.replace(/<span class="highlight">|<\/span>/g, ''); // Remove previous highlights
                }
            });
        }

        function highlightText(text, query) {
            const regex = new RegExp(`(${query})`, 'gi');
            return text.replace(regex, '<span class="highlight">$1</span>');
        }
    </script>
</body>
</html>
