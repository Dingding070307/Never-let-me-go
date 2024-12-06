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
                <p><strong>Direct Quote:</strong> "And I’m a Hailsham student—which is enough by itself sometimes to get people’s backs up." — Kathy H. (p.3)</p>
                <p><strong>Impact:</strong> Hailsham symbolizes a false sense of protection, hiding the true nature of the students' identity. It shapes the main characters' thoughts and behavior, especially their feelings of helplessness and acceptance when confronted with death.</p>
            </div>

            <div class="content-item" data-keywords="pavilion, hiding, secrets, bullying">
                <h3>Pavilion</h3>
                <p><strong>Meaning:</strong> Pavilion is a place to watch events; children assemble together jockeying and arguing.</p>
                <p><strong>Direct Quote:</strong> "The pavilion had become the place to hide out with your best friends when you wanted to get away from the rest of Hailsham." — Kathy H.</p>
                <p><strong>Impact:</strong> Pavilion was the first place Tommy was bullied. This place is a secret spot where children peep things happening in the field, symbolizing snooping and hidden truths.</p>
            </div>

            <h2>2. Characters</h2>

            <div class="content-item" data-keywords="Kathy, character, introspective, emotional">
                <h3>Kathy H.</h3>
                <p><strong>Characteristics:</strong> Reflective, emotional, and introspective.</p>
                <p><strong>Motivation:</strong> Kathy seeks to understand and come to terms with her past, and her relationship with Tommy and Ruth.</p>
                <p><strong>Key Moment:</strong> "I think I was always looking for that thing, that moment when it would all be sorted out." — Kathy H. (Chapter 2, Page 29)</p>
            </div>

            <div class="content-item" data-keywords="Tommy, character, immaturity, testiness">
                <h3>Tommy</h3>
                <p><strong>Characteristics:</strong> Testiness, immaturity.</p>
                <p><strong>Motivation:</strong> He is a proactive boy who always worries about his art talent and wants to be involved in group activities.</p>
                <p><strong>Relevant Quote:</strong> “But seriously, Kath. No hard feelings, right? I’m awfully sorry. I am, honestly.” — Tommy (p.13)</p>
            </div>

            <h2>3. Themes</h2>

            <div class="content-item" data-keywords="friendship, gender, cloning">
                <h3>Friendship</h3>
                <p>The setting of the story is a school, where friendship is essential. Kathy, the narrator, illustrates her campus life and her evolving relationship with Ruth and Tommy, showing how their friendship is tested by the events around them.</p>
            </div>

            <div class="content-item" data-keywords="gender, cloning, emotions">
                <h3>Gender</h3>
                <p>The story explores how cloning children, who do not have traditional emotions or feelings, gradually become aware of the differences between males and females. They also realize they cannot have children because they are clones.</p>
            </div>

            <h2>4. Key Moments</h2>

            <div class="content-item" data-keywords="memory, Kathy, lost">
                <h3>Prelude of Kathy’s Memory</h3>
                <p>In the first chapter, Kathy begins to sort through her memories, trying to find something she feels she has lost.</p>
            </div>

            <div class="content-item" data-keywords="bullying, Tommy, growth, maturity">
                <h3>Group Bullying Tommy</h3>
                <p>When the children were 12, seniors assembled to bully Tommy. Kathy and Ruth are witnesses. In this event, Tommy’s immaturity and explosive personality are exposed, marking his early emotional struggles.</p>
            </div>

            <div class="content-item" data-keywords="Ruth, confession, fate">
                <h3>Ruth's Confession</h3>
                <p>Ruth admits the failure of her relationship with Tommy and realizes that she will never change her fate. This moment highlights her acceptance of the inevitable future that awaits her and the other clones.</p>
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
