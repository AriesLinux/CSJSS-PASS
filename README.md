<div align="center">

# 💳 CSJSS PASS (CSJSS 數碼通行證)
## Next-Gen Digital ID & Wallet Integration Project
<br><br><br>
<img src="https://github.com/AriesLinux/CSJSS-Healthy-Kit/blob/main/school_logo.jpg" width="450" alt="School Logo">
<br><br><br>
<img src="https://github.com/AriesLinux/CSJSS-APPS-Hub/blob/main/CSJSS_PASS.png" width="150" alt="CSJSS PASS Logo">
<br><br>

![Version](https://img.shields.io/badge/Version-v1.0--alpha-blue?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Developing-orange?style=for-the-badge)
![NFC](https://img.shields.io/badge/Technology-NFC_%7C_Wallet-green?style=for-the-badge&logo=contactless-payment)
![Security](https://img.shields.io/badge/Security-AES_Encrypted-red?style=for-the-badge)

<p align="center">
  <strong>透過 Apple Pay 與 Google Pay 協議，將傳統學生證與手機錢包完美融合</strong>
</p>


</div>

---

## 🔬 運作原理 (How It Works)

**CSJSS PASS** 並非單純的圖片顯示，而是基於底層 NFC 通訊協議與憑證管理系統的深度整合：

### 1. 憑證封裝 (Wallet Pass Provisioning)
* **後端架構**: 使用伺服器動態生成加密的 `.pkpass` (iOS) 或 Google Wallet REST API 憑證
* **即時更新**: 透過 **APNs (Apple Push Notification service)** 實現資料同步，例如當學生完成拍卡，錢包APP中可即時顯示「已到校」狀態

### 2. NFC 模擬與 VAS 協議
* **通訊標準**: 採用 ISO/IEC 14443 Type A/B 標準
* **感應技術**: 
    * **Apple VAS (Value Added Services)** 協議
    * **Google Smart Tap** 協議。
* **快捷模式**: 支援「特快交通卡」模式（Express Mode），使用者**無需解鎖手機、無需 FaceID/TouchID**，靠近讀卡機即可感應

### 3. 安全加密機制
* **Dynamic Token**: 錢包內的 QR Code 採用時效性加密，每 30 秒更換一次，防止截圖偽造
* **AES-256 加密**: 學生身份 UID 在傳輸過程中全程加密，僅在校內授權讀卡機端解碼

---

## ✨ 物理學生卡改良方案 (Physical Card Redesign)

為了實現「手機就是學生證」並確保舊有系統平穩過渡，現有的物理學生卡需進行以下技術升級：

### 📍 需更改的地方 (Modifications)
| 項目 | 現有舊版卡片 | **新版 CSJSS PASS 兼容卡** |
| :--- | :--- | :--- |
| **芯片頻段** | 低頻 (125kHz) | **高頻 (13.56MHz) + NFC 雙頻芯片（因舊版無NFC功能）** |
| **存儲空間** | 唯讀 UID | **可讀寫加密磁區** (用於儲存離線憑證) |
| **天線設計** | 普通線圈 | **抗金屬干擾天線** (避免與手機貼合時產生訊號屏蔽) |

### 🚩 必須加入的標誌 (Required Indicators)
新版實體卡面需印製以下標準化標誌，以符合數位化識別：

* **NFC 感應標誌 (Contactless Symbol)**: 
    * 必須印在卡片右上角，標示感應核心位置
    <img src="https://github.com/user-attachments/assets/b2b315dc-339e-4d3d-a882-c3b01eb3c625" width="200" alt="EMV">
* **Wallet 兼容標識**: 
    * `Add to Apple Wallet` 與 `Add to Google Wallet` 的官方彩色圖示，方便學生掃描綁定
---

## 📊 運行狀態 (Status)

### ✅ 正常運作 (Working)
* [x] **Static Pass Issuance**: 手動生成靜態 Wallet 憑證文件
* [x] **NFC Handshake**: 完成 iPhone 與實驗室讀卡機的初步握手測試
* [x] **UI Framework**: 建立基於 **EazyUI** 的憑證綁定界面

### ❌ 開發阻礙 (Roadblocks)
* [ ] **自動化分發系統**: 正在解決自動發送 `.pkpass` 郵件至學生 `@csjss.edu.hk` 的後端邏輯
* [ ] **Google Wallet API**: 仍等待 Google Cloud Platform 及 Apple Pay API Partner 的企業帳號審核
* [ ] **硬體適配**: 校內部分舊款讀卡機需更換支援 NFC 協議的模組

---

## ⚙️ 開發端要求 (System Requirements)

* **Apple Developer Account**: 需具備 PassKit 開發權限
* **SSL Certificate**: 所有憑證生成必須經過受信任的證書簽名
* **Hardware Support**: 支援 NFC 的讀卡機（如 PN532 或 ACR122U）

---

## 👏 開發團隊 (Credits)

* **Lead Architect**: DONG ALLEN SHUHANG / CSJ IT 部
* **UI/UX Design**: **EazyUI Framework**

---

<div align="center">
  <p><strong>Digitizing the Campus Experience, One Tap at a Time.</strong></p>
  <p>如有任何問題，請前往 IT 部或透過 CSJSS Go! 回報 </p>
</div>
