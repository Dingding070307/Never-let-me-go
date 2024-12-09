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
            <!-- Setting -->
            <div class="content-item" data-keywords="hailsham school setting protection helplessness death false sense of safety">
                <h2>1. Setting</h2>
                <h3>Hailsham School</h3>
                <p><strong>Meaning:</strong> Hailsham School is the main setting of the story. While it appears to be a typical boarding school, as the story progresses, the dark truth about its purpose is revealed.</p>
            </div>
            
            <!-- Pavilion -->
            <div class="content-item" data-keywords="pavilion secret snooping bullying hidden truths">
                <h3>Pavilion</h3>
                <p><strong>Meaning:</strong> Pavilion is a place to watch events; children assemble together jockeying and arguing.</p>
            </div>

            <!-- Characters -->
            <div class="content-item" data-keywords="kathy reflective emotional introspective relationship tommy ruth">
                <h2>2. Characters</h2>
                <h3>Kathy H.</h3>
                <p><strong>Characteristics:</strong> Reflective, emotional, and introspective.</p>
            </div>
            
            <!-- Themes -->
            <div class="content-item" data-keywords="themes friendship gender relationships identity growing up struggles">
                <h2>3. Themes</h2>
                <h3>Friendship</h3>
                <p>Friendship is essential to the story. The narrator, Kathy, illustrates her campus life with Ruth and Tommy, showing how their bonds are tested over time.</p>
                <h3>Gender</h3>
                <p>Cloning children lack traditional emotions. They realize differences between genders but understand they cannot have children due to being clones.</p>
            </div>

            <!-- Key Moments -->
            <div class="content-item" data-keywords="key moments kathy memory tommy bullying ruth confession fate">
                <h2>4. Key Moments</h2>
                <h3>Prelude of Kathy’s Memory</h3>
                <p>In the first chapter, Kathy starts to sort through her memories, trying to find something she lost.</p>
                <h3>Group Bullying Tommy</h3>
                <p>When the children were 12, seniors assembled to bully Tommy. This marks the beginning of his emotional struggles.</p>
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
                if (keywords && fuzzyMatch(input, keywords.toLowerCase())) {
                    item.style.display = 'block';
                } else {
                    item.style.display = 'none';
                }
            });
        }

        // 模糊匹配函数
        function fuzzyMatch(input, keywords) {
            if (input.trim() === '') return true;

            const searchWords = input.split(' ');
            return searchWords.some(word => {
                return keywords.includes(word) || levenshteinDistance(word, keywords) <= 2;
            });
        }

        // 计算编辑距离（Levenshtein Distance）
        function levenshteinDistance(a, b) {
            const matrix = [];
            for (let i = 0; i <= b.length; i++) {
                matrix[i] = [i];
            }
            for (let j = 0; j <= a.length; j++) {
                matrix[0][j] = j;
            }
            for (let i = 1; i <= b.length; i++) {
                for (let j = 1; j <= a.length; j++) {
                    if (b.charAt(i - 1) === a.charAt(j - 1)) {
                        matrix[i][j] = matrix[i - 1][j - 1];
                    } else {
                        matrix[i][j] = Math.min(
                            matrix[i - 1][j - 1] + 1,
                            Math.min(matrix[i][j - 1] + 1, matrix[i - 1][j] + 1)
                        );
                    }
                }
            }
            return matrix[b.length][a.length];
        }
    </script>
</body>
</html>
