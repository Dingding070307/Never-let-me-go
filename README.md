from flask import Flask, render_template, request

app = Flask(__name__)

# 模拟数据（可以根据需要动态从数据库加载数据）
novel_data = {
    "characters": [
        {"name": "Kathy", "traits": ["reflective", "sensitive"], "relationships": ["Tommy", "Ruth"], "motivations": ["memory", "identity"], "key_moments": ["Reflects on her time at Hailsham", "Sees the tragic end of her classmates"]},
        {"name": "Tommy", "traits": ["impulsive", "passionate"], "relationships": ["Kathy", "Ruth"], "motivations": ["love", "self-discovery"], "key_moments": ["Fights with Kathy", "Discovers the truth about their future"]},
        {"name": "Ruth", "traits": ["manipulative", "dominant"], "relationships": ["Kathy", "Tommy"], "motivations": ["control", "desire"], "key_moments": ["Manipulates Kathy and Tommy's relationship", "Realizes the consequences of her actions"]}
    ],
    "settings": [
        {"location_name": "Hailsham", "significance": "The boarding school where the characters grow up, symbolizing their lost innocence."},
        {"location_name": "The Cottages", "significance": "A place of transition where the characters are forced to confront their future."}
    ],
    "themes": [
        {"name": "Memory", "examples": ["Kathy constantly reflects on her past at Hailsham.", "The characters' memories shape their understanding of their identity."]},
        {"name": "Identity", "examples": ["The characters struggle with the concept of self, as they are created for a specific purpose."]},
        {"name": "Mortality", "examples": ["The looming knowledge of their future deaths affects how the characters live."]}
    ]
}

@app.route('/')
def index():
    return render_template('index.html')

@app.route('/characters')
def characters():
    return render_template('characters.html', characters=novel_data["characters"])

@app.route('/settings')
def settings():
    return render_template('settings.html', settings=novel_data["settings"])

@app.route('/themes')
def themes():
    return render_template('themes.html', themes=novel_data["themes"])

@app.route('/search', methods=['GET', 'POST'])
def search():
    query = request.form.get('query')
    results = search_novel_data(query, novel_data)
    return render_template('search_results.html', results=results, query=query)

def search_novel_data(query, novel_data):
    results = {
        "characters": [],
        "settings": [],
        "themes": []
    }
    
    # 在角色中搜索
    for character in novel_data["characters"]:
        if query.lower() in character["name"].lower():
            results["characters"].append(character)
    
    # 在设置中搜索
    for setting in novel_data["settings"]:
        if query.lower() in setting["location_name"].lower():
            results["settings"].append(setting)
    
    # 在主题中搜索
    for theme in novel_data["themes"]:
        if query.lower() in theme["name"].lower():
            results["themes"].append(theme)
    
    return results

if __name__ == '__main__':
    app.run(debug=True)

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Never Let Me Go</title>
    <link rel="stylesheet" href="{{ url_for('static', filename='styles.css') }}">
</head>
<body>
    <h1>Never Let Me Go</h1>
    <nav>
        <a href="/characters">Characters</a>
        <a href="/settings">Settings</a>
        <a href="/themes">Themes</a>
    </nav>
    <form action="/search" method="POST">
        <input type="text" name="query" placeholder="Search...">
        <button type="submit">Search</button>
    </form>
</body>
</html>

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Characters - Never Let Me Go</title>
    <link rel="stylesheet" href="{{ url_for('static', filename='styles.css') }}">
</head>
<body>
    <h1>Characters</h1>
    <ul>
        {% for character in characters %}
            <li>
                <h2>{{ character.name }}</h2>
                <p><strong>Traits:</strong> {{ character.traits | join(', ') }}</p>
                <p><strong>Relationships:</strong> {{ character.relationships | join(', ') }}</p>
                <p><strong>Motivations:</strong> {{ character.motivations | join(', ') }}</p>
                <p><strong>Key Moments:</strong> {{ character.key_moments | join(', ') }}</p>
            </li>
        {% endfor %}
    </ul>
</body>
</html>

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Settings - Never Let Me Go</title>
    <link rel="stylesheet" href="{{ url_for('static', filename='styles.css') }}">
</head>
<body>
    <h1>Settings</h1>
    <ul>
        {% for setting in settings %}
            <li>
                <h2>{{ setting.location_name }}</h2>
                <p>{{ setting.significance }}</p>
            </li>
        {% endfor %}
    </ul>
</body>
</html>

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Themes - Never Let Me Go</title>
    <link rel="stylesheet" href="{{ url_for('static', filename='styles.css') }}">
</head>
<body>
    <h1>Themes</h1>
    <ul>
        {% for theme in themes %}
            <li>
                <h2>{{ theme.name }}</h2>
                <p>{{ theme.examples | join(', ') }}</p>
            </li>
        {% endfor %}
    </ul>
</body>
</html>

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Search Results</title>
    <link rel="stylesheet" href="{{ url_for('static', filename='styles.css') }}">
</head>
<body>
    <h1>Search Results for "{{ query }}"</h1>

    {% if results.characters %}
        <h2>Characters</h2>
        <ul>
            {% for character in results.characters %}
                <li>{{ character.name }}</li>
            {% endfor %}
        </ul>
    {% endif %}
    
    {% if results.settings %}
        <h2>Settings</h2>
        <ul>
            {% for setting in results.settings %}
                <li>{{ setting.location_name }}: {{ setting.significance }}</li>
            {% endfor %}
        </ul>
    {% endif %}
    
    {% if results.themes %}
        <h2>Themes</h2>
        <ul>
            {% for theme in results.themes %}
                <li>{{ theme.name }}: {{ theme.examples | join(', ') }}</li>
            {% endfor %}
        </ul>
    {% endif %}
</body>
</html>

body {
    font-family: Arial, sans-serif;
    background-color: #f4f4f9;
    color: #333;
    margin: 0;
    padding: 0;
}

h1 {
    color: #5a5a5a;
}

nav a {
    margin: 0 15px;
    text-decoration: none;
    color: #007bff;
}

nav a:hover {
    text-decoration: underline;
}

form {
    margin-top: 20px;
}

ul {
    list-style-type: none;
    padding: 0;
}

li {
    padding: 10px;
    border-bottom

Flask==2.2.2

__pycache__/
instance/
.env
*.pyc
*.pyo
*.pyd
.Python

git init

git add .
git commit -m "Initial commit"
