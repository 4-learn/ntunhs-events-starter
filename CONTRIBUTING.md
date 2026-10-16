# 協作規範

1. **不直接推 main**：開 branch → PR → 至少 1 位 review → CI 綠燈 → merge。
2. **branch 名稱**：`類型/簡短說明`，例如 `fix/timezone`、`feat/list-by-site`。
3. **commit 訊息**：`類型: 說明`。類型用 `feat`（新功能）、`fix`（修錯）、`test`（測試）、`docs`（文件）、`ci`（自動化）、`chore`（雜事）。
4. **一個 PR 只做一件事**，PR 描述寫 Why／What／Test plan，用 `Closes #編號` 連到 issue。
5. **刪測試或改測試的期望值**，要在 PR 描述說明為什麼，reviewer 要特別看。
6. **版本號**：`vMAJOR.MINOR.PATCH`。修錯升 PATCH、加功能升 MINOR、改壞相容性升 MAJOR。發版改 `app/main.py` 的 `VERSION`，再打同名 tag。
