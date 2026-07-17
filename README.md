# 📡 Job Radar 台中職缺雷達

台中職缺主動監測系統（PWA）。把「目標雇主巡檢 → 關鍵字掃描 → 12 點框架評分」的監測框架落地成可安裝在手機主畫面的工具。

**線上版本：** https://neeilo.github.io/Job-Radar/

## 功能

- **雷達**：巡檢到期總覽（到期亮紅、3 天內亮黃）、備份提醒、關鍵字快速掃描（LinkedIn / 104 深連結，自動帶入台中＋彰化＋南投與排除詞）
- **雇主**：目標雇主清單（預載 9 家），巡檢時鐘、官網直達、一鍵標記已巡，可增刪改
- **職缺**：職缺攔截登錄 → 地點硬篩 → 12 點框架加權評分 → 綠燈判定（門檻可調）
- **設定**：巡檢週期、綠燈門檻、中英關鍵字與排除詞、評分維度與權重、LinkedIn Job Alerts 設定引導、JSON 匯出／匯入

## 技術

- 純 HTML/CSS/JS 單檔，無框架、無外部依賴
- 資料存 localStorage（key：`job-radar-state-v1`），僅存於本機
- PWA：manifest + Service Worker（HTML network-first、其他 cache-first）

## 維護慣例

修改任何發布檔案後，`sw.js` 的 `CACHE` 版號必須 +1（`job-radar-v1` → `v2`），否則舊快取會擋住新版本。

## Roadmap（Phase 2 backlog）

- [ ] 自動爬蟲與排程推播（GitHub Actions / Make.com）
- [ ] Google Sheets 雲端同步（沿用 Neil OS 方案 C）
