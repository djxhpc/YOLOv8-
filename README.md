# YOLOv8-Teaching-and-Testing
使用Roboflow資料集或自訂義資料集訓練，並使用YOLOv8模型進行訓練(利用Google Colab)，再利用訓練完的模型檔(best.pt)與撰寫程式來即時辨識現實物體影像。

## Step.0 蒐集資料集與網站上傳
自行蒐集資料集或使用網路上公開資料集(如: Kaggle、COCO、Roboflow Universe等)，如下圖使用先前上銀機械手臂比賽的撞球影像共50張(數量可以找30、50或以上)，選擇Roboflow網站(https://roboflow.com)登入

![0](https://github.com/user-attachments/assets/0988c7d7-ae8c-4fb5-addc-097f5c4d48ef)
![1](https://github.com/user-attachments/assets/a2bb046a-fdc0-41e9-83e7-fbfd54172f49)

點選Create New Project，依照自行需求選擇Project Type類型，這邊就以Object Detection作為示範，建立完專案後，進行自定義資料集建置與上傳。

![2](https://github.com/user-attachments/assets/80f23803-a6cd-45f9-ac6c-fd055c678ebb)
![3](https://github.com/user-attachments/assets/93c0a312-2c17-4a34-a5db-843be78b4151)

## Step.1 資料標註
透過Roboflow工具進行資料標註(可自定義標籤)，這裡測試使用標註分類白色母球「White」與黑色子球「Black」共兩種。
![4](https://github.com/user-attachments/assets/6e315f3b-79b7-403d-b246-a7376454f0b0)

![5](https://github.com/user-attachments/assets/da61af60-29d8-45a7-b24d-570e9de7ee1d)


標註完成後回到Annotate那頁，點選右上角Add images to Dataset，系統會先幫你設定訓練集、驗證集、測試集比率，也可以自行調整。

![6](https://github.com/user-attachments/assets/47aa964e-5f90-4282-a5ee-ca9431111588)

![7](https://github.com/user-attachments/assets/508ec62c-1feb-4598-bddc-8f007485de90)

創建完後版本會顯示日期時間，並點選右上Export Dataset，選擇YOLOv8(也可以依個人需求或實驗選擇其他配置)。

![8](https://github.com/user-attachments/assets/c0e8caa7-f7b3-43e1-82c3-9ef855dada91)

## Step.2 訓練資料(Google Colab)與結果可視化
使用Google Colab (https://colab.research.google.com/)，開啟記事本並建立新專案。

![9](https://github.com/user-attachments/assets/2f978c8c-741e-43e7-b17d-5a88e63aa1cd)
載入YOLOv8與Python影像套件，將前面Roboflow建好的專案輸出貼到Colab中，如下圖所示

![10](https://github.com/user-attachments/assets/27f0971b-fcc7-49b9-ab4e-0e02f38ed4a3)

任務模式使用detect，模型使用yolov8s，epoches可依實驗需求調整，這裡使用25次為測試，並開始訓練模型，訓練完後可將模型中的混淆矩陣(Confusion Matrix)輸出顯示，評估模型效果。並將訓練結果可視化。

![11](https://github.com/user-attachments/assets/6e009cbf-e4d6-43cd-9a61-df3f1c449b35)
![12](https://github.com/user-attachments/assets/1865632e-4c27-420c-99d0-d2002d189afd)


使用訓練完的模型(best.pt)讀取影像測試結果。

![13](https://github.com/user-attachments/assets/9b02d1b8-5e5c-41d3-9353-6e7250567f2f)


## 延伸應用
可將訓練完模型輸出，進行其他如撞球、水果、汽車或其他物件等即時辨識(Realtime)等相關應用，並針對實驗、比賽或專題方面發想，如下是我測試的Object Detection模型，Classes為「Spongebob」、「Patrick」，影像總數量為90張。使用訓練完的模型檔(best.pt)與撰寫程式(predict.py)來即時辨識現實物體影像。

![16](https://github.com/user-attachments/assets/0d103bc7-4563-4289-9809-46ba5428cb6a)
![17](https://github.com/user-attachments/assets/c8731e0a-6398-41f2-a811-88b27de29331)

