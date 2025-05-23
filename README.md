# YOLOv8-Teaching-and-Testing
使用Roboflow資料集或自訂義資料集訓練，並使用YOLOv8模型進行訓練(利用Google Colab)，再利用訓練完的模型檔(best.pt)與撰寫程式來即時辨識現實物體影像。

## Step.0 蒐集資料集與網站上傳
自行蒐集資料集或使用網路上公開資料集(如: Kaggle、COCO、Roboflow Universe等)，如下圖使用先前上銀機械手臂比賽的撞球影像共50張(數量可以找30、50或以上)，選擇Roboflow網站(https://roboflow.com/)註冊登入。

![0](https://github.com/user-attachments/assets/0988c7d7-ae8c-4fb5-addc-097f5c4d48ef)
![1](https://github.com/user-attachments/assets/a2bb046a-fdc0-41e9-83e7-fbfd54172f49)

點選Create New Project，依照自行需求選擇Project Type類型，這邊就以Object Detection作為示範，建立完專案後，進行自定義資料集建置與上傳。
![2](https://github.com/user-attachments/assets/80f23803-a6cd-45f9-ac6c-fd055c678ebb)
![3](https://github.com/user-attachments/assets/93c0a312-2c17-4a34-a5db-843be78b4151)

## Step.1 Clone OpenPose

```
git clone https://github.com/CMU-Perceptual-Computing-Lab/openpose
cd openpose/
git submodule update --init --recursive --remote
```
