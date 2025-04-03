# Assignment 2: Speech Understanding
## Topic : Speech Enhancement and MFCC Feature Extraction and Comparative Analysis of Indian Languages

## Overview
This repository contains the implementation and evaluation of speaker verification and separation using:
- **WavLM Base+ model** for speaker verification.
- **LoRA (Low-Rank Adaptation)** for fine-tuning the model efficiently.
- **ArcFace loss** to enhance speaker discrimination.
- **SepFormer** for speech separation in multi-speaker scenarios.

We evaluate the performance of pre-trained and fine-tuned models on the **VoxCeleb1** and **VoxCeleb2** datasets. Additionally, we analyze the effectiveness of the speaker identification model when applied to speech separation outputs.

---

## Dataset
The dataset consists of **VoxCeleb1** and **VoxCeleb2**, which contain thousands of speech samples for speaker verification tasks.  
🔗 **[Dataset Link](https://mm.kaist.ac.kr/datasets/voxceleb/)**

---

## **Parameter Comparison**
| Model | Total Parameters | Trainable Parameters |
|--------|----------------|---------------------|
| Original | 94,381,936 | 94,381,936 |
| Fine-Tuned (LoRA) | 97,113,044 | 2,731,108 |

## **Results**

### **Performance Metrics for Speaker Verification**
| Model | EER (%) | TAR@1% FAR | Speaker Verification Accuracy (%) |
|--------|---------|------------|--------------------------------|
| Pretrained | 36.69 | 7.26 | 63.29 |
| Fine-Tuned | 18.79 | 18.14 | 81.20 |

Fine-tuning significantly improved speaker verification accuracy.

---

### **Speech Separation Metrics**
| Metric | Value |
|--------|-------|
| SDR (Signal to Distortion Ratio) | 13.00 |
| SIR (Signal to Interference Ratio) | 22.61 |
| SAR (Signal to Artifacts Ratio) | 14.25 |
| PESQ (Speech Quality) | 2.18 |

**Interpretation:** SepFormer effectively separates mixed audio, but introduces some artifacts, leading to moderate speech quality.

---

### **Speech Separation Audio Samples**
<table>
  <tr>
    <th>Mixed Audio</th>
    <th>Separated Audio 1</th>
    <th>Separated Audio 2</th>
  </tr>
  <tr>
    <td>
      <audio controls>
        <source src="./sample_sounds/mix.wav" type="audio/mpeg">
        Your browser does not support the audio element.
      </audio>
    </td>
    <td>
      <audio controls>
        <source src="./sample_sounds/output1.wav" type="audio/mpeg">
        Your browser does not support the audio element.
      </audio>
    </td>
    <td>
      <audio controls>
        <source src="./sample_sounds/output2.wav" type="audio/mpeg">
        Your browser does not support the audio element.
      </audio>
    </td>
  </tr>
</table>

---

## **Comparative Analysis of Indian Languages**
This project also includes an **MFCC-based comparative analysis of 10 Indian languages** to evaluate model performance across different linguistic structures.

| Task | Accuracy (%) |
|------|------------|
| Indian Language Classification | **86.70** |

🔗 **[Dataset Link](https://www.kaggle.com/datasets/hbchaitanyabharadwaj/audio-dataset-with-10-indian-languages)**

---

## **References**
1. T. Bäckström et al., *Introduction to Speech Processing*, 2nd ed., 2022. [Online]. Available: [https://speechprocessingbook.aalto.fi](https://speechprocessingbook.aalto.fi).
2. A. Paszke et al., *PyTorch: An Imperative Style, High-Performance Deep Learning Library*, NeurIPS 2019. [Online]. Available: [https://pytorch.org](https://pytorch.org).
3. E. J. Hu et al., "LoRA: Low-Rank Adaptation of Large Language Models," ICLR, 2022.
4. J. Deng et al., "ArcFace: Additive Angular Margin Loss for Deep Face Recognition," CVPR, 2019.
5. A. Nagrani et al., "VoxCeleb: A Large-Scale Speaker Identification Dataset," *arXiv preprint arXiv:1706.08612*, 2017.
6. J. S. Chung et al., "VoxCeleb2: Deep Speaker Recognition," *arXiv preprint arXiv:1806.05622*, 2018.
7. J. M. Cheng and H. C. Wang, "A Method of Estimating the Equal Error Rate for Automatic Speaker Verification," IEEE, 2004.
8. S. Chen et al., "WavLM: Large-Scale Self-Supervised Pre-Training for Full Stack Speech Processing," IEEE Journal of Selected Topics in Signal Processing, 2022.
9. C. Subakan et al., "Attention is All You Need in Speech Separation," ICASSP, 2021.

---

## **Installation & Usage**
1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/speaker-verification-separation.git
   cd speaker-verification-separation
