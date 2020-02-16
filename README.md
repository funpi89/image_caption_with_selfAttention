# image_caption_with_selfAttention

# 使用tensorflow2.0,把image caption的decoder裡的LSTM換成Self-Attention
![image](https://github.com/funpi89/image_caption_with_selfAttention/blob/master/model.jpg)

## 因為tf.keras.inceptionv3預訓練模型的'imagenet'訓練資料沒有人類,所以decoder使用lstm很難產生出人的相關字詞
## 把decoder修改為self-attention後,生成文字較易出現人的相關字詞
### decoder使用self-attention訓練20個epoch的結果
![image](https://github.com/funpi89/image_caption_with_selfAttention/blob/master/att.JPG)

### decoder使用LSTM訓練20個epoch的結果
![image](https://github.com/funpi89/image_caption_with_selfAttention/blob/master/noatt.JPG)

### 訓練模型時,由於COCO Dataset資料太多以致GPU運算不夠用,所以取三萬筆資料並且分為兩個檔案進行訓練
### 先使用`get_img_feature.ipynb以.npy`格式儲存訓練圖檔通過inceptionv3後的特徵向量
### 再執行`image_caption-SelfAttention.ipynb`進行image caption的訓練
