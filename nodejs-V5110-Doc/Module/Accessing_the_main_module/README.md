#Accessing the main module

當一個檔案直接從 Node.js 執行,且 require.main 為其模組 。這代表著你可以藉此測試其檔案是否已被執行 。 


```javascript
require.main === module
```

對於 foo.js 而言，當執行過 node foo.js時結果為true，但如果運行 require('./foo') 結果為 false 。

因為模組提供了檔案名稱的屬性 (通常為 __filename )， 能藉由檢查 require.main.filename 取得當前應用程序的入口點 。 .