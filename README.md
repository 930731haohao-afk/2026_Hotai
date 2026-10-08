# 2026 和泰黑客松｜三主題 DEMO

這個儲存庫提供三份可獨立解壓使用的展示包，包含原始碼、展示網頁、操作說明及測試。

## 下載

| 主題 | ZIP | 內容 |
| --- | --- | --- |
| EV FIT | [下載 EV FIT](demos/EV_FIT_DEMO_20261009.zip?raw=true) | 油轉電知識問答、互動卡片與生活適配試算；包含本機 Python 版及瀏覽器版 |
| HINO FLOW | [下載 HINO FLOW](demos/HINO_FLOW_DEMO_20261009.zip?raw=true) | 手機駕駛／經理流程、Python 車隊工作台、語音提醒模擬 |
| yoxi MoveAhead | [下載 yoxi MoveAhead](demos/yoxi_MoveAhead_DEMO_20261009.zip?raw=true) | 移動情境、上車點比較、模擬叫車及出發計畫 |

封裝日期：2026-10-09。完整性校驗值見 [SHA256SUMS.txt](SHA256SUMS.txt)。

## 開啟方式

1. 下載需要的 ZIP，完整解壓後先讀內附的 `README.md`。
2. HINO／yoxi 可直接開啟 `docs/index.html`；使用本機 HTTP 服務可避免部分瀏覽器的檔案儲存限制。
3. EV 瀏覽器版需要 HTTP 與網路。在解壓後的專案根目錄執行以下命令（需 Python 3），再開啟 http://127.0.0.1:8080/ ：

```sh
python -m http.server 8080 --bind 127.0.0.1 --directory docs
```

終端機按 `Ctrl+C` 停止服務。三份展示包共用這個示範埠號，請一次啟動一份，或自行換用不同埠號。

EV／HINO 的完整本機 Python 版另需依包內說明安裝依賴。HINO 手機與桌面工作台的紀錄各自獨立，沒有同步。

## 驗證與範圍

本次在 Windows、Python 3.12.14、Node 24.19.0 的既有環境驗證：

| 項目 | 通過數 |
| --- | ---: |
| EV Python 測試 | 121 |
| HINO Python 測試 | 52 |
| HINO 手機 JavaScript 測試 | 24 |
| HINO 語音模擬檢查 | 14 |
| yoxi JavaScript 測試 | 5 |
| 合計 | 216 |

另通過 ZIP CRC、逐檔 SHA-256、Python／JavaScript 語法、JSON 解析及 14 個靜態檔案的本機 HTTP 檢查。每份 ZIP 內有 `MANIFEST.json` 與 `PACKAGE_CHECKS.json`。

未重新驗證全新電腦安裝、瀏覽器完整互動或實際語音播放，也沒有呼叫真實模型、車載、叫車或付款服務。EV 網頁版使用知識庫摘錄；HINO／yoxi 使用合成展示資料。原文件與知識資料保留既有查核日期，不代表封裝日已重新查證所有外部規格。

封裝已排除本機執行環境、runtime、資料庫、日誌、真實金鑰與 Git 歷史。EV 的歷史合成測試紀錄含一筆刻意構造的金鑰樣式字串，已核對為 `S08` 測試案例，不是真實憑證。

目前提供的是 ZIP 下載，尚未部署成公開操作網站。若日後要用 GitHub Pages，須先將靜態檔案解壓上傳並另行設定發布來源；ZIP 不會自動展開。參考 [GitHub 官方檔案上傳說明](https://docs.github.com/en/repositories/working-with-files/managing-files/adding-a-file-to-a-repository)與 [Pages 發布來源說明](https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site)。

本專案是競賽概念原型，沒有 TOYOTA、HINO、yoxi 或和泰官方背書；未另行授予開源授權。
