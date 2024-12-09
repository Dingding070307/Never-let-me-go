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
            <div class="content-item" data-keywords="hailsham school setting protection helplessness death">
                <h2>1. Setting</h2>
                <h3>Hailsham School</h3>
                <p><strong>Meaning:</strong> Hailsham School is the main setting of the story. While it appears to be a typical boarding school, as the story progresses, the dark truth about its purpose is revealed.</p>
                <p><strong>Direct Quote:</strong> "And I’m a Hailsham student—which is enough by itself sometimes to get people’s backs up." — Kathy H. (p.3)</p>
                <p><strong>Impact:</strong> Hailsham symbolizes a false sense of protection, hiding the true nature of the students' identity. It shapes the main characters' thoughts and behavior, especially their feelings of helplessness and acceptance when confronted with death.</p>
            </div>
            
            <div class="content-item" data-keywords="pavilion secret snooping bullying hidden truths">
                <h3>Pavilion</h3>
                <p><strong>Meaning:</strong> Pavilion is a place to watch events; children assemble together jockeying and arguing.</p>
                <p><strong>Direct Quote:</strong> "The pavilion had become the place to hide out with your best friends when you wanted to get away from the rest of Hailsham." — Kathy H.</p>
                <p><strong>Impact:</strong> Pavilion was the first place Tommy was bullied. This place is a secret spot where children peep things happening in the field, symbolizing snooping and hidden truths.</p>
            </div>

            <div class="content-item" data-keywords="kathy reflective emotional introspective relationship tommy ruth">
                <h2>2. Characters</h2>
                <h3>Kathy H.</h3>
                <p><strong>Characteristics:</strong> Reflective, emotional, and introspective.</p>
                <p><strong>Motivation:</strong> Kathy seeks to understand and come to terms with her past, and her relationship with Tommy and Ruth.</p>
                <p><strong>Key Moment:</strong> "I think I was always looking for that thing, that moment when it would all be sorted out." — Kathy H. (Chapter 2, Page 29)</p>
            </div>
            
            <div class="content-item" data-keywords="friendship ruth tommy school">
                <h3>Friendship</h3>
                <p>The setting of the story is school. Friendship is essential to constitute the setting. In this case, the narrator, Kathy, illustrates her campus life. During the process, she and her friends Ruth and Tommy are tested by the experiences they go through.</p>
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
                const keywords = item.getAttribute('data-keywords');
                if (keywords && keywords.toLowerCase().includes(input)) {
                    item.style.display = 'block';
                } else {
                    item.style.display = 'none';
                }
            });
        }
    </script>
</body>
</html>
