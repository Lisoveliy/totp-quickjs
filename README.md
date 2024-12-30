# totp-quickjs

TOTP library for **quickjs** engine

## Features 
- Generation of HOTP values with `getHOTP` function
- Generation of TOTP values with `TOTP` class
- Support of `SHA-1`, `SHA-256`, `SHA-512` algorithms using `jsSHA` library
- Support of time offset for TOTP
- Support of digits more than 6

## Example of usage:

`@param {string} secret base32 encoded string`

`@param {string} issuer issuer of TOTP`

`@param {string} client client of TOTP`

`@param {number} [digits=6] number of digits in OTP token`

`@param {number} [fetchTime=30] period of token in seconds`

`@param {number} [timeOffset=0] time offset for token in seconds`

`@param {string} [hashType='SHA-1'] type of hash (more in jsSHA documentation)`
  
     const totp = new TOTP('secret', 'issuer', 'client', 6, 30, 0, 'SHA-1')
     const otp = totp.genOTP(Date.now())

     //result: otp: {
     //   otp: 'XXXXXX',
     //   createdTime: 'unixEpochCreationTime',
     //   expireTime: 'unixEpochExpireTime'
     //}
