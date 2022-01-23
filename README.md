# Revisiting Facial Keypoint Detection – An Efficient Approach Using Deep Neural Networks

### This paper was presented at Big DML,  2021. [FKPD_BigDML_Submission-Final.pdf](https://github.com/sabeesh90/Imputation_vs_Augmentation_Facial_Key_Point_Detection/files/7785657/FKPD_BigDML_Submission-Final.pdf)

[BigDML_Paper96_FKPD_Final.pptx](https://github.com/sabeesh90/Imputation_vs_Augmentation_Facial_Key_Point_Detection/files/7914956/BigDML_Paper96_FKPD_Final.pptx)

### Authors - Pratima Dileep, Bharath Kumar Bolla, Sabeesh E

<img src="https://user-images.githubusercontent.com/48343095/147588912-2c0ca3da-e72e-4120-ab60-9f48bdd9a02c.png"  width="500"  height = "600"/>

<h2> Aim of the Research </h2>
The aim of this paper is to design light weight and faster neural networks. <br>
  - To evaluate Custom CNN with pre trained architectures <br>
  - To evaluate augmentation vs imputation <br>
  - To fine tune Custom CNNs manually and by Auto-Keras Tuner <br>

The paper aims at establishing the superiority of custom CNN over pre trained architectures. Further augmentation techniques are superior to imputation techniques in case of missing values. <br>

The dataset used here is a kaggle dataset and consists of null values. <br>

Null vs Non Null|
:---------------:|
![image](https://user-images.githubusercontent.com/48343095/147589455-c43bf036-ff62-42c6-aab7-3847a48951fd.png)|

<h2> Imputation techniques </h2>
Two types of imputations have been implemented here <br>
- Forward fill imputation <br>
- KNN imputation

<h2> Augmentation </h2>
The following augmentations have been used in our model building.

Augmentation |
:---------------:|
![image](https://user-images.githubusercontent.com/48343095/147589817-f9da9364-5e3d-4a3e-b5eb-2924f887357e.png) |

<h2> Architectures </h2>
The Custom model and pre trained (NasNetmobile/MobilenetV2) architectures are shown below.

Custom tuned and Keras tuned CNN | Pre trained architectures 
:---------------:|:---------------:
![image](https://user-images.githubusercontent.com/48343095/147590287-cbdb04a8-14b5-41fa-8b44-ca852b52f2bf.png)| ![image](https://user-images.githubusercontent.com/48343095/147590295-30c0dd00-f9dc-42c1-b8b4-e1775a27046d.png)

<h2> RMSE - Custom Models vs Pre Trained models </h2>

Custom Models | Pre trained models 
:---------------:|:---------------:
![image](https://user-images.githubusercontent.com/48343095/147590594-832ed776-de3d-4cb6-9c1b-5c10e1474368.png) | ![image](https://user-images.githubusercontent.com/48343095/147590612-21e0046c-b3b8-4229-91d9-20acbc40714d.png)

It is seen that custom models with augmentation fare better than imputation techniques with the least rmse scores. Similarly Fine tuned MobileNetV2 with augmentation has the least RMSE score among transfer learning models and also among Custom models suggesting that augmentation is a more robust technique than just imputation.


<h2> Inference Time / Model parameter</h2>
- Manually tuned custom model has lower inference time on CPU than Keras tuned model <br>
- MobilenetV2 yielded lower RMSE than Manually tuned custom model inspite of increased parameters. This can be attributed to the architectural efficiency of the mobilenet architectures.

Model size|Latency 
:---------------:|:---------------:
![image](https://user-images.githubusercontent.com/48343095/147591158-1deebb28-3cea-464e-b24d-06bc2cfc300f.png) | ![image](https://user-images.githubusercontent.com/48343095/147591144-faa0e66b-cbb4-472c-aa0b-e0bdc241c3bd.png)

