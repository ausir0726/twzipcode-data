# TwZipcode
> 開發用中華郵政郵遞區號 / Taiwan zipcodes for developers.


1. 將[中華郵政](www.post.gov.tw)的**「臺灣地區郵遞區號前3碼一覽表 103/12(Excel版)」**轉成js，方便開發時可直接引用。
2. 英文譯名來自於[地名資訊服務網](gn.moi.gov.tw)的**「臺灣地區鄉鎮市區級以上行政區域名稱中英對照表.pdf」**。

## Install

### Bower
```sh
bower install twzipcode-data
```

### npm
```sh
npm install twzipcode-data --save-dev
```

## 用法 Usage
```javascript
import twzipcode from 'twzipcode-data'

// 英文
let data_en = twzipcode('en')

// 預設中文
let data = twzipcode()

// 所有縣市
let counties = data.counties

// 所有郵遞區號
let zipcodes = data.zipcodes

// 以縣市名稱分組的郵遞區號
let zipcodesGroupByCounty = data.computed.groupByCounty

// 以郵遞區號為key的郵遞區號
let zipcodesKeyByZipcode = data.computed.keyByZipcode

```

## 資料結構 / Data Structure

### 縣市 / County Object
| 參數    | 說明           |
|---------|---------------|
| id      | 中文名稱       |
| name    | 縣市名稱       |

### 郵遞區號 / Zipcode Object
| 參數    | 說明           |
|---------|---------------|
| id      | 3碼郵遞區號    |
| county  | 縣、市或直轄市中文名稱 |
| city    | 鄉鎮市區中文名稱 |

## Build Setup

``` bash
# install dependencies
npm install

# run tests
npm run test

# build for production with minification
npm run build
```

## i18n
1. In `./src/{locale}`, add `counties.js` and `zipcodes.js`.
2. In `./test`, add `integrity.test.{locale}.js`.
3. In `.src/locales.js`, append `{locale}` to export array.

See [src/zh-tw](src/zh-tw).

## vue-twzipcode
中華郵政郵遞區號 Vuejs components：[vue-twzipcode](https://github.com/yyc1217/vue-twzipcode)