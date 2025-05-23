# YOLOv8-Teaching-and-Testing
使用Roboflow資料集或自訂義資料集訓練，並使用YOLOv8模型進行訓練(利用Google Colab)，再利用訓練完的模型檔(best.pt)與撰寫程式來即時辨識現實物體影像。

## Step.0 蒐集資料集與網站上傳
自行蒐集資料集或使用網路上公開資料集(如: Kaggle、COCO、Roboflow Universe等)，如下圖使用先前上銀機械手臂比賽的撞球影像共50張(數量可以找30、50或以上)，選擇Roboflow(https://roboflow.com/) 網站登入。

![0](https://github.com/user-attachments/assets/6d879476-14df-47ec-901f-3db743d3d717)

![1](https://github.com/user-attachments/assets/1e6ee8c8-146d-4cfc-9664-d9892da48024)


點選Create New Project，依照自行需求選擇Project Type類型，這邊就以Object Detection作為示範，建立完專案後，進行自定義資料集建置與上傳。

![2](https://github.com/user-attachments/assets/7f10b84d-dbdd-4b20-b31a-7b61d86443bc)
![3](https://github.com/user-attachments/assets/cac0f5c8-fa4b-4317-b376-35e7596e10d7)


## Step.1 資料標註
透過Roboflow工具進行資料標註(可自定義標籤)，這裡測試使用標註分類白色母球「White」與黑色子球「Black」共兩種。

![4](https://github.com/user-attachments/assets/c7408e3e-22db-47ca-bf3b-1c8ee6034898)
![5](https://github.com/user-attachments/assets/ab22ebba-fc8c-4fae-8de4-1dfae3b69124)


標註完成後回到Annotate那頁，點選右上角Add images to Dataset，系統會先幫你設定訓練集、驗證集、測試集比率，也可以自行調整。

![6](https://github.com/user-attachments/assets/47aa964e-5f90-4282-a5ee-ca9431111588)

![7](https://github.com/user-attachments/assets/7f9ed018-e9eb-477a-8e87-d15000d19892)



創建完後版本會顯示日期時間，並點選右上Export Dataset，選擇YOLOv8(也可以依個人需求或實驗選擇其他配置)。

![8](https://github.com/user-attachments/assets/f000a4b9-c5d6-4b37-8475-10b0962e33b5)



## Step.2 訓練資料(Google Colab)與結果可視化
使用Google Colab (https://colab.research.google.com/)，開啟記事本並建立新專案。

![9](https://github.com/user-attachments/assets/784a30a6-7ede-416d-a002-22374952398e)


載入YOLOv8與Python影像套件，將前面Roboflow建好的專案輸出貼到Colab中，如下圖所示:

![10](https://github.com/user-attachments/assets/77b16ac2-b3bd-45b5-9e6d-c96f55e1a399)



任務模式使用detect，模型使用yolov8s，epoches可依實驗需求調整，這裡使用25次為測試，並開始訓練模型，訓練完後可將模型中的混淆矩陣(Confusion Matrix)輸出顯示，評估模型效果。並將訓練結果可視化。

![11](https://github.com/user-attachments/assets/6e009cbf-e4d6-43cd-9a61-df3f1c449b35)

![12](https://github.com/user-attachments/assets/01d161ac-6354-442d-aba4-0f852b7afb49)



使用訓練完的模型(best.pt)讀取影像測試結果。

![13](https://github.com/user-attachments/assets/00e71769-93af-4f05-b6bf-f0c65e7cd5ca)


## 延伸應用
將訓練完模型輸出，進行其他如撞球、水果、汽車或其他物件等即時辨識(Realtime)等相關應用，並針對實驗、比賽或專題方面發想，如下是我測試的Object Detection模型，Classes為「Spongebob」、「Patrick」，影像總數量為90張。使用訓練完的模型檔(best.pt)與撰寫程式(predict.py)來即時辨識現實物體影像。

![16](https://github.com/user-attachments/assets/0d103bc7-4563-4289-9809-46ba5428cb6a)
![17](https://github.com/user-attachments/assets/c8731e0a-6398-41f2-a811-88b27de29331)
![APEXepoches5](https://github.com/user-attachments/assets/885111e3-985e-45e5-af5f-98c1292628ea)

