<div align="center">
  
# Skin Disease Detection
### 18CSC305J - AI
### Domain: Machine Learning / AI
  
</div>

## Overview
A Flask-based skin disease detection project that uses a pre-trained PyTorch model to classify skin images into nine classes. The repository supports both a web interface and command-line prediction.

## Problem Statement
Identify skin conditions and classify them into categories such as dryness, oiliness, acne, vitiligo, and more using computer vision and deep learning.

## Description
This system analyzes skin images and predicts skin condition categories. It is designed to make skin-type identification easier for users by providing an image upload interface and immediate classification results.

## Classes of Skin Diseases

- acanthosis-nigricans
- acne
- acne-scars
- alopecia-areata
- dry
- melasma
- oily
- vitiligo
- warts

![Skin disease classes](102730903-a-set-of-human-skin-conditions-illustration.webp)

## Frontend Preview

![Frontend preview 1](Images/WhatsApp%20Image%202022-01-23%20at%2012.55.42%20PM.jpeg)

![Frontend preview 2](Images/WhatsApp%20Image%202022-01-23%20at%2012.55.42%20PM%20(1).jpeg)

![Frontend preview 3](Images/WhatsApp%20Image%202022-01-23%20at%2012.55.43%20PM.jpeg)

![Frontend result screen](Images/result.jpeg)

![Frontend preview 4](Images/WhatsApp%20Image%202022-01-23%20at%2012.55.43%20PM%20(1).jpeg)

![Frontend preview 5](Images/WhatsApp%20Image%202022-01-23%20at%2012.55.43%20PM%20(2).jpeg)

## Tech Stack

- PyTorch
- torchvision
- Pillow
- Flask
- Werkzeug
- HTML
- CSS
- JavaScript
- Bootstrap

## Model Details

This repository uses a fine-tuned EfficientNet-based model saved in `skin-model-pokemon.pt`.

![EfficientNet family](Images/fam.png)

![EfficientNet-B0 architecture](Images/b0.png)

## Repository Structure

- `run.py` - starts the Flask application
- `predict.py` - runs command-line image prediction
- `skin-model-pokemon.pt` - trained PyTorch model
- `app/` - Flask application package
  - `app/routes.py` - prediction route and upload handling
  - `app/__init__.py` - Flask app configuration
  - `app/templates/index.html` - web UI template
  - `app/static/` - static CSS, JS, and image assets
- `Images/` - images used for README and UI previews
- `requirements.txt` - Python dependency list

## Setup Instructions

### 1. Clone the repository
```bash
git clone https://github.com/your-username/Skin-Disease-Detection-master.git
cd Skin-Disease-Detection-master
```

### 2. Create and activate a virtual environment

Windows:
```powershell
python -m venv venv
venv\Scripts\activate
```

macOS / Linux:
```bash
python3 -m venv venv
source venv/bin/activate
```

### 3. Install dependencies
```bash
pip install -r requirements.txt
```

### 4. Create the uploads folder
The web app stores uploaded images in `app/static/uploads`.

Windows / macOS / Linux:
```bash
mkdir -p app/static/uploads
```

## Run the Web App

### Step-by-step execution
1. Activate the virtual environment.
2. Run the Flask app:
```bash
python run.py
```
3. Open your browser at:
```text
http://127.0.0.1:5000/
```
4. Use the web page to:
- Click **Choose A File**
- Select a skin image
- Click **Submit**
- View the predicted class displayed on the screen

## Run CLI Prediction

Use the command-line interface for single-image prediction:

```bash
python predict.py -m skin-model-pokemon.pt -i "Images/WhatsApp%20Image%202022-01-23%20at%2012.55.42%20PM.jpeg"
```

### Example
```bash
python predict.py -m skin-model-pokemon.pt -i "Images/result.jpeg"
```

## Notes

- `run.py` launches the Flask web app.
- `predict.py` loads the model on CPU using `torch.load(..., map_location=torch.device('cpu'))`.
- The Flask app reads models from `skin-model-pokemon.pt` by default.
- If you are on Windows, use `venv\Scripts\activate` to activate the virtual environment.
- Ensure the uploads directory exists before running the app.

## Troubleshooting

- If the app does not start, confirm dependencies are installed.
- If prediction fails, verify the model file path and image file path.
- For browser upload errors, confirm the form uses `enctype="multipart/form-data"` and `app/static/uploads` is writable.

## Contact
To improve the project, update `app/routes.py` and retrain the model for additional skin classes.
