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

# Results

### Different architectures
*Learning rate = 10-5, Batch size = 8*

| Architectures / Results  | ResNet18   | ResNet34 | ResNet50 | ShuffleNetV2 |
| :---:                    | :---:      | :---:    | :---:    | :---:        | 
| Accuracy - validation    | 0.99218    | 0.98828  | 0.99609  | 0.99218      |
| Accuracy - training      | 0.9825     | 0.9865   | 0.9875   | 0.9855       |
| Loss - validation        | 0.02982	  | 0.04580	 | 0.03221	| 0.03506|     |
| Loss - training          | 0.04986	  | 0.03738	 | 0.04466	| 0.03784      |
| Best epoch               | 76         | 58       | 43       | 86           |

<br/>

| Precision & Recall |      |         | Precision |             |           |      |         | Recall  |             |           |
| :---:              | :---:| :---:   | :---:     | :---:       | :---:     | :---:| :---:   | :---:   | :---:       | :---:     |
|                    | Low  | Missing | Normal    | Placeholder | Stretched | Low  | Missing | Normal  | Placeholder | Stretched |                                                    
| ResNet18	         | 1.0  | 1.0	    | 0.94      | 1.0	        | 1.0       |	0.94 | 1.0     | 1.0	   | 1.0         | 1.0       |
| ResNet34	         | 0.94 | 1.0     | 0.9412    | 1.0         |	1.0	      | 0.94 | 1.0	   | 0.96	   | 1.0	       | 0.98      |
| ResNet50	         | 0.98	| 1.0	    | 0.98	    | 1.0	        | 1.0       |	0.98 | 1.0     | 0.98    | 1.0         | 1.0       |
| ShuffleNetV2	     | 0.97 |	1.0	    | 0.9074	  | 1.0	        | 1.0	      | 0.94 | 1.0	   | 0.98	   | 1.0         |	0.96     |


### Different optimizers
*Architecture = ShuffleNetV2*

| Optimizers            | Adam    | AdamW   | Adagrad | RMSProp |
| :---:                 | :---:   | :---:   | :---:   | :---:   | 
| Accuracy - validation | 0.99218 | 0.98828 | 0.69921 | 0.99218 |
| Accuracy - training   | 0.9855  | 0.983	  | 0.5965	| 0.9735  |
| Loss - validation	    | 0.03506 | 0.03195 | 1.29849 | 0.04831 |
| Loss - training	      | 0.03784 | 0.04106 | 1.34299 | 0.06966 |
| Best epoch	          | 86      | 85      | 24      | 60      |

### Accuracy evolution during 100 epochs
| *ResNet18* | *ResNet34* |
|:--:|:--:|
| ![image](https://github.com/NacuAndrei/Glitch-detection-in-video-games/assets/80635358/6c9e34a7-8c05-4b62-a1d6-4c97405eb91f)| ![image](https://github.com/NacuAndrei/Glitch-detection-in-video-games/assets/80635358/2fe6a6cf-4816-4d93-9c3e-e08469cbc2eb) |

| *ResNet50* | *ShuffleNetV2* |
|:--:|:--:|
| ![image](https://github.com/NacuAndrei/Glitch-detection-in-video-games/assets/80635358/06c38109-1cf5-4fde-936e-00363e88df42) | ![image](https://github.com/NacuAndrei/Glitch-detection-in-video-games/assets/80635358/d65d99f4-9238-4ffd-a87c-7c56fa6978d2) |

### Confusion matrices
| *ResNet18* | *ResNet34* |
|:--:|:--:|
| ![image](https://github.com/NacuAndrei/Glitch-detection-in-video-games/assets/80635358/9656ddc9-5558-43b9-a6c9-39cff0847d31) | ![image](https://github.com/NacuAndrei/Glitch-detection-in-video-games/assets/80635358/5cf4f802-e520-4d36-a5be-334482274f0e) |

| *ResNet50* | *ShuffleNetV2* |
|:--:|:--:|
| ![image](https://github.com/NacuAndrei/Glitch-detection-in-video-games/assets/80635358/e68b06bf-4de9-42f4-b3b2-11c46c4d9a64) | ![image](https://github.com/NacuAndrei/Glitch-detection-in-video-games/assets/80635358/db81104e-c55d-43f4-a539-8e7b46d0e9c0) |








