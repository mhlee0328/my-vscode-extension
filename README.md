# My VSCode Extension

記錄 Visual Studio Code 我常用的 extension 版本

### 如何匯出目前 VS Code 的擴展

要匯出您目前在 Visual Studio Code (VS Code) 中安裝的擴展，請按照以下步驟操作：

1. 打開 VS Code 的終端或命令提示符。
2. 執行以下命令來列出目前安裝的擴展並將其匯出到一個 `extensions.list` 文件中：

    ```shell
    code --list-extensions > extensions.list
    ```

    這條命令會將所有已安裝擴展的標識符列出並寫入到 `extensions.list` 文件中。

3. 您現在可以在當前目錄中找到名為 `extensions.list` 的文件，其中包含了您所有已安裝的 VS Code 擴展。

完成這些步驟後，您將擁有一個包含所有已安裝擴展的 `extensions.list` 文件，方便您在其他設備上重新安裝這些擴展或與他人分享您的擴展列表。



### 如何匯入備份安裝 VS Code 的擴展

如果您已經有一個 `extensions.list` 文件位於 `C:\Users\user\.vscode` 目錄中，並且想要從這個文件安裝 Visual Studio Code (VS Code) 擴展，請按照以下步驟操作：

1. 打開 PowerShell。
2. 切換到包含 `extensions.list` 文件的目錄，例如：`C:\Users\user\.vscode`。
3. 執行以下 PowerShell 命令來讀取 `extensions.list` 文件並安裝列出的擴展：

    ```powershell
    Get-Content .\extensions.list | ForEach-Object { code --install-extension $_ }
    ```

    這條命令會對 `extensions.list` 文件中的每一行（每個擴展的標識符）執行 `code --install-extension` 命令，從而安裝這些擴展。

4. 確保您的 VS Code 可執行文件 `code` 已經加入到環境變量中，這樣您才能在 PowerShell 或任何命令行界面中直接執行它。如果尚未將 VS Code 添加到環境變量，可以在 VS Code 中打開命令面板（快捷鍵 `Ctrl+Shift+P` 或 `Cmd+Shift+P`），然後輸入 `Shell Command: Install 'code' command in PATH` 來進行設定。

完成上述步驟後，您應該能夠成功從 `extensions.list` 文件安裝所有列出的 VS Code 擴展。

