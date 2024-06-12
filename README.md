# forecast_order
このリポジトリには、Hawk APIを使用して受注予測を行うための ForecastOrders クラスが含まれています。このクラスを使用して、受注データを元に予測を実行し、その結果を取得することができます。
# Requirement
ForecastOrdersはPython3系で動作し、以下のライブラリに依存します。
* [requests](https://pypi.org/project/requests/)
# Installation
```
pip install requests
```
# Methods
```
・forecast_orders(self, client_id, api_token, pred_id, original_data):
    受注予測を実行し、その結果を取得します。
"""
引数は省略不可です。
Args:
  client_id (str): client ID,任意の文字列
  private_key (str): 認証に使用するAPIトークン
  pred_id (str): 予測ID,任意の文字列
  original_data (list): 予測用の実績データ
Returns:
  dict:予測結果
"""
```
# Usage
以下は、ForecastOrders クラスを使用して予測を実行し、結果を取得するサンプルコードです。
```
# 入力データ
client_id = "your_client_id"
api_token = "your_api_token"
pred_id = "your_pred_id"
original_data = [
    {"受注日(YYYYMMDD形式)": "20230101", "金額": 1000},
    {"受注日(YYYYMMDD形式)": "20230102", "金額": 1500},
    # 他のデータを追加
]

forecast_orders_instance = ForecastOrders()
forecast_result = forecast_orders_instance.forecast_orders(client_id, api_token, pred_id, original_data)
```
# Notes
* このクラスはテスト環境用に設計されています。実際のエンドポイントやAPI URLを使用する前に、テスト環境で十分に動作を確認してください。
* ジョブステータスの取得や予測結果の取得には一定の時間がかかる場合があります。適宜 time.sleep などを用いて適切に待機時間を設けてください。
# Author
* Author  
Yuto Sasa
* Organization  
[株式会社ゼンク](https://zenk.co.jp/)
# License
"ForecastOrders" is under [MIT license](https://opensource.org/license/mit).
