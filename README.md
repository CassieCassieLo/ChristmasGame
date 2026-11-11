# Santa Spell Night

純 Web 的聖誕英文拼字打地鼠遊戲：Santa 從煙囪冒出來，玩家用滑鼠或觸控敲出正確英文單字。

## 本機預覽

專案不需要安裝套件，使用靜態 HTTP 伺服器開啟：

```bash
python3 -m http.server 8000
```

然後前往 `http://127.0.0.1:8000/`。

## 遊戲規則

- 三關依序為 3×3、4×4、5×5 煙囪矩陣。
- 每題先看中文提示，再敲出正確英文拼字。
- 每關限時 60 秒，拼對 10 個單字即過關。
- 敲錯扣一顆愛心，每局共有五顆。
- 關卡越後面，Santa 出現與消失越快，同時出現的煙囪數量也越多。
- 失敗時退出關卡並回到主地圖。
- 拼對時 Santa 會送上大大的啾咪表情。
- 第一次開始遊戲會由 Santa NPC 說明關卡內容與操作方式。
- 解鎖進度、教學狀態與音效偏好保存於瀏覽器 `localStorage`。

## 美術方向

正式方向為「北極藍夜光」：極光、冰晶、雪夜屋頂與紅白 Santa。角色、擊中反應、地圖和關卡背景使用 ImageGen 生成，再以 `generate2dmap` 的場景規劃與 `generate2dsprite` 的角色資產規則整理成 Web runtime 素材；HUD 和互動元件以 CSS/HTML 實作，確保 GitHub Pages 不需後端即可部署。

關卡資料規劃在 [game-data/level-plan.json](game-data/level-plan.json)。

## GitHub Pages

將儲存庫的 Pages Source 設為 `Deploy from a branch`，選擇主要分支與根目錄即可。
