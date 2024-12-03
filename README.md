# GALURA - Galucoma Detection with Advanced Retinal Analysis

## Project Description
Glaura is an AI CNN model that can detect galucoma.

## Contributor
| Full Name | Affiliation | Email | LinkedIn | Role |
|-----------|-------------|-------|----------|------|
| Muhamad Ridwan Firmansyah | Universitas Siliwangi | muhridwanf12@gmail.com | [link](https://www.linkedin.com/in/muhamad-ridwan-firmansyah-a922b5243/) | Team Lead |
| Rahmat Fauzi Prihastanto | Universitas Pamulang | zeekun0910@gmail.com | [link](https://www.linkedin.com/in/rahmat-fauzi-b555a11b2?utm_source=share&utm_campaign=share_via&utm_content=profile&utm_medium=android_app) | Team Member |
| Zakiy Qiros Muhammad | Universitas Negeri Surabaya | zakiyqm@gmail.com | [link](https://www.linkedin.com/in/zakiy-qiros-muhammad-255a46309/) | Team Member |
| Divo Kalama | Universitas Siber Asia | divoakademi@gmail.com | [link](https://www.linkedin.com/in/divokalama/) |Team Member |
| Fadhilah Ishma Diyanah | Universitas Sebelas Maret | fadhilahishma19@gmail.com | [link](https://www.linkedin.com/in/fadhilahishma/) | Team Member |
| Aditia Prathama | PT. Pama Persada Nusantara, Politeknik Negeri Sriwijaya | aditiaprathama01576@gmail.com | - | Team Member |
| Nicholas Dominic | Startup Campus, AI Track | nic.dominic@icloud.com | [link](https://linkedin.com/in/nicholas-dominic) | Supervisor |

## Setup
### Prerequisite Packages (Dependencies)
- pandas==2.1.0
- PIL==11.0.0
- tensorflow==2.17.1

### Environment
Glaura was trained using Google Colab with detailed specifications as follows
| | |
| --- | --- |
| GPU | Nvidia T4 (x1) |
| ROM | 112.6 GB (Available Disk) |
| RAM | 12.7 GB (Usable RAM) |

## Dataset
This is an improved machine-learning-ready glaucoma dataset using a balanced subset of standardized fundus images from the Rotterdam EyePACS AIROGS [1] set. This dataset is split into training, validation, and test folders which contain 4000 (~84%), 385 (~8%), and 385 (~8%) fundus images in each class respectively. Each training set has a folder for each class: referable glaucoma (RG) and non-referable glaucoma (NRG).
<div style="display: flex; align-items: center; justify-content: center;">
  <div style="text-align: center; margin-right: 20px;">
    <img src="EyePACS-Glaucoma-57.jpg" alt="RG (Referable Glaucoma)" width="300">
    <p><strong>RG</strong></p>
  </div>
  <div style="text-align: center;">
    <img src="EyePACS-NRG-37.jpg" alt="NRG (Non-Referable Glaucoma)" width="300">
    <p><strong>NRG</strong></p>
  </div>
</div>


- Link: [Click here](https://www.kaggle.com/datasets/deathtrooper/glaucoma-dataset-eyepacs-airogs-light-v2)

## Results
### Model Performance
Describe all results found in your final project experiments, including hyperparameters tuning and architecture modification performances. Put it into table format. Please show pictures (of model accuracy, loss, etc.) for more clarity.

#### 1. Metrics
Inform your model validation performances, as follows:
- For classification tasks, use **Precision and Recall**.
- For object detection tasks, use **Precision and Recall**. Additionaly, you may also use **Intersection over Union (IoU)**.
- For image retrieval tasks, use **Precision and Recall**.
- For optical character recognition (OCR) tasks, use **Word Error Rate (WER) and Character Error Rate (CER)**.
- For adversarial-based generative tasks, use **Peak Signal-to-Noise Ratio (PNSR)**. Additionally, for specific GAN tasks,
  - For single-image super resolution (SISR) tasks, use **Structural Similarity Index Measure (SSIM)**.
  - For conditional image-to-image translation tasks (e.g., Pix2Pix), use **Inception Score**.

Feel free to adjust the columns in the table below.

| model | epoch | learning_rate | batch_size | optimizer | val_loss | val_precision | val_recall | ... |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| vit_b_16 | 1000 |  0.0001 | 32 | Adam | 0.093 | 88.34% | 84.15% | ... |
| vit_l_32 | 2500 | 0.00001 | 128 | SGD | 0.041 | 90.19% | 87.55% | ... |
| ... | ... | ... | ... | ... | ... | ... | ... | ... | 

#### 2. Ablation Study
Any improvements or modifications of your base model, should be summarized in this table. Feel free to adjust the columns in the table below.

| model | layer_A | layer_B | layer_C | ... | top1_acc | top5_acc |
| --- | --- | --- | --- | --- | --- | --- |
| vit_b_16 | Conv(3x3, 64) x2 | Conv(3x3, 512) x3 | Conv(1x1, 2048) x3 | ... | 77.43% | 80.08% |
| vit_b_16 | Conv(3x3, 32) x3 | Conv(3x3, 128) x3 | Conv(1x1, 1028) x2 | ... | 72.11% | 76.84% |
| ... | ... | ... | ... | ... | ... | ... |

#### 3. Training/Validation Curve
Insert an image regarding your training and evaluation performances (especially their losses). The aim is to assess whether your model is fit, overfit, or underfit.
 
### Testing
Show some implementations (demos) of this model. Show **at least 10 images** of how your model performs on the testing data.

### Deployment (Optional)
Describe and show how you deploy this project (e.g., using Streamlit or Flask), if any.

## Supporting Documents
### Presentation Deck
- Link: https://...

### Business Model Canvas
Provide a screenshot of your Business Model Canvas (BMC). Give some explanations, if necessary.

### Short Video
Provide a link to your short video, that should includes the project background and how it works.
- Link: https://...

## References
Provide all links that support this final project, i.e., papers, GitHub repositories, websites, etc.
- Link: https://...
- Link: https://...
- Link: https://...

## Additional Comments
Provide your team's additional comments or final remarks for this project. For example,
1. ...
2. ...
3. ...

## How to Cite
If you find this project useful, we'd grateful if you cite this repository:
```
@article{
...
}
```

## License
For academic and non-commercial use only.

## Acknowledgement
This project entitled <b>"GALURA - Galucoma Detection with Advanced Retinal Analysis"</b> is supported and funded by Startup Campus Indonesia and Indonesian Ministry of Education and Culture through the "**Kampus Merdeka: Magang dan Studi Independen Bersertifikasi (MSIB)**" program.
