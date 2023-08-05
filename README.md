# Glitch detection in video games

## Abstract

Video games are programs intended for entertainment. Due to their complexity, there
can be quite a few errors that may be unnoticed and negatively affect a player’s experience.
In this paper I propose a method for detecting glitches in video games that uses specific
techniques from deep learning.

The first step consists in the generation of a synthetic dataset using Unity (Unity perception package). 2500
images from 10 different objects are generated, which are labeled by „Normal”, „Low”,
„Stretched”, „Missing” or „Placeholder”. There are 4 different architectures tested:
ResNet18, ResNet34, ResNet50 and ShuffleNetV2, the best accuracy score for validation
being 99.6%, achieved in only 100 epochs. In addition, throughout the testing period, only 2 of the 250
images used are wrongly labeled by ResNet50 and the precision and recall reach values that
are close to the maximum for each of the 5 classes.

The results are analyzed and compared with those obtained in similar papers.
Furthermore, different aproaches are discussed, where new types of errors or other types of
games and methods specific to artificial intelligence are found.

## Dataset

### One example of each class - bookstore object
![image](https://github.com/NacuAndrei/Glitch-detection-in-video-games/assets/80635358/4f36b9aa-b567-4c3b-8347-ec33a607587a) ![image](https://github.com/NacuAndrei/Glitch-detection-in-video-games/assets/80635358/bb61916b-a718-4cd3-bffb-155290c41cdc) ![image](https://github.com/NacuAndrei/Glitch-detection-in-video-games/assets/80635358/5e06ba45-2ca0-4f03-ba00-b2ef44f25f31)
![image](https://github.com/NacuAndrei/Glitch-detection-in-video-games/assets/80635358/7af0ba9b-2561-4008-ad27-38a7a43820ee) ![image](https://github.com/NacuAndrei/Glitch-detection-in-video-games/assets/80635358/6cc23b37-ea4c-4108-ad52-1f769104a340)

### Random rotations of object
![image](https://github.com/NacuAndrei/Glitch-detection-in-video-games/assets/80635358/b73d48c7-7edb-403b-9c2f-34bb28b90eb7) ![image](https://github.com/NacuAndrei/Glitch-detection-in-video-games/assets/80635358/e4dbfa9e-e4fa-4133-ac8e-3bd66e7bd734)









