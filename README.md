# events-api 起點：松年長照中心跌倒事件紀錄

Git 與自動化 **第 14 節 綜合 Workshop B** 的範本 repo。講義：<https://hackmd.io/c/r12AlLGsfl>

> 林護理長：「夜班如果偵測到有人跌倒，我希望隔天早上能看到一筆紀錄：幾點、哪一台攝影機、哪裡。先不用有 AI，有地方收、收進來的資料是對的就好。」

## 開始

1. 右上角 **Use this template → Create a new repository**，名稱填 `events-api`、選 **Public**
2. 在 VM 裡：

```bash
git clone git@github.com:<你的帳號>/events-api.git
cd events-api
python3 -m venv .venv && source .venv/bin/activate
pip install -r requirements.txt
pytest -q
```

一開始會看到 **1 個紅燈**（`test_event_time_without_timezone_rejected`），這是第一個任務。

## 內容

| 路徑 | 用途 |
| --- | --- |
| `app/main.py` | FastAPI：`GET /health`、`POST /events`、`GET /events`（存在記憶體） |
| `tests/test_events.py` | 5 個測試，每個對應一條需求 |
| `requirements.txt` | 與 `devops-ci-demo` 同版本 |

## 卡住了？

| 分支 | 內容 |
| --- | --- |
| `checkpoint/fixed` | 任務 1 完成：時區檢查已補上，5 個測試全綠 |
| `checkpoint/ci` | 任務 2 完成：再加 `.github/workflows/ci.yml` |
| `checkpoint/release` | 任務 3 完成：再加協作規範（PR 範本、CODEOWNERS）與「打 tag 自動發 Release」的 workflow |

```bash
git fetch origin
git switch -c my-rescue origin/checkpoint/ci   # 從任務 2 的終點接著做
```

（用 Use this template 建的 repo 預設只有 `main`。要救援分支，在建立時勾 **Include all branches**。）

資料都是虛構的。
