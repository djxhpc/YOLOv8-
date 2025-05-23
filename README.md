# YOLOv8-Teaching-and-Testing
使用Roboflow資料集或自訂義資料集訓練，並使用YOLOv8模型進行訓練(利用Google Colab)，再利用訓練完的模型檔(best.pt)與撰寫程式來即時辨識現實物體影像。

## Step.0 蒐集資料集與網站上傳
自行蒐集資料集或使用網路上公開資料集(如: Kaggle、COCO、Roboflow Universe等)，如下圖使用先前上銀機械手臂比賽的撞球影像共50張(數量可以找30、50或以上)
```
![0](https://github.com/user-attachments/assets/0988c7d7-ae8c-4fb5-addc-097f5c4d48ef)

```
## Step.1 Clone OpenPose

```
git clone https://github.com/CMU-Perceptual-Computing-Lab/openpose
cd openpose/
git submodule update --init --recursive --remote
```
