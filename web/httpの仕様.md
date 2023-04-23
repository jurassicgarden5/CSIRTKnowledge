### レスポンス
| ステータスコード | 内容 |
| --- | --- |
| 1xx | 処理が継続 |
| 2xx | 正常終了 |
| 3xx | リダイレクト |
| 4xx | クライアントエラー |
| 5xx  |  サーバエラー |

### パラメータ
* hiddenパラメータ
  * 利用者自身が書き換えできるものの、情報漏洩や第三者からの書き換えには堅牢

### http認証
* Basic認証
  * AuthorizationヘッダはIDとPWを：で区切ってつなげてbase64エンコードしたもの
  * 一度認証すると同じディレクトリへのリクエストにはブラウザが自動的にAuthorizationヘッダ付与

### cookie
* Domain属性：何も設定しないが一番安全
* HttpOnly属性：XSS対策として一定有効
* SameSite属性：CSRF対策として一定有効

### 同一オリジンポリシー
javascriptなどクライアントスクリプトからサイトをまたがったアクセスを禁止
#### クロスドメインが許可されている機能
* iframe要素
* img要素：src属性で指定可能
* script要素：src属性で指定可能（他のサイトからjavascriptを読み込み可能
* CSS
* from要素：action属性
  * submitはjavascriptからも常に操作可能（この仕様がCSRFの原因）

### CORS
情報提供元がAccess-Control-Allow-Origin：<情報依頼元のURL> のレスポンスヘッダを送信した場合にXMLHttpRequestが可能



