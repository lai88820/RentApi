# RentHouse API (AI 智慧共居房屋媒合系統 後端)

RentHouse API 是專為次世代租屋平台打造的核心後端系統。本專案由 3 人團隊採敏捷協作開發，以 **C# ASP.NET Core** 建構高擴充性的 RESTful API。系統無縫對接前端 Angular 應用，除了負責核心業務邏輯與高效能的資料存取，更深度整合了 **AI 智慧媒合引擎**，提供精準的租屋配對服務。

本專案結合了 **JWT 身分驗證、關聯式資料庫管理、圖片上傳與通知服務**，打造出具備高穩定性與容錯能力的完整租屋平台後端架構。

## 專案連結與展示 (Demo & Links)
* **[點此觀看系統實機運作影片 (Google Drive)](https://drive.google.com/file/d/1Pmr0WVPEQpz3UOtleiwPOsqHCDLucNbu/view?usp=drive_link)**
* **[點此前往前端 Angular UI 專案 (GitHub)](https://github.com/lai88820/RentHouse/tree/dev)**
* **後端照片<img width="1429" height="911" alt="image" src="https://github.com/user-attachments/assets/b53000a3-f6a1-41b5-9283-9654702172f7" />
        <img width="1492" height="902" alt="image" src="https://github.com/user-attachments/assets/87a00cf9-dd94-4198-a488-3b456085fee8" />
        <img width="1444" height="908" alt="image" src="https://github.com/user-attachments/assets/d5ce6789-eeff-41dd-992c-2fa7d36ebcf4" />
        <img width="1577" height="733" alt="image" src="https://github.com/user-attachments/assets/bd16932e-bc5a-4030-aa48-1ab2cd2d917d" />
        <img width="1461" height="726" alt="image" src="https://github.com/user-attachments/assets/80767b6b-f867-4bbc-a4d2-bd354ec1c605" />
        <img width="1560" height="726" alt="image" src="https://github.com/user-attachments/assets/4e69de6c-cad5-4661-9bb6-1043bf5a8d8d" />
* **前端照片<img width="1594" height="900" alt="image" src="https://github.com/user-attachments/assets/f913ca22-41b6-4f0f-8742-d14335852559" />
            <img width="1615" height="923" alt="image" src="https://github.com/user-attachments/assets/22dc5d25-54fc-427a-85ae-3a477a910fe0" />
            <img width="1658" height="905" alt="image" src="https://github.com/user-attachments/assets/a9f06f23-caec-499c-8fc2-5722571da08c" />








---

## 團隊成員與分工 (Team & Roles)
本專案由 3 人團隊共同研發，採前後端分離架構：
* **[賴重勻] (Backend & AI Module)：** 負責 C# 後端 API 開發、部分前端、房屋上下架審核、Entity Framework Core 資料庫建置，以及主導 Google Gemini AI 核心串接與效能優化。
* **[組員 A ] (Frontend Developer)：** 負責 Angular 前端畫面實作、UI/UX 設計與狀態管理。
* **[組員 B ] (可依實際狀況填寫，例如：Database / QA / PM)：** 負責...

---

## 核心技術亮點 (Core Highlights)
- **AI 深度評估模組：** 跳脫傳統條件篩選，整合 AI 進行自然語言處理，交叉比對租客作息與房屋公約，自動產出精準的房屋匹配講評。
- **高效能與高容錯架構：** 實作 DTO 資料瘦身優化傳輸效能，並具備 API 請求防護機制，確保系統在高負載下依然穩定運行。
- **嚴謹的安全機制：** 導入 JWT Token 驗證與 Role-based Authorization，確保會員、房東與管理者權限分明。

---

## 技術架構 (Tech Stack)

### 後端技術
- **Framework:** ASP.NET Core Web API (C#)
- **Database:** SQL Server, Entity Framework Core
- **Authentication:** JWT (JSON Web Token)
- **Architecture:** RESTful API

### 系統設計概念
- 前後端分離架構 (Frontend / Backend Separation)
- 分層式架構 (Controller / Service / Repository)
- 模組化功能設計與高擴充性 API

---

## 系統架構圖

```text
Frontend (Angular 21)
        ↓
REST API (ASP.NET Core)
        ↓
Service Layer
        ↓
Repository Layer
        ↓
SQL Server Database
主要功能模組
1. 身分驗證系統 (Auth)
使用者註冊 / 登入

JWT Token 發放與驗證 Middleware

角色權限控管 (Role-based Authorization)

2. 會員系統 (Users)
使用者資料 CRUD 與狀態管理

個人資訊更新與頭像上傳處理

3. 房屋管理系統 (Houses)
房屋物件新增 / 編輯 / 刪除

房屋列表查詢與詳細資訊展示

多維度房屋分類 (坪數、價格、地區)

4. 智慧房屋媒合系統 (Match)
AI 深度媒合運算： 結合外部 AI API 進行高階語意配對。

條件與偏好篩選： 依據使用者需求進行快速推薦邏輯運算。

5. 圖片與檔案系統 (Upload)
房屋實景圖片上傳

使用者頭像上傳與伺服器路徑管理

6. 通知系統 (Notifications)
系統公告與媒合結果通知

具備可擴充即時通知之底層設計 (預留 SignalR 介面)

API 架構設計
Auth
HTTP
POST   /api/auth/login
POST   /api/auth/register
GET    /api/auth/profile
Users
HTTP
GET    /api/users
GET    /api/users/{id}
PUT    /api/users/{id}
Houses
HTTP
GET    /api/houses
GET    /api/houses/{id}
POST   /api/houses
PUT    /api/houses/{id}
DELETE /api/houses/{id}
Match
HTTP
POST   /api/match/search
POST   /api/match/recommend
Upload
HTTP
POST   /api/upload/image
POST   /api/upload/avatar
資料庫設計 (Database)
主要資料表 (Entity) 包含：

Users (使用者)

Houses (房屋)

HouseImages (房屋圖片)

Matches (媒合紀錄)

Notifications (通知)

Roles (權限)

開發環境啟動指南
啟動專案 (CLI)：

Bash
dotnet run
或使用 Visual Studio (IIS Express / Kestrel) 啟動。

API 測試工具
建議使用 Postman，或透過開發環境內建之 Swagger UI：

https://localhost:{port}/swagger
安全機制 (Security)
JWT 驗證： API 路由全面受 Token 驗證保護。

密碼加密： 採用 Password Hash，拒絕明碼儲存。

CORS 控制： 嚴格限制跨網域請求來源。

未來優化方向 (Future Work)
[ ] 導入 SignalR 實作即時聊天與通知

[ ] 導入 Redis 快取優化熱門房源查詢效能

[ ] 導入 ElasticSearch 提升房源搜尋精準度

[ ] 將應用程式 Docker 化，建置 CI/CD 自動部署流程

RentHouse Backend API — Powered by ASP.NET Core
