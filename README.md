from flask import Flask, render_template, request

app = Flask(__name__)

# 模拟数据（可以根据需要动态从数据库加载数据）
library_data = {
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

@app.route('/search', methods=['GET', 'POST'])
def search():
    query = request.form.get('query')
    results = search_library_data(query, library_data)
    return render_template('search_results.html', results=results, query=query)

def search_library_data(query, library_data):
    results = {
        "characters": [],
        "settings": [],
        "themes": []
    }
    
    # 在角色中搜索
    for character in library_data["characters"]:
        if query.lower() in character["name"].lower():
            results["characters"].append(character)
    
    # 在设置中搜索
    for setting in library_data["settings"]:
        if query.lower() in setting["location_name"].lower():
            results["settings"].append(setting)
    
    # 在主题中搜索
    for theme in library_data["themes"]:
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
    <title>Library Search</title>
    <link rel="stylesheet" href="{{ url_for('static', filename='styles.css') }}">
</head>
<body>
    <h1>Library Search</h1>
    <form action="/search" method="POST">
        <input type="text" name="query" placeholder="Search for a character, theme, or setting" required>
        <button type="submit">Search</button>
    </form>
</body>
</html>

body {
    font-family: Arial, sans-serif;
    background-color: #f4f4f9;
    color: #333;
    margin: 0;
    padding: 0;
}

h1, h2, h3 {
    color: #2c3e50;
}

form {
    margin-top: 20px;
    text-align: center;
}

input[type="text"] {
    padding: 8px;
    width: 300px;
    font-size: 16px;
}

button {
    padding: 8px 16px;
    font-size: 16px;
    background-color: #3498db;
    color: white;
    border: none;
    cursor: pointer;
}

button:hover {
    background-color: #2980b9;
}

ul {
    list-style-type: none;
    padding: 0;
}

li {
    padding: 10px;
    border-bottom: 1px solid #ddd;
}

p {
    font-size: 14px;
    color: #7f8c8d;
}
