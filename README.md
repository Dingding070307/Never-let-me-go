<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Analysis of Never Let Me Go</title>
    <link rel="stylesheet" href="style.css">
    <style>
        .highlight {
            background-color: yellow;
            font-weight: bold;
        }
    </style>
</head>
<body>
    <header>
        <h1>Analysis of Never Let Me Go</h1>
        <input type="text" id="searchInput" onkeyup="searchContent()" placeholder="Search for information...">
    </header>
    <main>
        <section id="content">
            <div class="content-item">
                <h2>1. Setting</h2>
                <h3>Hailsham School</h3>
                <p><strong>Meaning:</strong> Hailsham School is the main setting of the story. While it appears to be a typical boarding school, as the story progresses, the dark truth about its purpose is revealed.</p>
                <p><strong>Direct Quote:</strong> "And I’m a Hailsham student—which is enough by itself sometimes to get people’s backs up." — Kathy H. (p.3)</p>
                <p><strong>Impact:</strong> Hailsham symbolizes a false sense of protection, hiding the true nature of the students' identity. It shapes the main characters' thoughts and behavior, especially their feelings of helplessness and acceptance when confronted with death.</p>
            </div>
            
            <div class="content-item">
                <h3>Pavilion</h3>
                <p><strong>Meaning:</strong> Pavilion is a place to watch events; children assemble together jockeying and arguing.</p>
                <p><strong>Direct Quote:</strong> "The pavilion had become the place to hide out with your best friends when you wanted to get away from the rest of Hailsham." — Kathy H.</p>
                <p><strong>Impact:</strong> Pavilion was the first place Tommy was bullied. This place is a secret spot where children peep things happening in the field, symbolizing snooping and hidden truths.</p>
            </div>

            <div class="content-item">
                <h2>2. Characters</h2>
                <h3>Kathy H.</h3>
                <p><strong>Characteristics:</strong> Reflective, emotional, and introspective.</p>
                <p><strong>Motivation:</strong> Kathy seeks to understand and come to terms with her past, and her relationship with Tommy and Ruth.</p>
                <p><strong>Key Moment:</strong> "I think I was always looking for that thing, that moment when it would all be sorted out." — Kathy H. (Chapter 2, Page 29)</p>
            </div>
            
            <div class="content-item">
                <h2>3. Themes</h2>
                <h3>Friendship</h3>
                <p>Friendship is essential to the story. The narrator, Kathy, illustrates her campus life with Ruth and Tommy, showing how their bonds are tested over time.</p>
                <h3>Gender</h3>
                <p>Cloning children lack traditional emotions. They realize differences between genders but understand they cannot have children due to being clones.</p>
            </div>

            <div class="content-item">
                <h2>4. Key Moments</h2>
                <h3>Prelude of Kathy’s Memory</h3>
                <p>In the first chapter, Kathy starts to sort through her memories, trying to find something she lost.</p>
                <h3>Group Bullying Tommy</h3>
                <p>When the children were 12, seniors assembled to bully Tommy. This marks the beginning of his emotional struggles.</p>
                <h3>Ruth's Confession</h3>
                <p>Ruth admits the failure of her relationship with Tommy and realizes that she will never change her fate. This moment is crucial for understanding Ruth's internal struggle and her acceptance of her predetermined future.</p>
            </div>
        </section>
    </main>

    <footer>
        <p>© 2024 Analysis of Never Let Me Go</p>
    </footer>

    <script>
        function searchContent() {
            const input = document.getElementById('searchInput').value.toLowerCase();
            const content = document.getElementById('content');
            const items = content.querySelectorAll('.content-item');

            items.forEach(item => {
                const text = item.innerHTML;
                item.innerHTML = text.replace(/<span class="highlight">|<\/span>/g, ''); // 清除之前的高亮
                if (input.trim() !== '' && item.textContent.toLowerCase().includes(input)) {
                    const regex = new RegExp(input, 'gi');
                    item.innerHTML = item.innerHTML.replace(regex, match => `<span class="highlight">${match}</span>`);
                    item.style.display = 'block';
                } else if (input.trim() === '') {
                    item.style.display = 'block'; // 输入为空时显示所有内容
                } else {
                    item.style.display = 'none'; // 不匹配时隐藏
                }
            });
        }
    </script>
</body>
</html>
