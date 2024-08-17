# kuzushiji-handwritten-recognition


##  Data Set
[Kuzushiji-49](https://github.com/rois-codh/kmnist)

49 個類別（28x28 灰度像素，270,912 個圖像）
包含 48 個平假名字元和一個平假名疊字符號。



## About the Model
使用卷積層提取圖像中的特徵

最大池化層減少特徵圖的大小，同時保留特徵，降低計算複雜度

Dropout隨機丟棄部分神經元，防止過擬合

平坦層轉為一維向量，以便輸入到全連接層

全連接層做最後的輸出

| Layer (type)              | Output Shape        | Param #  |
|---------------------------|---------------------|----------|
| conv2d (Conv2D)           | (None, 28, 28, 32)  | 320      |
| conv2d_1 (Conv2D)         | (None, 28, 28, 32)  | 9,248    |
| conv2d_2 (Conv2D)         | (None, 28, 28, 32)  | 9,248    |
| max_pooling2d (MaxPooling2D) | (None, 14, 14, 32) | 0      |
| conv2d_3 (Conv2D)         | (None, 14, 14, 64)  | 18,496   |
| conv2d_4 (Conv2D)         | (None, 14, 14, 64)  | 36,928   |
| max_pooling2d_1 (MaxPooling2D) | (None, 7, 7, 64)  | 0      |
| dropout (Dropout)         | (None, 7, 7, 64)    | 0        |
| conv2d_5 (Conv2D)         | (None, 7, 7, 64)    | 36,928   |
| conv2d_6 (Conv2D)         | (None, 7, 7, 64)    | 36,928   |
| max_pooling2d_2 (MaxPooling2D) | (None, 3, 3, 64)  | 0      |
| dropout_1 (Dropout)       | (None, 3, 3, 64)    | 0        |
| flatten (Flatten)         | (None, 576)         | 0        |
| dense (Dense)             | (None, 512)         | 295,424  |
| dense_1 (Dense)           | (None, 49)          | 25,137   |
| **Total params:**         | **468,657**         |          |
| **Trainable params:**     | **468,657**         |          |
| **Non-trainable params:** | **0**               |          |

