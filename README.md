# **SAM3-Plus-Qwen3.5**

SAM3-Plus-Qwen3.5 is an advanced, experimental computer vision suite that seamlessly integrates Facebook's Segment Anything Model 3 (SAM3) with the Qwen3.5 multimodal reasoning engine. This application provides a highly interactive web interface designed for precision image detection, interactive click-based segmentation, and automated video object tracking. By utilizing SAM3 to generate high-quality candidate masks and leveraging Qwen3.5 to intelligently filter and reason about these proposals based on user-provided text prompts, the tool ensures highly accurate, context-aware visual grounding. The suite is fully GPU-accelerated and offers distinct operational modes for both static images and video files, making it an excellent workspace for researchers and developers building sophisticated vision-language workflows.

### **Key Features**

* **Image Detection with AI Filtering:** Combines SAM3's powerful region proposal capabilities with Qwen3.5's reasoning to filter out irrelevant bounding boxes, ensuring the final segmented objects strictly match the user's text prompt. 
* **Automated Video Segmentation:** Processes video files frame-by-frame using SAM3's video tracking model. Users can input text prompts to automatically segment, track, and render mask overlays or bounding boxes onto the video output.
* **Interactive Click Segmentation:** Features an interactive image canvas where users can click directly on target objects. The SAM3 tracker instantly generates and overlays precise segmentation masks based on cumulative point data.
* **Custom User Interface:** Built on Gradio with a deeply customized, responsive "Steel Blue" theme using advanced CSS. It includes intuitive upload zones, real-time status indicators, and integrated result explanations.
* **Hardware Optimization:** Utilizes dynamic memory management, inference mode, and Flash Attention compatibility to efficiently run complex vision and language models on CUDA-enabled GPUs.

### **Repository Structure**

```text
├── examples/
│   ├── 1.jpg
│   ├── 1V.mp4
│   ├── 2.jpg
│   └── 3.jpg
├── app.py
├── LICENSE.txt
├── pre-requirements.txt
├── README.md
└── requirements.txt
```

### **Installation and Requirements**

To run SAM3-Plus-Qwen3.5 locally, you must configure a Python environment with the following dependencies. A compatible CUDA-enabled GPU is highly recommended to handle the intensive model loads.

**1. Install Pre-requirements**
Run the following command to update pip to the required version before installing the main dependencies:
```bash
pip install pip>=26.0.0
```

**2. Install Core Requirements**
Install the necessary machine learning, computer vision, and UI libraries. You can place these in a `requirements.txt` file and run `pip install -r requirements.txt`.

```text
torch==2.6.0
torchvision==0.21.0
transformers==5.3.0
supervision
scipy
timm
accelerate
gradio
einops
ninja
decord
scikit-learn
scikit-image
matplotlib
modelscope
pycocotools
https://github.com/Dao-AILab/flash-attention/releases/download/v2.7.4.post1/flash_attn-2.7.4.post1+cu12torch2.6cxx11abiFALSE-cp310-cp310-linux_x86_64.whl
opencv-python
sentencepiece
qwen-vl-utils
pillow
kernels
requests
av
hf_xet
```

### **Usage**

Once your environment is set up and the dependencies are successfully installed, you can launch the application by running the main Python script:

```bash
python app.py
```

Upon initialization, the script will load the SAM3 image, tracker, and video models alongside the Qwen3.5 model into your VRAM. Once complete, it will provide a local web address (usually `http://127.0.0.1:7860/`) which you can open in your browser. You can navigate between the different tabs to experiment with text-to-image filtering, video mask propagation, or interactive click-based tracking.

### **License and Source**

* **License:** SAM License (Available at [LICENSE.txt](https://github.com/PRITHIVSAKTHIUR/SAM3-Plus-Qwen3.5/blob/main/LICENSE.txt))
* **GitHub Repository:** [https://github.com/PRITHIVSAKTHIUR/SAM3-Plus-Qwen3.5.git](https://github.com/PRITHIVSAKTHIUR/SAM3-Plus-Qwen3.5.git)
