# SlotMachine 安裝與啟動教學

## 專案簡介
這是一個使用 Blazor WebAssembly 開發的自製點名用拉霸機應用程式。

## 系統需求

### 作業系統
- macOS (Darwin)
- Windows
- Linux

### 必要軟體
- .NET 8.0 SDK 或更新版本
- 網頁瀏覽器 (Chrome, Firefox, Safari, Edge)

## 安裝步驟

### 1. 安裝 .NET SDK

#### macOS 用戶 (使用 Homebrew)
```bash
# 檢查是否已安裝 Homebrew
brew --version

# 安裝 .NET SDK
brew install --cask dotnet
```

**注意**: 安裝過程中可能需要輸入系統密碼，請在終端機中輸入密碼完成安裝。

#### Windows 用戶
1. 前往 [.NET 官方下載頁面](https://dotnet.microsoft.com/download)
2. 下載 .NET 8.0 SDK
3. 執行安裝程式並按照指示完成安裝

#### Linux 用戶 (Ubuntu/Debian)
```bash
# 更新套件清單
sudo apt update

# 安裝 .NET SDK
sudo apt install dotnet-sdk-8.0
```

### 2. 驗證安裝
```bash
# 檢查 .NET 版本
dotnet --version

# 應該顯示類似: 8.0.x 的版本號
```

## 專案啟動步驟

### 方法一：使用 .NET CLI (推薦)

1. **開啟終端機並切換到專案目錄**
```bash
cd /Users/yen/Desktop/SlotMachine/src
```

2. **還原 NuGet 套件**
```bash
dotnet restore
```

3. **啟動專案**
```bash
dotnet run
```

### 方法二：使用 Visual Studio
1. 開啟 Visual Studio
2. 開啟 `SlotMachine.sln` 解決方案文件
3. 按 F5 或點擊「開始偵錯」按鈕

### 方法三：使用 Visual Studio Code
1. 開啟 Visual Studio Code
2. 開啟專案資料夾
3. 按 Ctrl+Shift+P (Windows/Linux) 或 Cmd+Shift+P (macOS)
4. 輸入 "dotnet: run" 並執行

### 方法四：指定啟動設定檔
```bash
# HTTP 模式
dotnet run --launch-profile http

# HTTPS 模式
dotnet run --launch-profile https
```

## 存取應用程式

啟動成功後，您可以在瀏覽器中存取：

- **HTTP**: `http://localhost:5128`
- **HTTPS**: `https://localhost:7102`

## 專案結構說明

```
SlotMachine/
├── src/                          # 主要原始碼目錄
│   ├── Pages/                    # Razor 頁面
│   │   └── Slot.razor           # 拉霸機主頁面
│   ├── Layout/                  # 版面配置
│   ├── wwwroot/                 # 靜態資源
│   │   ├── data/                # 資料檔案
│   │   │   ├── slots.json       # 拉霸機配置
│   │   │   ├── dun-dun-duuuun.mp3  # 音效檔案
│   │   │   └── glass_ping.mp3   # 音效檔案
│   │   └── css/                 # 樣式檔案
│   ├── Program.cs               # 應用程式進入點
│   └── SlotMachine.csproj       # 專案檔案
├── docs/                        # 建置後的檔案
└── README.md                    # 專案說明
```

## 功能特色

- 🎰 拉霸機點名功能
- 🔊 音效支援
- 📱 PWA (Progressive Web App) 支援
- 🎨 響應式設計
- ⚡ Blazor WebAssembly 高效能

## 常見問題與解決方案

### Q1: 執行 `dotnet` 指令時出現 "command not found"
**解決方案**: 
- 確認已正確安裝 .NET SDK
- 重新開啟終端機
- 檢查 PATH 環境變數是否包含 .NET 安裝路徑

### Q2: 安裝 .NET SDK 時需要密碼
**解決方案**: 
- 這是正常現象，請在終端機中輸入您的系統密碼
- 如果無法輸入密碼，請確保終端機有適當的權限

### Q3: 專案啟動後無法存取網頁
**解決方案**: 
- 檢查防火牆設定
- 確認埠號 5128 或 7102 沒有被其他程式佔用
- 嘗試使用不同的瀏覽器

### Q4: 音效無法播放
**解決方案**: 
- 確認瀏覽器允許音效播放
- 檢查音效檔案是否存在於 `wwwroot/data/` 目錄中
- 確認瀏覽器支援音效格式

### Q5: 建置失敗
**解決方案**: 
```bash
# 清理專案
dotnet clean

# 重新還原套件
dotnet restore

# 重新建置
dotnet build
```

## 開發環境設定

### 推薦的開發工具
- **Visual Studio Code** + C# 擴充功能
- **Visual Studio** (Windows/macOS)
- **JetBrains Rider**

### 有用的 VS Code 擴充功能
- C# Dev Kit
- Blazor Snippet Pack
- Auto Rename Tag

## 技術規格

- **框架**: Blazor WebAssembly
- **.NET 版本**: 8.0
- **目標平台**: Web
- **PWA 支援**: 是
- **音效格式**: MP3

## 聯絡資訊

如有任何問題或建議，請聯絡專案維護者。

---

**最後更新**: 2024年12月
