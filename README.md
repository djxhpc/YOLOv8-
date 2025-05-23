# YOLOv8-Teaching-and-Testing
使用Roboflow資料集或自訂義資料集訓練，並使用YOLOv8模型進行訓練(利用Google Colab)，再利用訓練完的模型檔(best.pt)與撰寫程式來即時辨識現實物體影像。

## Step.0 蒐集資料集與網站上傳
自行蒐集資料集或使用網路上公開資料集(如: Kaggle、COCO、Roboflow Universe等)，如下圖使用先前上銀機械手臂比賽的撞球影像共50張(數量可以找30、50或以上)，選擇Roboflow(https://roboflow.com/) 網站登入

![0](https://github.com/user-attachments/assets/f62f5fe9-c076-4e81-9cd7-71aee012bf23)
![1](https://github.com/user-attachments/assets/d52403fc-e84c-4011-9128-ab918dcf729e)


點選Create New Project，依照自行需求選擇Project Type類型，這邊就以Object Detection作為示範，建立完專案後，進行自定義資料集建置與上傳。

![2](https://github.com/user-attachments/assets/c7f86dce-944f-4944-971e-3d2316742045)
![3](https://github.com/user-attachments/assets/f859882e-a1b2-4daa-996e-4e321663dff5)


## Step.1 資料標註
透過Roboflow工具進行資料標註(可自定義標籤)，這裡測試使用標註分類白色母球「White」與黑色子球「Black」共兩種。

![4](https://github.com/user-attachments/assets/67b64142-270b-4e6d-8a12-b71047fa0cb0)
![5](https://github.com/user-attachments/assets/a2eeaf20-1bd4-4ff0-80cf-2e1a644481e2)


標註完成後回到Annotate那頁，點選右上角Add images to Dataset，系統會先幫你設定訓練集、驗證集、測試集比率，也可以自行調整。

![6](https://github.com/user-attachments/assets/47aa964e-5f90-4282-a5ee-ca9431111588)

![7](https://github.com/user-attachments/assets/ca964b99-0a34-4c2b-9eb7-17866dc96908)


創建完後版本會顯示日期時間，並點選右上Export Dataset，選擇YOLOv8(也可以依個人需求或實驗選擇其他配置)。

![8](https://github.com/user-attachments/assets/03bac75c-baff-4a0c-85c3-2b3662af26d4)


## Step.2 訓練資料(Google Colab)與結果可視化
使用Google Colab (https://colab.research.google.com/)，開啟記事本並建立新專案。

![9](https://github.com/user-attachments/assets/1503d100-b75c-4a7f-b037-11f074ce9346)

載入YOLOv8與Python影像套件，將前面Roboflow建好的專案輸出貼到Colab中，如下圖所示

![10](https://github.com/user-attachments/assets/977bfa28-68b7-4ca4-9a04-bb31f75b57d6)


任務模式使用detect，模型使用yolov8s，epoches可依實驗需求調整，這裡使用25次為測試，並開始訓練模型，訓練完後可將模型中的混淆矩陣(Confusion Matrix)輸出顯示，評估模型效果。並將訓練結果可視化。

![11](https://github.com/user-attachments/assets/6e009cbf-e4d6-43cd-9a61-df3f1c449b35)

![12](https://github.com/user-attachments/assets/2be267ef-28e0-48e2-b011-2e8719c8b6dd)


使用訓練完的模型(best.pt)讀取影像測試結果。

![13](https://github.com/user-attachments/assets/6cf177c4-ef10-467b-b02f-6ef1de64ff22)

## 延伸應用
可將訓練完模型輸出，進行其他如撞球、水果、汽車或其他物件等即時辨識(Realtime)等相關應用，並針對實驗、比賽或專題方面發想，如下是我測試的Object Detection模型，Classes為「Spongebob」、「Patrick」，影像總數量為90張。使用訓練完的模型檔(best.pt)與撰寫程式(predict.py)來即時辨識現實物體影像。

![16](https://github.com/user-attachments/assets/0d103bc7-4563-4289-9809-46ba5428cb6a)
![17](https://github.com/user-attachments/assets/c8731e0a-6398-41f2-a811-88b27de29331)

