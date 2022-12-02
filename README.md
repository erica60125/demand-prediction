# ncku-demand-predict

## 需量預測

需量預測數據是使用成大工科系系館的需量所作訓練
以下以資料夾個別做說明:

- data_preprocessing: 所有用到的功能的sample code
	- 為基本從資料庫撈取資料
	- 使用 codis 與中央氣象局api抓取天氣
- error-calculation: 計算預測結果的RMSE、MAPE、MAE 的誤差值
- scheduled : 
	- 定時抓取天氣、需量寫入至資料庫
	- 定時將用量以 kmeans 做分群, 分為尖峰、離峰、半尖峰
- training: 訓練模型
	- 使用 LSTM 架構來訓練模型
	
- predict: 預測需量
	- 以 sliding windows 的方式來定時對已訓練好的模型做更新並預測


以上為需量預測的功能，而我們會將預測結果呈現於網頁上，詳細網頁架構於[連結](https://github.com/erica60125/demandDashboard)做說明