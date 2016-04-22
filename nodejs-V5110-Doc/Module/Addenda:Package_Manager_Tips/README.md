#Addenda: Package Manager Tips

Node.js 的 require() 函式被設計為足以支援大量合理的目錄結構 Package 管理程序 如 dpkg, rpm, and npm 將能從未經修改的 Node.js 模組中找到可以建立的本地端 packages 。

以下為一個建議的目錄結構:

比方說我們希望目錄結構為 /usr/lib/node/<some-package>/<some-version> 擁有特定版本的 package 內容 。

Packages 可以互相依賴 。 比如說如果要安裝 package foo 可能會需要某個特定版本的 package bar 。bar package 本身具有相關性，在一些情況下這些依賴關係也有可能發生衝突或循環 。

Node.js 查詢任何載入模組的真實路徑(解析符號連結)然後尋找依賴於node_modules文件裡的描述，這種情況可以使用下方的架構解決 。

```javescript
/usr/lib/node/foo/1.2.3/ - foo package 版本為 1.2.3 的內容。
/usr/lib/node/bar/4.3.2/ - foo 依賴於 bar package 的內容
/usr/lib/node/foo/1.2.3/node_modules/bar - 符號連結於 /usr/lib/node/bar/4.3.2/.
/usr/lib/node/bar/4.3.2/node_modules/* - bar package 依賴的符號連結 。
```

因此，即使遇到循環或者衝突，每個模組都能得到一個可以使用的模組版本 。

所以當 foo package 使用 require('bar')方法，他將會取得 /usr/lib/node/foo/1.2.3/node_modules/bar 中的版本 。
而當 bar package 使用 require('quux')方法，他將會取得 /usr/lib/node/bar/4.3.2/node_modules/quux 中的版本 。

此外，為了使模組的查詢過程優話，可以將它們放在 /usr/lib/node_modules/<name>/<version> 目錄底下 。 那麼 Node.js 將不會刻意尋找缺少的依賴關係 。

為了提供給 Node.js 的 REPL 模組，將 /usr/lib/node_modules 檔案加入到 $NODE_PATH 環境變數可能是有用的 。

因為使用 node_modules 檔案尋找模組都是相對的，並且基於檔案的真實路徑呼叫 require()，package 本身是可以在任何地方 。
