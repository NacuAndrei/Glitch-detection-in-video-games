# Glitch detection in video games

## Abstract

Video games are programs intended for entertainment. Due to their complexity, there
can be quite a few errors that may be unnoticed and negatively affect a player’s experience.
In this paper I propose a method for detecting glitches in video games that uses specific
techniques from deep learning.
The first step consists in the generation of a synthetic dataset using Unity engine. 2500
images from 10 different objects are generated, which are labeled by „Normal”, „Low”,
„Stretched”, „Missing” or „Placeholder”. There are 4 different architectures tested:
ResNet18, ResNet34, ResNet50 and ShuffleNetV2, the best accuracy score for validation
being 99.6%, achieved in only 100 epochs. In addition, throughout the testing period, only 2 of the 250
images used are wrongly labeled by ResNet50 and the precision and recall reach values that
are close to the maximum for each of the 5 classes.
The results are analyzed and compared with those obtained in similar papers.
Furthermore, different aproaches are discussed, where new types of errors or other types of
games and methods specific to artificial intelligence are found.

This projects is also the thesis for my bachelor's degree in computer science.
