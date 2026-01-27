# snakebite (Firebase edition)

這個 repo 係一個 Snake 遊戲（手機可玩），加咗：
- **Firebase Hosting**：自動部署
- **Firestore Leaderboard（Top 10）**
- **匿名登入（Anonymous Auth）**：確保寫入 leaderboard 有基本保護

網站上線後：
- 你玩完 Game Over 會自動上傳分數
- 右下會見到 Top 10 排行榜

---

## 你要做嘅一次性設定（必做）

### 1) 建立 Firebase Project
1. 去 Firebase Console 建 project
2. 開啟 **Firestore Database**
3. 開啟 **Authentication → Sign-in method → Anonymous**
4. 建立一個 Web App，拎到 `firebaseConfig`

### 2) 把 Secrets 加入 GitHub（令 GitHub Actions 可 deploy）
Repo → Settings → Secrets and variables → Actions → New repository secret：
- `FIREBASE_PROJECT_ID`：例如 `my-project-123`
- `FIREBASE_TOKEN`：喺你電腦跑 `firebase login:ci` 取得

### 3) 更新 `.firebaserc`
把 `YOUR_FIREBASE_PROJECT_ID` 改成你嘅 project id。

### 4) 更新 `index.html` 入面 `firebaseConfig`
把你 Firebase Web App 嘅 config 貼入去。

---

## 本地測試（可選）
你可以先用本機開 `index.html` 測試遊戲。
如果要測試 Firebase：
- 建議用 `firebase emulators:start`（可後續加）

---

## 注意
- Leaderboard 係公開讀取（所有人都睇到 Top10）
- 寫入需要登入（匿名 auth）

