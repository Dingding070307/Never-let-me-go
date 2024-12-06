<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document Content Search</title>
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
        .section {
            margin-bottom: 20px;
        }
        .section h2 {
            color: #333;
        }
        .section p {
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
        
        <!-- Setting Section -->
        <div class="section" id="setting">
            <h2>1. Setting</h2>
            <h3>Hailsham School</h3>
            <p><strong>Meaning:</strong> Hailsham School is the main setting of the story. While it appears to be a typical boarding school, as the story progresses, the dark truth about its purpose is revealed.</p>
            <p><strong>Direct Quote:</strong> "And I’m a Hailsham student-which is enough by itself sometimes to get people’s backs up. (p.3)" — Kathy H.</p>
            <p><strong>Impact:</strong> Hailsham symbolizes a false sense of protection, hiding the true nature of the students' identity. It shapes the main characters' thoughts and behavior, especially their feelings of helplessness and acceptance when confronted with death.</p>
        </div>
        
        <div class="section">
            <h3>Pavilion</h3>
            <p><strong>Meaning:</strong> Pavilion is a place to watch events; children assemble together jockeying and arguing.</p>
            <p><strong>Direct Quote:</strong> "The pavilion had become the place to hide out with your best friends when you wanted to get away from the rest of Hailsham."</p>
            <p><strong>Impact:</strong> Pavilion was the first place Tommy was bullied. This place is a secret place to peep at things happening in the field, symbolized as a place of snooping.</p>
        </div>

        <!-- Characters Section -->
        <div class="section" id="characters">
            <h2>2. Characters</h2>
            <h3>Kathy H.</h3>
            <p><strong>Characteristics:</strong> Reflective, emotional, and introspective.</p>
            <p><strong>Motivation:</strong> Kathy seeks to understand and come to terms with her past, and her relationship with Tommy and Ruth.</p>
            <p><strong>Key Moment:</strong> "I think I was always looking for that thing, that moment when it would all be sorted out." — Kathy H.</p>
        </div>
        
        <div class="section">
            <h3>Tommy</h3>
            <p><strong>Characteristics:</strong> Testiness, immaturity.</p>
            <p><strong>Motivation:</strong> He is a proactive boy, always worried about his art talent. He wants to involve in group activities.</p>
            <p><strong>Relevant quote:</strong> "But seriously, Kath. No hard feelings, right? I’m awfully sorry. I am, honestly." (p.13)</p>
        </div>

        <!-- Themes Section -->
        <div class="section" id="themes">
            <h2>3. Themes</h2>
            <p><strong>Friendship:</strong> The setting of the story is school. Friendship is essential to constitute the setting. Kathy illustrates her campus life with Ruth and Tommy, and their friendship is tested over time.</p>
            <p><strong>Gender:</strong> Cloning children do not have emotions or feelings, but gradually realize the differences between male and female. They are told they cannot have children because they are clones.</p>
        </div>

        <!-- Key Moments Section -->
        <div class="section" id="key-moments">
            <h2>4. Key Moments</h2>
            <h3>Prelusion of Kathy’s Memory</h3>
            <p>In the first chapter, Kathy starts to sort through her memories, trying to find something she lost.</p>

            <h3>Group Bullying Tommy</h3>
            <p>When the children were 12, seniors assemble to bully Tommy. Kathy and Ruth are witnesses. This event exposes Tommy’s immaturity and explosive personality.</p>

            <h3>Ruth's Confession</h3>
            <p>Ruth admits the failure of her relationship with Tommy and realizes that she will never change her fate.</p>
        </div>
    </div>

    <script>
        function searchDocument() {
            const query = document.getElementById("search-box").value.toLowerCase();
            const sections = document.querySelectorAll(".section p, .section h3");
            
            sections.forEach(section => {
                let text = section.innerHTML.toLowerCase();
                if (query && text.includes(query)) {
                    section.innerHTML = highlightText(section.innerHTML, query);
                } else {
                    section.innerHTML = section.innerHTML.replace(/<span class="highlight">|<\/span>/g, ''); // Remove previous highlights
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
