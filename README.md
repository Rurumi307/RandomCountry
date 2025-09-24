# RandomCountry

這個專案是一個簡單的 Python 工具，用於從 Excel 檔案中隨機抽取尚未去過、適合一日遊的行政區資料。  
主要功能是根據指定條件過濾資料，並隨機選出指定數量的地點，方便旅遊規劃或活動抽籤。

## 功能說明

- 從 `RandomCountry.xlsx` 的「行政區名稱」工作表讀取資料
- 篩選「一日遊」欄位為 Y 且「去過」欄位不為 Y 的資料
- 隨機抽取指定筆數的地點（可調整 n 參數）

## 使用方式

1. 將你的行政區資料放在 `RandomCountry.xlsx`，並確保有「一日遊」與「去過」欄位
2. 執行 `RandomCountry.ipynb`，可在 Jupyter Notebook 或 VS Code 的 Notebook 模式下運行
3. 調整 `n` 參數以設定要抽取的地點數量
4. 結果會在程式輸出顯示

## 需求套件

- pandas

安裝方式：
```bash
pip install pandas
```

## 範例

```python
import pandas as pd

file_path = './RandomCountry.xlsx'
sheet_name = '行政區名稱'

df = pd.read_excel(file_path, sheet_name=sheet_name)
filtered_df = df.query("一日遊 == 'Y' and 去過 != 'Y'")
n = 2
random_rows = filtered_df.sample(n=n, random_state=None)
print(random_rows)
```

---

如需自訂條件或功能，歡迎自行修改程式碼！

