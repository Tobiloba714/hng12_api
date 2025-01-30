from flask import Flask, jsonify
from flask_cors import CORS
from datetime import datetime

# Initialize Flask app
app = Flask(__name__)

# Enable CORS for all origins
CORS(app)

# Define API route
@app.route("/", methods=["GET"])
def get_info():
    response = {
        "email": "samoladapoelisha@gmail.com", 
        "current_datetime": datetime.utcnow().isoformat() + "Z", 
        "github_repo_url": "https://github.com/Tobiloba714/hng12_api"  
    }
    return jsonify(response)


if __name__ == "__main__":
    app.run(debug=True, host="0.0.0.0", port=5000)  
