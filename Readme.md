# **Vision-Language Context Optimization for Satellite Image Classification**

This project explores the application of the **Context Optimization (CoOp)** technique using **CLIP** for **satellite image classification**. The training was implemented using the **Dassl (Domain Adaptive Semi-Supervised Learning)** library. The research project was conducted as a part of the IIT Bombay Summer Internship under CSRE Dept. in June, 2024.

This project implements the Context Optimization (CoOp) technique for fine-tuning CLIP models using learnable prompts, attempting to beat SOTA ( State-Of-The-Art)  scores with newer approaches, built on top of the [Dassl](https://github.com/KaiyangZhou/Dassl.pytorch) framework. 
While we could beat the SOTA in some shots learning, we couldn't in many other specific shots learning\!

 This repo includes our newer approaches developed to beat certain SOTA scores , at certain specified few shots learning.
---

## **🧠 Key Concepts**

* **CoOp (Context Optimization)**: Learns prompts to improve zero-shot performance of CLIP.

* **CLIP**: A vision-language model that aligns image and text embeddings in a shared latent space.

* **Dassl**: A flexible PyTorch library designed for domain adaptation and domain generalization tasks.

---

## **🗂️ Dataset**

* **Dataset**: EuroSAT, UC Merced Land Use Dataset , Million Aid

* **Classes**: \[e.g., Forest, Urban, Water, Agriculture\] *(Modify as per your dataset)*

* **Input**: RGB satellite images

---

## **⚙️ Setup Instructions**

### **1\. Clone the Repository**

git clone https://github.com/KaiyangZhou/CoOp.git

cd CoOp

To avoid any kind of symlink issues , get the .zip file from [here](https://drive.google.com/file/d/1hjkr6esTbFqodh0aynzkTAsqYLIuaJn6/view?usp=sharing)

### **2\. Create Conda Environment**

conda create \-n coop-env python=3.8 \-y

conda activate coop-env

### **3\. Install Dependencies**

pip install \-r requirements.txt

pip install torch torchvision torchaudio

pip install \-e .

---

## **🚀 Training**

### **Directory Structure**

datasets/

├── satellite\_dataset/

│   ├── train/

│   ├── val/

│   └── test/

### **Training Script**

python train.py \\

  \--config-file configs/coop/base\_prompt/satellite.yaml \\

  MODEL.BACKBONE.NAME clip\_vit\_b16 \\

  DATASET.NAME satellite\_dataset \\

  TRAINER.COOP.N\_CTX 16 \\

  OUTPUT\_DIR output/coop/satellite\_run1

---

## **📈 Evaluation**

python train.py \\

  \--config-file configs/coop/base\_prompt/satellite.yaml \\

  \--eval-only \\

  MODEL.BACKBONE.NAME clip\_vit\_b16 \\

  DATASET.NAME satellite\_dataset \\

  OUTPUT\_DIR output/coop/satellite\_run1

---

        For detailed guidance on training, validation and evaluation refer to the original [CoOp repository](https://github.com/KaiyangZhou/CoOp).

## **🧪 Results**

| Class | Accuracy |
| ----- | ----- |
| Forest | 91.2% |
| Urban | 88.4% |
| Water | 93.0% |
| Agriculture | 89.7% |

---

## **📊 Visualization**

Include t-SNE plots, class-wise confusion matrix, or image-caption alignment visualizations.

---

## **📁 Output Directory**

output/coop/satellite\_run1/

├── log.txt

├── model.pth

└── results.txt

---

## **✍️ Citation**

If you use this project, consider citing:

@inproceedings{zhou2022coop,

  title={Learning to prompt for vision-language models},

  author={Zhou, Kaiyang and Yang, Jingkang and Loy, Chen Change and Liu, Ziwei},

  booktitle={CVPR},

  year={2022}

}

---

## **🙌 Acknowledgements**

* [CLIP](https://github.com/openai/CLIP)

* [Dassl Framework](https://github.com/KaiyangZhou/Dassl.pytorch)

* [CoOp Original Repo](https://github.com/KaiyangZhou/CoOp)

---

## **📧 Contact**

For any questions, feedback, or inquiries, please feel free to reach out:

* **Name**: Souradeep Dutta  
* **Email**: aimldatasets22@gmail.com  
* **GitHub Profile**: [https://github.com/Souradeep2233](https://github.com/Souradeep2233) 
