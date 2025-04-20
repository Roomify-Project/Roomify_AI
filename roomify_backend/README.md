# 🧠 Roomify AI Inference API

This is the backend API for Roomify AI model. It allows generating interior design images from an input room photo and a text prompt.

---

## 🔧 Features

- ✅ Accepts image + prompt
- 🎨 Returns a newly generated room design using our custom-trained Conditional GAN
- 🚀 FastAPI-based endpoint for integration with mobile/web apps

---

## 🛠️ Requirements

Install dependencies:

```bash
pip install -r requirements.txt

Make sure to use Python 3.10+ and CUDA-compatible PyTorch for GPU support.


## 🚀 How to Run the API

### 1. Clone the repository or copy the project folder to your server.

Make sure the folder structure is as follows:

Roomify-API/
├── app/
│   ├── __init__.py
│   ├── models/
│   │   ├── generator.py
│   │   ├── clip_encoder.py
│   ├── inference_utils.py
├── main.py
├── requirements.txt
├── README.md

---

### 2. Install the required packages

Use Python 3.10+ and run:

```bash
pip install -r requirements.txt

If you're using Colab or a virtual environment, activate it first.

3. Run the API server

uvicorn app.main:app --reload

The server will start at:

http://127.0.0.1:8000


✅ POST /generate-design
Request:

image: JPG or PNG file of the room (form-data)

prompt: Text describing the design (form-data)

Example (via Postman or frontend):

POST http://127.0.0.1:8000/generate-design

Form-data:

image: (upload image file)

prompt: "Modern living room with wood furniture and natural lighting"

Response:

{
  "generated_path": "temp_outputs/generated_9f7ab3dc.png"
}

You can now access the generated image from the returned path.

💾 Model Checkpoints
Download the latest trained generator checkpoint and place it here:

bash
Copy
Edit
/content/drive/MyDrive/Roomify/checkpoints_512/generator_epoch30.pth
📎 Download Link: 🔗 Google Drive backend Folder https://drive.google.com/drive/folders/1L3X2HU46y1gU17QIAfR63MQT4BfW5Saz?usp=drive_link
checkpoints Folder : https://drive.google.com/drive/folders/1-27vaFCe2TJLYb8rOREKb3r8CVlJUxJP?usp=drive_link

👨‍💻 Developer Notes
The model is based on Conditional UNet GAN

CLIP is used to encode the text prompt

Image size: 512x512


📝 Notes
Model checkpoint must be stored at: checkpoints/generator_epoch30.pth

Generated images will be saved to: temp_outputs/

Inference runs on GPU (cuda) if available.

🤝 Built by Khaled & Roomify Team