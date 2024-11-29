from flask import Flask, render_template, request
from fuzzywuzzy import fuzz, process

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

    # 在角色中搜索（模糊匹配）
    for character in library_data["characters"]:
        match_score = fuzz.partial_ratio(query.lower(), character["name"].lower())
        if match_score > 70:  # 设定一个阈值，匹配度超过70%则认为是相关结果
            character["highlighted_name"] = highlight_match(query, character["name"])
            results["characters"].append(character)

    # 在设置中搜索（模糊匹配）
    for setting in library_data["settings"]:
        match_score = fuzz.partial_ratio(query.lower(), setting["location_name"].lower())
        if match_score > 70:
            setting["highlighted_name"] = highlight_match(query, setting["location_name"])
            results["settings"].append(setting)

    # 在主题中搜索（模糊匹配）
    for theme in library_data["themes"]:
        match_score = fuzz.partial_ratio(query.lower(), theme["name"].lower())
        if match_score > 70:
            theme["highlighted_name"] = highlight_match(query, theme["name"])
            results["themes"].append(theme)

    return results

def highlight_match(query, text):
    """高亮显示匹配的查询部分"""
    start = text.lower().find(query.lower())
    if start != -1:
        end = start + len(query)
        return text[:start] + "<mark>" + text[start:end] + "</mark>" + text[end:]
    return text

if __name__ == '__main__':
    app.run(debug=True)
