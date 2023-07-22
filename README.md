# Classification of Weeds and Crops using Convolutional Neural Networks

Weeds are one of the major threats in agriculture, as they have the ability to spread quickly and cause significant damage to crop plants by stealing water, vitamins, and minerals. In addition to that, weeds also cause deterioration in soil quality. In order to cope with these challenges, various methods such as mechanical, biological, and predominantly chemical approaches are used for weed control. Especially in today’s agriculture, where sustainability is important, rapid weed detection becomes crucial, so that negative effects can be drastically mitigated. In order to achieve that effectively, deep learning models can play a key role. This particular study aims to train a model that is capable of accurately classifying crops and weeds while discussing used methods.

There are two datasets that are experiments carried out with. DeepWeeds [Olsen et al. 2019, [DeepWeeds GitHub Page](https://github.com/AlexOlsen/DeepWeeds)] is a multi-class dataset and consists of 17,509 Images and 9 classes (8 weed species and 1 non-weed class). 4Weed [Aggarwal et al., 2022] is a Multi-Class dataset and consists of 618 Images and 4 classes. This dataset is used in the study to simulate a real-life situation.

The main purpose of the experiments is to create a robust model and a good baseline that can give the best performance for the DeepWeeds dataset. Various experiments are carried out to see the effects of data augmentation layers, choice of baseline models (between ResNet5* and InceptionV3), fine-tuning methods, specific activation functions, batch normalization layers, and weed-to-weed dataset transfer learning performance. Please see my bachelor's study for detailed experiments and results (can be found below). 

The primary objective of these experiments is to develop a strong and reliable model that can achieve optimal performance on the DeepWeeds dataset. To achieve this, several experiments have been conducted, investigating the impact of various factors. These factors include data augmentation techniques, the choice of baseline models (ResNet50 and InceptionV3), fine-tuning methods, specific activation functions, batch normalization layers, and the performance of the model while applying weed-to-weed transfer learning. For a comprehensive understanding of the experiments and their results, please refer to my bachelor's study, which can be found down below.

The best-performing model, which is called Endgültiges Modell (Final Model) and shared here, has the following features:

* The data augmentation consists of RandomZoom, RandomFlip, RandomRotation, RandomBrightness, and CenterCrop
* Base model is ResNet50, pre-trained on ImageNET.
* The top layer is a dense layer with nine neurons and sigmoid activation function.
* Fine-tuning is carried out by first freezing the base model and only training the upper layer. After a single training process, the layers of the base model are unlocked and the training process is performed again. Namely Top-Then-Full Fine-Tuning.
* Batch Normalization layers are trainable and in training mode.

Architecture of Endgültiges Modell:
<p align="center">
<img width="404" alt="endgultigesmodell" src="https://github.com/rvthx/bachelorarbeit-cropandweed/assets/72575490/7e01b0a9-d957-4775-8a9a-0609ff708b6c">
</p>

The test accuracy of the Endgültiges Modell is 92.32%. 

Full Study (in German): [Bachelorarbeit.pdf](https://github.com/rvthx/bachelorarbeit-cropandweed/files/12136716/Bachelorarbeit.pdf)
