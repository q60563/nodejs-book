# Table of Contents

- Crypto
  - Determining if crypto support is unavailable
  - Class: Certificate
    - new crypto.Certificate()
    - certificate.exportChallenge(spkac)
    - certificate.exportPublicKey(spkac)
    - certificate.verifySpkac(spkac)
  - Class: Cipher
    - cipher.final([output_encoding])
    - cipher.setAAD(buffer)
    - cipher.getAuthTag()
    - cipher.setAutoPadding(auto_padding=true)
    - cipher.update(data[, input_encoding][, output_encoding])
  - Class: Decipher
    - decipher.final([output_encoding])
    - decipher.setAAD(buffer)
    - decipher.setAuthTag(buffer)
    - decipher.setAutoPadding(auto_padding=true)
    - decipher.update(data[, input_encoding][, output_encoding])
  - Class: DiffieHellman
    - diffieHellman.computeSecret(other_public_key[, input_encoding][, output_encoding])
    - diffieHellman.generateKeys([encoding])
    - diffieHellman.getGenerator([encoding])
    - diffieHellman.getPrime([encoding])
    - diffieHellman.getPrivateKey([encoding])
    - diffieHellman.getPublicKey([encoding])
    - diffieHellman.setPrivateKey(private_key[, encoding])
    - diffieHellman.setPublicKey(public_key[, encoding])
    - diffieHellman.verifyError
  - Class: ECDH
    - ecdh.computeSecret(other_public_key[, input_encoding][, output_encoding])
    - ecdh.generateKeys([encoding[, format]])
    - ecdh.getPrivateKey([encoding])
    - ecdh.getPublicKey([encoding[, format]])
    - ecdh.setPrivateKey(private_key[, encoding])
    - ecdh.setPublicKey(public_key[, encoding])
  - Class: Hash
    - hash.digest([encoding])
    - hash.update(data[, input_encoding])
  - Class: Hmac
    - hmac.digest([encoding])
    - hmac.update(data[, input_encoding])
  - Class: Sign
    - sign.sign(private_key[, output_format])
    - sign.update(data[, input_encoding])
  - Class: Verify
    - verifier.update(data[, input_encoding])
    - verifier.verify(object, signature[, signature_format])
  - crypto module methods and properties
    - crypto.DEFAULT_ENCODING
    - crypto.fips
    - crypto.createCipher(algorithm, password)
    - crypto.createCipheriv(algorithm, key, iv)
    - crypto.createCredentials(details)
    - crypto.createDecipher(algorithm, password)
    - crypto.createDecipheriv(algorithm, key, iv)
    - crypto.createDiffieHellman(prime[, prime_encoding][, generator][, generator_encoding])
    - crypto.createDiffieHellman(prime_length[, generator])
    - crypto.createECDH(curve_name)
    - crypto.createHash(algorithm)
    - crypto.createHmac(algorithm, key)
    - crypto.createSign(algorithm)
    - crypto.createVerify(algorithm)
    - crypto.getCiphers()
    - crypto.getCurves()
    - crypto.getDiffieHellman(group_name)
    - crypto.getHashes()
    - crypto.pbkdf2(password, salt, iterations, keylen, digest, callback)
    - crypto.pbkdf2Sync(password, salt, iterations, keylen, digest)
    - crypto.privateDecrypt(private_key, buffer)
    - crypto.privateEncrypt(private_key, buffer)
    - crypto.publicDecrypt(public_key, buffer)
    - crypto.publicEncrypt(public_key, buffer)
    - crypto.randomBytes(size[, callback])
    - crypto.setEngine(engine[, flags])
  - Notes
    - Legacy Streams API (pre Node.js v0.10)
    - Recent ECDH Changes
    - Support for weak or compromised algorithms


# Crypto
# Determining if crypto support is unavailable
# Class: Certificate
### new crypto.Certificate()
### certificate.exportChallenge(spkac)
### certificate.exportPublicKey(spkac)
### certificate.verifySpkac(spkac)
# Class: Cipher
### cipher.final([output_encoding])
### cipher.setAAD(buffer)
### cipher.getAuthTag()
### cipher.setAutoPadding(auto_padding=true)
### cipher.update(data[, input_encoding][, output_encoding])
# Class: Decipher
### decipher.final([output_encoding])
### decipher.setAAD(buffer)
### decipher.setAuthTag(buffer)
### decipher.setAutoPadding(auto_padding=true)
### decipher.update(data[, input_encoding][, output_encoding])
# Class: DiffieHellman
### diffieHellman.computeSecret(other_public_key[, input_encoding][, output_encoding])
### diffieHellman.generateKeys([encoding])
### diffieHellman.getGenerator([encoding])
### diffieHellman.getPrime([encoding])
### diffieHellman.getPrivateKey([encoding])
### diffieHellman.getPublicKey([encoding])
### diffieHellman.setPrivateKey(private_key[, encoding])
### diffieHellman.setPublicKey(public_key[, encoding])
### diffieHellman.verifyError
# Class: ECDH
### ecdh.computeSecret(other_public_key[, input_encoding][, output_encoding])
### ecdh.generateKeys([encoding[, format]])
### ecdh.getPrivateKey([encoding])
### ecdh.getPublicKey([encoding[, format]])
### ecdh.setPrivateKey(private_key[, encoding])
### ecdh.setPublicKey(public_key[, encoding])
# Class: Hash
### hash.digest([encoding])
### hash.update(data[, input_encoding])
# Class: Hmac
### hmac.digest([encoding])
### hmac.update(data[, input_encoding])
# Class: Sign
### sign.sign(private_key[, output_format])
### sign.update(data[, input_encoding])
# Class: Verify
### verifier.update(data[, input_encoding])
### verifier.verify(object, signature[, signature_format])
# crypto module methods and properties
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
### Legacy Streams API (pre Node.js v0.10)
### Recent ECDH Changes
### Support for weak or compromised algorithms