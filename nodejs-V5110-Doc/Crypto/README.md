# Table of Contents

- [Crypto](#crypto)
  - [Determining if crypto support is unavailable](#determining-if-crypto-support-is-unavailable)
  - [Class: Certificate](#class-certificate)
    - [new crypto.Certificate()](#new-cryptocertificate)
    - [certificate.exportChallenge(spkac)](#certificateexportchallengespkac)
    - [certificate.exportPublicKey(spkac)](#certificateexportpublickeyspkac)
    - [certificate.verifySpkac(spkac)](#certificateverifyspkacspkac)
  - [Class: Cipher](#class-cipher)
    - [cipher.final([output_encoding])](#cipherfinaloutput_encoding)
    - [cipher.setAAD(buffer)](#ciphersetaadbuffer)
    - [cipher.getAuthTag()](#ciphergetauthtag)
    - [cipher.setAutoPadding(auto_padding=true)](#ciphersetautopaddingauto_paddingtrue)
    - [cipher.update(data[, input_encoding][, output_encoding])](#cipherupdatedata-input_encoding-output_encoding)
  - [Class: Decipher](#class-decipher)
    - [decipher.final([output_encoding])](#decipherfinaloutput_encoding)
    - [decipher.setAAD(buffer)](#deciphersetaadbuffer)
    - [decipher.setAuthTag(buffer)](#deciphersetauthtagbuffer)
    - [decipher.setAutoPadding(auto_padding=true)](#deciphersetautopaddingauto_paddingtrue)
    - [decipher.update(data[, input_encoding][, output_encoding])](#decipherupdatedata-input_encoding-output_encoding)
  - [Class: DiffieHellman](#class-diffiehellman)
    - [diffieHellman.computeSecret(other_public_key[, input_encoding][, output_encoding])](#diffiehellmancomputesecretother_public_key-input_encoding-output_encoding)
    - [diffieHellman.generateKeys([encoding])](#diffiehellmangeneratekeysencoding)
    - [diffieHellman.getGenerator([encoding])](#diffiehellmangetgeneratorencoding)
    - [diffieHellman.getPrime([encoding])](#diffiehellmangetprimeencoding)
    - [diffieHellman.getPrivateKey([encoding])](#diffiehellmangetprivatekeyencoding)
    - [diffieHellman.getPublicKey([encoding])](#diffiehellmangetpublickeyencoding)
    - [diffieHellman.setPrivateKey(private_key[, encoding])](#diffiehellmansetprivatekeyprivate_key-encoding)
    - [diffieHellman.setPublicKey(public_key[, encoding])](#diffiehellmansetpublickeypublic_key-encoding)
    - [diffieHellman.verifyError](#diffiehellmanverifyerror)
  - [Class: ECDH](#class-ecdh)
    - [ecdh.computeSecret(other_public_key[, input_encoding][, output_encoding])](#ecdhcomputesecretother_public_key-input_encoding-output_encoding)
    - [ecdh.generateKeys([encoding[, format]])](#ecdhgeneratekeysencoding-format)
    - [ecdh.getPrivateKey([encoding])](#ecdhgetprivatekeyencoding)
    - [ecdh.getPublicKey([encoding[, format]])](#ecdhgetpublickeyencoding-format)
    - [ecdh.setPrivateKey(private_key[, encoding])](#ecdhsetprivatekeyprivate_key-encoding)
    - [ecdh.setPublicKey(public_key[, encoding])](#ecdhsetpublickeypublic_key-encoding)
  - [Class: Hash](#class-hash)
    - [hash.digest([encoding])](#hashdigestencoding)
    - [hash.update(data[, input_encoding])](#hashupdatedata-input_encoding)
  - [Class: Hmac](#class-hmac)
    - [hmac.digest([encoding])](#hmacdigestencoding)
    - [hmac.update(data[, input_encoding])](#hmacupdatedata-input_encoding)
  - [Class: Sign](#class-sign)
    - [sign.sign(private_key[, output_format])](#signsignprivate_key-output_format)
    - [sign.update(data[, input_encoding])](#signupdatedata-input_encoding)
  - [Class: Verify](#class-verify)
    - [verifier.update(data[, input_encoding])](#verifierupdatedata-input_encoding)
    - [verifier.verify(object, signature[, signature_format])](#verifierverifyobject-signature-signature_format)
  - [crypto module methods and properties](#crypto-module-methods-and-properties)
    - [crypto.DEFAULT_ENCODING](#cryptodefault_encoding)
    - [crypto.fips](#cryptofips)
    - [crypto.createCipher(algorithm, password)](#cryptocreatecipheralgorithm-password)
    - [crypto.createCipheriv(algorithm, key, iv)](#cryptocreatecipherivalgorithm-key-iv)
    - [crypto.createCredentials(details)](#cryptocreatecredentialsdetails)
    - [crypto.createDecipher(algorithm, password)](#cryptocreatedecipheralgorithm-password)
    - [crypto.createDecipheriv(algorithm, key, iv)](#cryptocreatedecipherivalgorithm-key-iv)
    - [crypto.createDiffieHellman(prime[, prime_encoding][, generator][, generator_encoding])](#cryptocreatediffiehellmanprime-prime_encoding-generator-generator_encoding)
    - [crypto.createDiffieHellman(prime_length[, generator])](#cryptocreatediffiehellmanprime_length-generator)
    - [crypto.createECDH(curve_name)](#cryptocreateecdhcurve_name)
    - [crypto.createHash(algorithm)](#cryptocreatehashalgorithm)
    - [crypto.createHmac(algorithm, key)](#cryptocreatehmacalgorithm-key)
    - [crypto.createSign(algorithm)](#cryptocreatesignalgorithm)
    - [crypto.createVerify(algorithm)](#cryptocreateverifyalgorithm)
    - [crypto.getCiphers()](#cryptogetciphers)
    - [crypto.getCurves()](#cryptogetcurves)
    - [crypto.getDiffieHellman(group_name)](#cryptogetdiffiehellmangroup_name)
    - [crypto.getHashes()](#cryptogethashes)
    - [crypto.pbkdf2(password, salt, iterations, keylen, digest, callback)](#cryptopbkdf2password-salt-iterations-keylen-digest-callback)
    - [crypto.pbkdf2Sync(password, salt, iterations, keylen, digest)](#cryptopbkdf2syncpassword-salt-iterations-keylen-digest)
    - [crypto.privateDecrypt(private_key, buffer)](#cryptoprivatedecryptprivate_key-buffer)
    - [crypto.privateEncrypt(private_key, buffer)](#cryptoprivateencryptprivate_key-buffer)
    - [crypto.publicDecrypt(public_key, buffer)](#cryptopublicdecryptpublic_key-buffer)
    - [crypto.publicEncrypt(public_key, buffer)](#cryptopublicencryptpublic_key-buffer)
    - [crypto.randomBytes(size[, callback])](#cryptorandombytessize-callback)
    - [crypto.setEngine(engine[, flags])](#cryptosetengineengine-flags)
  - [Notes](#notes)
    - [Legacy Streams API (pre Node.js v0.10)](#legacy-streams-api-pre-nodejs-v010)
    - [Recent ECDH Changes](#recent-ecdh-changes)
    - [Support for weak or compromised algorithms](#support-for-weak-or-compromised-algorithms)

# Crypto
`Crytpo`模組提供了包含OpenSSL's hash、HMAC、cipher、decipher、sign和verify等的加密的功能
用`require('crypto')`來載入這個模組
```javascript
const crypto = require('crypto');

const secret = 'abcdefg';
const hash = crypto.createHmac('sha256', secret)
                   .update('I love cupcakes')
                   .digest('hex');
console.log(hash);
  // Prints：
  //   c0fa1bc00531bd78ef38c628449c5102aeabd49b5dc3a2a516ea6ea959d6658e
```

## Determining if crypto support is unavailable
如果沒有載入`crypto`的模組支援的話Node.js是可以建立的，但在有些時候使用`require('crypto')`則會得到錯誤訊息
```javascript
var crypto;
try {
  crypto = require('crypto');
} catch (err) {
  console.log('crypto support is disabled!');
}
```

## Class: Certificate
SPKAC最初是由Netscape實現了一個證書簽名請求機制，目前正式指定為[HTML5的keygen元素](http://www.w3.org/TR/html5/forms.html#the-keygen-element)的一部分

`crypto`模組提供了`Certificate`類別和SPKAC數據的工作，最常見的用法是生成HTML5元素`<keygen>`的輸出處理
Node.js使用[OpenSSL的SPKAC](https://www.openssl.org/docs/apps/spkac.html)執行

### new crypto.Certificate()
要實例`Certificate`類別可以用關鍵字`new`或是直接呼叫`crypto.Certificate()`來當成一個函數
```javascript
const crypto = require('crypto');

const cert1 = new crypto.Certificate();
const cert2 = crypto.Certificate();
```

### certificate.exportChallenge(spkac)
`SPKAC`的資料結構包含了一個公開的key和challenge
`certificate.exportChallenge()`可以以一個Node.js Buffer的形式return chanllenge的部件
SPKAC參數可以是一個字串或Buffer
```javascript
const cert = require('crypto').Certificate();
const spkac = getSpkacSomehow();
const challenge = cert.exportChallenge(spkac);
console.log(challenge.toString('utf8'));
  // Prints the challenge as a UTF8 string
```

### certificate.exportPublicKey(spkac)
`SPKAC`的資料結構包含了一個公開的key和chanllenge
`certificate.exportPublicKey()`可以以一個Node.js Buffer的形式return 公開的key
`SPKAC`參數可以是一個字串或Buffer
```javascript
const cert = require('crypto').Certificate();
const spkac = getSpkacSomehow();
const publicKey = cert.exportPublicKey(spkac);
console.log(publicKey);
  // Prints the public key as <Buffer ...>
```

### certificate.verifySpkac(spkac)
如果`SPKAC`的資料結構式有效的會return `true`否則會return `false`
`SPKAC`參數必須是一個Node.js的Buffer
```javascript
const cert = require('crypto').Certificate();
const spkac = getSpkacSomehow();
console.log(cert.verifySpkac(new Buffer(spkac)));
  // Prints true or false
```

## Class: Cipher
`Cipher`類別常用於對資料進行加密，這個類別主要有兩個使用方式：
- 包裝成一個可以讀寫的stream，能寫入未加密資料或讀出加密資料
- 用cipher.update()或cipher.final()方法產生加密資料
crypto.createCipher() 或 crypto.createCipheriv()方法常用於創`Cipher`的實例，`Cipher`的物件不能使用`new`來創建

例：將`Cipher`物件封裝成stream：
```javascript
const crypto = require('crypto');
const cipher = crypto.createCipher('aes192', 'a password');

var encrypted = '';
cipher.on('readable', () => {
  var data = cipher.read();
  if (data)
    encrypted += data.toString('hex');
});
cipher.on('end', () => {
  console.log(encrypted);
  // Prints: ca981be48e90867604588e75d04feabb63cc007a8f8ad89b10616ed84d815504
});

cipher.write('some clear text data');
cipher.end();
```

例：使用`Cipher`和piped stream：
```javascript
const crypto = require('crypto');
const fs = require('fs');
const cipher = crypto.createCipher('aes192', 'a password');

const input = fs.createReadStream('test.js');
const output = fs.createWriteStream('test.enc');

input.pipe(cipher).pipe(output);
```

例：使用cipher.update() 和 cipher.final() 方法：
```javascript
const crypto = require('crypto');
const cipher = crypto.createCipher('aes192', 'a password');

var encrypted = cipher.update('some clear text data', 'utf8', 'hex');
encrypted += cipher.final('hex');
console.log(encrypted);
  // Prints: ca981be48e90867604588e75d04feabb63cc007a8f8ad89b10616ed84d815504
```

### cipher.final([output_encoding])
return剩餘的解密內容
如果`output_encoding`參數是`'binary'`、`'base64'`或`'hex'`中的一種，則返回一個字串
如果沒有提供`output_encoding`，則返回一個Buffer

一旦使用了`cipher.final()`方法後，`Cipher`物件就不能再用於加密
如果多次使用`cipher.final()`將會丟回錯誤

### cipher.setAAD(buffer)
當使用加密認證模式(目前只支援`GCM`)時，`cipher.setAAD()`方法用於輸入額外認證資料(AAD)參數的值

### cipher.getAuthTag()
當使用加密認證模式(目前只支援`GCM`)時，`cipher.getAuthTag()`方法會return一個包含認證標籤的buffer

`cipher.getAuthTag()`方法只能在cipher.final()方法後使用

### cipher.setAutoPadding(auto_padding=true)
當使用區塊加密演算法時，`Cipher`類別會自動填充輸入的資料到適當的區塊大小，如果要禁用預設填充可以用`cipher.setAutoPadding(false)`

當`auto_padding`的值是`false`時，輸入的資料長度必須是cipher區塊大小的倍數，否則cipher.final()會丟回錯誤
禁用自動填充是個有用的非標準填充，例如用0x0替代PKCS填充

`cipher.setAutoPadding()`方法必須在cipher.final()之後使用

### cipher.update(data[, input_encoding][, output_encoding])
用在更新資料`(data)`的cipher，如果有`input_encoding`的參數，那必須是`'utf8'`、`'ascii'`或`'binary'`
資料`(data)`參數須是一個指定編碼格式的字串，如果沒有`input_encoding`參數，資料`(data)`會是一個Buffer然後`input_encoding`會被忽略

`output_encoding`參數制定了加密資料輸出的編碼格式，可以是`'binary'`、`'base64'`或`'hex'`
如果`output_encoding`被指定了，則return指定編碼的相符字串，否則return一個Buffer

`cipher.update()`方法可以在cipher.final()使用前多次呼叫，如果在cipher.final()後使用會丟出錯誤

## Class: Decipher
`Deipher`類別常用於對資料進行解密，這個類別主要有兩個使用方式：
- 包裝成一個可以讀寫的stream，能寫入未加密資料或讀出加密資料
- 用decipher.update()或decipher.final()方法產生加密資料
crypto.createDecipher() 或 crypto.createDecipheriv()方法常用於創`Decipher`的實例，`Decipher`的物件不能使用`new`來創建

例：用`Decipher`物件封裝成stream：
```javascript
const crypto = require('crypto');
const decipher = crypto.createDecipher('aes192', 'a password');

var decrypted = '';
decipher.on('readable', () => {
  var data = decipher.read();
  if (data)
  decrypted += data.toString('utf8');
});
decipher.on('end', () => {
  console.log(decrypted);
  // Prints: some clear text data
});

var encrypted = 'ca981be48e90867604588e75d04feabb63cc007a8f8ad89b10616ed84d815504';
decipher.write(encrypted, 'hex');
decipher.end();
```

例：使用`Decipher`和piped stream：
```javascript
const crypto = require('crypto');
const fs = require('fs');
const decipher = crypto.createDecipher('aes192', 'a password');

const input = fs.createReadStream('test.enc');
const output = fs.createWriteStream('test.js');

input.pipe(decipher).pipe(output);
```

例：使用decipher.update()和decipher.final()方法：
```javascript
const crypto = require('crypto');
const decipher = crypto.createDecipher('aes192', 'a password');

var encrypted = 'ca981be48e90867604588e75d04feabb63cc007a8f8ad89b10616ed84d815504';
var decrypted = decipher.update(encrypted, 'hex', 'utf8');
decrypted += decipher.final('utf8');
console.log(decrypted);
  // Prints: some clear text data
```

### decipher.final([output_encoding])
return剩餘的解密內容
如果`output_encoding`參數是`'binary'`、`'base64'`或`'hex'`中的一種，則返回一個字串
如果沒有提供`output_encoding`，則返回一個Buffer

一旦使用了`decipher.final()`方法後，`Decipher`物件就不能再用於加密
如果多次使用`decipher.final()`將會丟回錯誤

### decipher.setAAD(buffer)
當使用加密認證模式(目前只支援`GCM`)時，`decipher.setAAD()`方法用於輸入額外認證資料(AAD)參數的值

### decipher.setAuthTag(buffer)
當使用加密認證模式(目前只支援`GCM`)時，`decipher.getAuthTag()`方法被用來傳遞接收到的認證標籤
如果沒有認證標籤，或加密內容被篡改，decipher.final()會被回傳，表示加密內容由於認證失敗而該放棄

### decipher.setAutoPadding(auto_padding=true)
當資料加密沒有使用標準的區塊填充，使用`decipher.setAutoPadding(false)`方法可以禁用自動填充
以防止decipher.final()方法檢查和移除填充

只有在輸入的資料長度為cipher區塊大小的倍數時才能關掉自動填充功能

`decipher.setAutoPadding()`方法必須在decipher.update()方法之前使用

### decipher.update(data[, input_encoding][, output_encoding])
用在更新資料`(data)`的decipher，如果有`input_encoding`的參數，那必須是`'binary'`、`'base64'`或`'hex'`
資料`(data)`參數須是一個指定編碼格式的字串，如果沒有`input_encoding`參數，資料會是一個Buffer然後`input_encoding`會被忽略

`output_encoding`參數制定了加密資料輸出的編碼格式，可以是`'binary'`、`'ascii'`或`'utf8'`
如果`output_encoding`被指定了，則return指定編碼的相符字串，否則return一個Buffer

`decipher.update()`方法可以在decipher.final()使用前多次呼叫，如果在decipher.final()後使用會丟出錯誤

## Class: DiffieHellman
### diffieHellman.computeSecret(other_public_key[, input_encoding][, output_encoding])
### diffieHellman.generateKeys([encoding])
### diffieHellman.getGenerator([encoding])
### diffieHellman.getPrime([encoding])
### diffieHellman.getPrivateKey([encoding])
### diffieHellman.getPublicKey([encoding])
### diffieHellman.setPrivateKey(private_key[, encoding])
### diffieHellman.setPublicKey(public_key[, encoding])
### diffieHellman.verifyError
## Class: ECDH
### ecdh.computeSecret(other_public_key[, input_encoding][, output_encoding])
### ecdh.generateKeys([encoding[, format]])
### ecdh.getPrivateKey([encoding])
### ecdh.getPublicKey([encoding[, format]])
### ecdh.setPrivateKey(private_key[, encoding])
### ecdh.setPublicKey(public_key[, encoding])
## Class: Hash
### hash.digest([encoding])
### hash.update(data[, input_encoding])
## Class: Hmac
### hmac.digest([encoding])
### hmac.update(data[, input_encoding])
## Class: Sign
### sign.sign(private_key[, output_format])
### sign.update(data[, input_encoding])
## Class: Verify
### verifier.update(data[, input_encoding])
### verifier.verify(object, signature[, signature_format])
## crypto module methods and properties
### crypto.DEFAULT_ENCODING
### crypto.fips
### crypto.createCipher(algorithm, password)
### crypto.createCipheriv(algorithm, key, iv)
### crypto.createCredentials(details)
### crypto.createDecipher(algorithm, password)
### crypto.createDecipheriv(algorithm, key, iv)
### crypto.createDiffieHellman(prime[, prime_encoding][, generator][, generator_encoding])
### crypto.createDiffieHellman(prime_length[, generator])
### crypto.createECDH(curve_name)
### crypto.createHash(algorithm)
### crypto.createHmac(algorithm, key)
### crypto.createSign(algorithm)
### crypto.createVerify(algorithm)
### crypto.getCiphers()
### crypto.getCurves()
### crypto.getDiffieHellman(group_name)
### crypto.getHashes()
### crypto.pbkdf2(password, salt, iterations, keylen, digest, callback)
### crypto.pbkdf2Sync(password, salt, iterations, keylen, digest)
### crypto.privateDecrypt(private_key, buffer)
### crypto.privateEncrypt(private_key, buffer)
### crypto.publicDecrypt(public_key, buffer)
### crypto.publicEncrypt(public_key, buffer)
### crypto.randomBytes(size[, callback])
### crypto.setEngine(engine[, flags])
# Notes
## Legacy Streams API (pre Node.js v0.10)
## Recent ECDH Changes
## Support for weak or compromised algorithms
