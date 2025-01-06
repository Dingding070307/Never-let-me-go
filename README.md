<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Never Let Me Go - Notes</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background: linear-gradient(to bottom, #e0f7fa, #bbdefb);
            margin: 0;
            padding: 20px;
            color: #333;
        }
        .container {
            max-width: 1200px;
            margin: auto;
            background: #fff;
            padding: 20px;
            border-radius: 8px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
        }
        .search-bar {
            display: flex;
            justify-content: center;
            margin-bottom: 20px;
        }
        .search-bar input {
            width: 80%;
            padding: 10px;
            font-size: 16px;
            border: 1px solid #ccc;
            border-radius: 4px;
            outline: none;
        }
        .search-bar input:focus {
            border-color: #64b5f6;
            box-shadow: 0 0 5px rgba(100, 181, 246, 0.5);
        }
        .highlight {
            background-color: #ffeb3b;
            padding: 2px;
            border-radius: 4px;
        }
        h1, h2 {
            text-align: center;
            color: #1a237e;
        }
        section {
            margin-bottom: 40px;
        }
        section h3 {
            color: #01579b;
        }
        section p {
            line-height: 1.6;
        }
    </style>
    <script>
        function highlightKeywords() {
            const searchInput = document.getElementById('search').value.toLowerCase();
            const content = document.querySelectorAll('.content');

            content.forEach(paragraph => {
                const text = paragraph.textContent.toLowerCase();
                if (text.includes(searchInput) && searchInput.trim() !== "") {
                    const regex = new RegExp(`(${searchInput})`, 'gi');
                    paragraph.innerHTML = paragraph.textContent.replace(regex, '<span class="highlight">$1</span>');
                } else {
                    paragraph.innerHTML = paragraph.textContent;
                }
            });
        }
    </script>
</head>
<body>
    <div class="container">
        <h1>Never Let Me Go - Study Notes</h1>
        <div class="search-bar">
            <input type="text" id="search" placeholder="Search for keywords..." oninput="highlightKeywords()">
        </div>

        <section>
            <h2>Settings</h2>
            <div class="content">
                <h3>Hailsham</h3>
                <p>
                    "Hailsham. I bet that was a beautiful place." (Page 7)<br>
                    <strong>Explanation:</strong> The donor’s comment reflects how Hailsham is idealized by those who didn’t experience it, contrasting with the students’ complex feelings about their upbringing.
                </p>
                <p>
                    "You were at Hailsham, weren’t you? So is it really true?" (Page 200)<br>
                    <strong>Explanation:</strong> Rumors about Hailsham closing reveal its symbolic importance as a failed attempt to humanize clones and the lingering effects of its legacy.
                </p>
                <p>
                    "I won’t be a carer any more come the end of the year… I’ll have Hailsham with me, safely in my head." (Page 274)<br>
                    <strong>Explanation:</strong> Kathy’s attachment to Hailsham reflects its lasting impact as a source of identity, even as she faces the inevitability of her fate.
                </p>
            </div>
            <div class="content">
                <h3>Fields</h3>
                <p>
                    "You know, Kath, when I used to play football back at Hailsham. I had this secret thing I did… splash, splash, splash." (Page 273)<br>
                    <strong>Explanation:</strong> Tommy’s memory of football at Hailsham symbolizes innocence and fleeting moments of joy before facing their grim destinies.
                </p>
            </div>
            <div class="content">
                <h3>The Pond</h3>
                <p>
                    "Kath, I’ll tell you about it. I’ll be down at the pond after lunch. If you come down there, I’ll tell you." (Page 24)<br>
                    <strong>Explanation:</strong> The pond serves as a meeting point for private and meaningful conversations, reflecting the characters’ need for connection and trust.
                </p>
            </div>
            <div class="content">
                <h3>The Gallery</h3>
                <p>
                    "We came in to find the woman we’d been following talking to a much older woman with silver hair, who seemed to be in charge of the place…" (Page 154)<br>
                    <strong>Explanation:</strong> The gallery’s peaceful and artistic setting contrasts with the clones’ harsh reality, symbolizing hope and identity tied to creativity and self-expression.
                </p>
            </div>
            <!-- Additional sections can be appended here following the same structure -->
        </section>
    </div>
</body>
</html>
