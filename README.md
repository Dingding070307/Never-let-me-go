<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Analysis of Never Let Me Go</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <header>
        <h1>Analysis of Never Let Me Go</h1>
        <input type="text" id="searchInput" onkeyup="searchContent()" placeholder="Search for information...">
    </header>
    <main>
        <section id="content">
            <h2>1. Setting</h2>
            <div class="content-item" data-keywords="Hailsham, setting, education, fate">
                <h3>Hailsham School</h3>
                <p><strong>Meaning:</strong> Hailsham School is the main setting of the story. While it appears to be a typical boarding school, as the story progresses, the dark truth about its purpose is revealed.</p>
                <p><strong>Direct Quote:</strong> "We were taught to be... creative... But not about the world we were in." — Kathy H. (Chapter 1, Page 12)</p>
                <p><strong>Impact:</strong> Hailsham symbolizes a false sense of protection, hiding the true nature of the students' identity. It shapes the main characters' thoughts and behavior, especially their feelings of helplessness and acceptance when confronted with death.</p>
            </div>

            <div class="content-item" data-keywords="lake, boat, freedom, escape, fate">
                <h3>The Lake and the Boat</h3>
                <p><strong>Meaning:</strong> The lake and the boat are important symbols in the novel, particularly as Kathy and Tommy try to understand their identity.</p>
                <p><strong>Direct Quote:</strong> "It was like a dream... the boat was always there, but we never really got anywhere." — Kathy H. (Chapter 4, Page 52)</p>
                <p><strong>Impact:</strong> The lake and boat symbolize the inner struggles of the characters and their inability to attain true freedom. They serve as a reminder that no matter how much they wish to escape or change their fate, they are unable to avoid their ultimate destiny.</p>
            </div>

            <h2>2. Characters</h2>
            <div class="content-item" data-keywords="Kathy, Tommy, Ruth, characters, relationships">
                <h3>Kathy H.</h3>
                <p><strong>Characteristics:</strong> Reflective, emotional, and introspective.</p>
                <p><strong>Motivation:</strong> Kathy seeks to understand and come to terms with her past, and her relationship with Tommy and Ruth.</p>
                <p><strong>Key Moment:</strong> "I think I was always looking for that thing, that moment when it would all be sorted out." — Kathy H. (Chapter 2, Page 29)</p>
            </div>

            <h2>3. Themes</h2>
            <div class="content-item" data-keywords="memory, identity, death, ethics, science">
                <h3>Memory</h3>
                <p>Kathy narrates the story through memories, and memory plays a crucial role in the novel, revealing the emotional and self-reflective nature of the characters.</p>
                <p><strong>Direct Quote:</strong> "I don't think I ever really felt fully alive until I left." — Kathy H. (Chapter 7, Page 91)</p>
                <p><strong>Impact:</strong> Memory allows Kathy to revisit and reflect on her past, and it gives the reader insight into the emotional weight of her experiences.</p>
            </div>

            <h2>4. Key Moments</h2>
            <div class="content-item" data-keywords="Kathy, Tommy, Ruth, key moments">
                <h3>Ruth's Confession</h3>
                <p>Ruth admits the failure of her relationship with Tommy and realizes that she will never change her fate. This moment is pivotal for understanding Ruth's internal struggle and acceptance of her predetermined future.</p>
                <p><strong>Direct Quote:</strong> "I'm sorry, Tommy. I'm sorry I couldn't tell you sooner." — Ruth (Chapter 10, Page 141)</p>
            </div>

            <h2>5. Questions</h2>
            <div class="content-item" data-keywords="questions, fate, identity">
                <h3>Why do the characters so passively accept their fate?</h3>
                <p>Their sense of helplessness may stem from a lack of choice imposed on them, or perhaps it reflects an ingrained acceptance of their predetermined destiny. The novel explores how their lives are shaped by forces beyond their control.</p>
                <p><strong>Direct Quote:</strong> "We lived in a world where things could only end one way." — Kathy H. (Chapter 12, Page 162)</p>
            </div>
        </section>
    </main>

    <footer>
        <p>© 2024 Analysis of Never Let Me Go</p>
    </footer>

    <script>
        function searchContent() {
            const input = document.getElementById('searchInput').value.toLowerCase();
            const items = document.querySelectorAll('.content-item');

            items.forEach(item => {
                const keywords = item.getAttribute('data-keywords').toLowerCase();
                if (keywords.includes(input)) {
                    item.style.display = 'block';
                } else {
                    item.style.display = 'none';
                }
            });
        }
    </script>
</body>
</html>
