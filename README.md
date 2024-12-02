# GALURA - Galucoma Detection with Advanced Retinal Analysis

## Project Description
Glaura is an AI CNN model that can detect galucoma.........

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
| RAM | 15 GB |

## Dataset
This is an improved machine-learning-ready glaucoma dataset using a balanced subset of standardized fundus images from the Rotterdam EyePACS AIROGS set. This dataset is split into training, validation, and test folders which contain 4000 (~84%), 385 (~8%), and 385 (~8%) fundus images in each class respectively. Each training set has a folder for each class: referable glaucoma (RG) and non-referable glaucoma (NRG).

| ![RG](Pictures/EyePACS-Glaucoma-57.jpg "RG") | ![NRG](Pictures/EyePACS-NRG-37.jpg "NRG") |
| --- | --- |
| **RG (Referable Glaucoma)** | **NRG (Non-Referable Glaucoma)** |

- Link: [Click here](https://www.kaggle.com/datasets/deathtrooper/glaucoma-dataset-eyepacs-airogs-light-v2)

## Results
### Model Performance

#### 1. Metrics
Accuracy, precision, f1 score, and recall metrics are used as model benchmarks. For comparison, several models were also created.

| Model | Accuracy | Precision | Recal | F1 Score| Note |
| ----- | -------- | --------- | ----- | ------- | ---- |
| DenseNet169 | 92.5% | 89.2% | 96.8% | 92.9% | with augmentation (rotation between -20 until 20 deg, horizontal flip) |
| DenseNet121 | 93.3% | 93.9% | 92.7% | 93.3% | with augmentation (rotation between -20 until 20 deg, horizontal flip) |
| ResNet50 | 93.3% | 91.3% | 95.8% | 93.5% | with augmentation (rotation between -20 until 20 deg, horizontal flip, noise) |
| Glaura | % | % | % | % | with augmentation (rotation between -20 until 20 deg, horizontal flip) |
| DenseNet169 | 93.8% | 91% | 97.4% | 94.1% | without augmentation |
| ResNet50 | % | % | % | % | without augmentation |
| Glaura | 91.3% | 89.8% | 93.3% | 91.5% | without augmentation |



#### 2. Ablation Study
here are some experiments and hyperparameter tuning on the main model (Glaura)

| layer_A | layer_B | layer_C | layer_D | layer_E | Layer_F | Layer_G | layer_H | layer_I | layer_J | layer_K | layer_L | layer_M | layer_N | layer_O | layer_P | layer_Q | layer_R | layer_S | layer_T | layer_U | layer_V | layer_W | layer_X | layer_Y | layer_Z | Accuracy | Precision |
| ------- | ------- | ------- | ------- | ------- | ------- | ------- | ------- | ------- | ------- | ------- | ------- | ------- | ------- | ------- | -------- | -------- | -------- | -------- | -------- |  -------- |  -------- |  -------- |  -------- |  -------- |  -------- |  -------- |  -------- |
| Conv2D(32, (3, 3)), BatchNorm, MaxPooling(2,2)  | Conv2D(64, (3, 3)), BatchNorm, MaxPooling(2,2)  | Conv2D(128, (3, 3)), BatchNorm, MaxPooling(2,2) | Conv2D(256, (3, 3), BatchNorm, MaxPooling(2,2) | Flatten | Dense(128), Dropout(0.5), BatchNorm | Dense(64), Dropout(0.5), BatchNorm | Dense(32), Dropout(0.5), BatchNorm | Dense(16), Dropout(0.5), BatchNorm | Dense(8), Dropout(0.5), BatchNorm | Dense(4), Dropout(0.5), BatchNorm | Dense(1) | | | | | | | | | | | | | | | 52.6% | 57.1% |
| Conv2D(64, (3, 3)), BatchNorm | Conv2D(32, (3, 3)), MaxPooling(2,2) | Conv2D(128, (3, 3)), BatchNorm | Conv2D(128, (3, 3)), Dropout(0.3) | Conv2D(64, (3, 3)), BatchNorm | Conv2D(64, (3, 3)), Dropout(0.3) | Flatten | Dense(128), Dropout(0.5), BatchNorm | Dense(64), Dropout(0.5), BatchNorm | Dense(32), Dropout(0.5), BatchNorm | Dense(16), Dropout(0.5), BatchNorm | Dense(4) | Dense(1) | 50.3% | 71.4% |

#### 3. Training/Validation Curve
This is the final model's curve of Loss and Accuracy. The curve shows that train and validation is balance enough
![Loss and Accuracy](Pictures/Loss_accuracy_graphic.png)
 
### Testing
![Confussion Matrix](Pictures/Confussion_Matrix.png)

Classification Report:
|             | precision | recall | f1-score | support |
| ----------- | --------- | ------ | -------- | ------- |
|         NRG |      0.93 |   0.89 |    0.91  |     385 |
|         RG  |      0.90 |   0.93 |    0.91  |     385 |
|    accuracy |           |        |    0.91  |     770 |
|   macro avg |      0.91 |   0.91 |    0.91  |     770 |
|weighted avg |      0.91 |   0.91 |    0.91  |     770 |


To ensure model's performance, tests were conducted using new images that the model has never seen before
| Image | Lable | Predict |
| ----  | ----- | ------- |
| [NRG_1.jpg](Pictures/Test/NRG_1.jpg) | NRG | NRG | 
| [NRG_2.jpg](Pictures/Test/NRG_2.jpg) | NRG | RG | 
| [NRG_3.jpg](Pictures/Test/NRG_3.jpg) | NRG | NRG | 
| [NRG_4.jpg](Pictures/Test/NRG_4.jpg) | NRG | NRG | 
| [NRG_5.jpg](Pictures/Test/NRG_5.jpg) | NRG | NRG | 
| [RG_1.jpg](Pictures/Test/RG_1.jpg) | RG | RG | 
| [RG_2.jpg](Pictures/Test/RG_2.jpg) | RG | RG | 
| [RG_3.jpg](Pictures/Test/RG_3.jpg) | RG | RG | 
| [RG_4.jpg](Pictures/Test/RG_4.jpg) | RG | RG | 
| [RG_5.jpg](Pictures/Test/RG_5.jpg) | RG | RG |



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
