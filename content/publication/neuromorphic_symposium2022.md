---
title: "The 4th International Symposium on Neuromorphic AI Hardware"
date: 2022-12-08T10:52:03+09:00
---
## Deep Learning Method on Word Level American Sign Language Recognition from Video 
### Arie Rachmad Syulistyo1, Yuichiro Tanaka2, and Hakaru Tamukoh1,2
#### 1 Graduate School of Life Science and Systems Engineering, Kyushu Institute of Technology
#### 2-4 Hibikino, Wakamatsu, Kitakyushu, 808-0196, Japan
#### 2 Research Center for Neuromorphic AI Hardware, Kyushu Institute of Technology
#### 2-4 Hibikino, Wakamatsu, Kitakyushu, 808-0196, Japan
 
Recently, the number of American sign language (ASL) learners is increasing and there are many materials of sign language such as video and software that can be installed in handphones. However, people that learn from that materials cannot study sign language sufficiently because they cannot check their gestures. Therefore, this study aims to develop an embedded ASL recognition system that is high accuracy and requires low computational costs so that ASL learners can check their gestures with their handphones. The contribution of this study is investigating an appropriate neural network structure for the embedded ASL recognition system. This system uses the MediaPipe library [1] to extract the keypoint from an image then this feature is processed by either long-short term memory (LSTM), bidirectional LSTM (BiLSTM), gated recurrent unit (GRU), or bidirectional GRU (BiGRU) based neural network. We investigated the system accuracy and computation time changing the network construction using a ten-class ASL dataset, where 18 videos are included for each class, randomly chosen from the WLASL dataset [2]. Based on the experimental results shown in Table 1, GRU1, GRU2 and BiGRU1 have the best results compared to other algorithms and the GRU-based methods require lower computational costs than the BiGRU-based methods. However, all these algorithms require high computational resources, and therefore, we need an algorithm with low computational resources such as reservoir computing for embedded systems. 
Table 1. Experiment Result
|     Method     |     Architecture                                                |     Accuracy    |     Time (Sec)    |
|----------------|-----------------------------------------------------------------|-----------------|-------------------|
|     LSTM1      |     2 LSTM + 3 Dense layers                                     |     44%         |     0.38          |
|     LSTM2      |     2 LSTM + Dropout + 3 Dense layers                           |     33%         |     0.39          |
|     BiLSTM1    |     2 BiLSTM + 3 Dense layers                                   |     33%         |     0.65          |
|     BiLSTM2    |     2 BiLSTM + 2 Dropout + 3 Dense layers                       |     33%         |     0.65          |
|     GRU1       |     3 {GRU + Dense} + BatchNorm + 1 Dense layer                 |    **_56%_**         |     0.44          |
|     GRU2       |     3 {GRU + Dropout + Dense} + BatchNorm + 1 Dense layer       |     **_56%_**         |     0.45          |
|     BiGRU1     |     3 {BiGRU + Dense} + BatchNorm. + 1 Dense layer              |     **_56%_**         |     0.75          |
|     BiGRU2     |     3 {BiGRU + Dropout + Dense} + BatchNorm. + 1 Dense layer    |     50%         |     0.69          |


References
#### [1] M. Yasumuro and K. Jin’no, Nonlinear Theory Its Appl. IEICE, 13 (2), pp. 288–293, 2022.
#### [2] D. Li et al, 2020 IEEE Winter Conference on Applications of Computer Vision, pp. 1448-1458, 2020. 