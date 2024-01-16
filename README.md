# URLとは
URLとは、Uniform Resource Locatorの略語で、**Webサイトのページがどこに位置するのかを示す**「**住所**」のような意味合いで使われる。  
インターネットには、膨大な量の情報が点在しており、目的の情報を見つけ出すためには、URLを使って情報の位置を探し出す必要がある。  

URLは「http://」や「https://」から始まり、その後にドメイン名（Webサイトの名前）が続く形で構成されている。  
`たとえば、「http://java.jp/test/index.html」というURLは、`  
`「HTTPプロトコルでアクセスできる、java.jpサーバ上の、testフォルダ内のindex.html」を意味する。`

### 短縮URL
元の長いURLを短くしたもので、URLを入力すると、もとの長いURLに繋がるようにリダイレクトする仕組みになっている。
長いURLは見た目が乱雑に見えるうえに、コピー＆ペーストが困難な場合が多いため、短縮URLが開発された。
> [!CAUTION]
> URLを短縮している以上、フィッシング詐欺の偽装サイトなどに悪用されるケースもあり、注意が必要。

# クエリ文字列とは
クエリ文字列（URLパラメーター）とは、**サーバーに情報を送るためにURLの末尾につけ足す文字列**（**変数**）のこと。  
「?」をURLの末尾につけ、その次に「パラメーター＝値」をつけ、複数のパラメーターをつけたい場合は「&」を使用する。  
この形式で、サーバーに送信したいデータをURLにつけ加えることが可能。

例えば、基本のURLが「https:// ○△×□.jp/」だとして、  
基本のURLにクエリ文字列（URLパラメーター）を加えると「https:// ○△×□.jp/?●=▲×■&○=△×□」となる。  
`URLの「?●=▲×■&○=△×□」の部分が、クエリ文字列（URLパラメーター）。`

> [!CAUTION]
> 1. 標準的なパラメーターを使用する！
>    * 「=」の代わりに「:」や「,」を使用したり、「&」の代わりに「[]」を使用したりする非標準パラメーターを使用すると、検索エンジンにうまく読み取ってもらえない可能性がある。
> 1. パラメーターにおいて、「?」は一度だけ！
>    * 「?」を使用するのは、パラメーターの頭部分だけです。2つ以上入れると、URLがうまく機能しなくなる。
> 1. ページ内リンクは一番後ろに設置する！
>    * パラメーターとページ内リンクが逆になると、ページ内リンクが作動しなくなってしまう。

# パス変数(パスパラメータ)とは

# クエリ文字列とパス変数の違いとは

# HTTPメソッドとは
Webでは、クライアントコンピュータの**ブラウザから送信されるHTTPリクエスト**に従って、サーバの処理が行われ、  
**クライアントから発信されるHTTPリクエスト**は、どのリソースに対して何をしたいかを指示する必要がある。  
`「どの」リソースかは、URLで決定されますが、「何をしたいか」は別に指示する必要があるので、そのために使用するのがHTTPメソッドという。`

|HTTPメソッド|意味|
|:---:|:---|
|GET|リソース情報を取得する。|
|POST|新しいリソース情報を送り込む。|
|PUT|リソース情報を新しい情報で置き換える。|
|PATCH|リソース情報の一部を新しい情報で書き換える。|
|DELETE|リソース情報を削除する。|

# リクエストヘッダーとは
HTTPリクエストヘッダーとは、Webコンテンツの伝送に用いられるHTTPで、  
`クライアントからサーバへの要求であるHTTPリクエストの前半にある制御情報を記した領域のこと。`  

例えばUser-Agent、Referer、Cookieなどがある。

### リクエストでよく使われるヘッダーフィールド
|フィールド名|意味|
|:---:|:---|
|Accept|受理可能なメディア|
|Acccept-Charset|受理可能な文字セット|
|Accept-Encoding|受理可能なエンコーディング|
|Accept-Language|受理可能な言語|
|Authorization|認証のために提供する情報（IDやパスワードなど）|
|Connection|接続状態に関する通知（リクエスト処理後は即座に切断など）|
|Cookie|持っているCookie情報|
|Ecpect|期待するステータスコード|
|From|メールアドレス|
|Host|ホスト名|
|If-Match|条件に合致すればメソッドを実行|
|If-Modified-Since|指定日時よりも最近に更新されていたらメソッドを実行|
|If-None-Match|条件に合致しないならメソッドを実行|
|If-Unmodified-Since|指定日時よりも最近に更新されていなければメソッドを実行|
|Range|取得する範囲|
|Referer|参照元のURI|
|User-Agent|プラウザやクライアントプログラムの名称やバージョン|

参考:[完全解説：HTTPヘッダーとは？それを確認する方法を紹介](https://apidog.com/jp/blog/how-to-check-http-headers/)

# HTTPステータスコードとは
ウェブサイトを閲覧するウェブブラウザから送られる**リクエスト**に対し、ウェブサーバーから返信される**レスポンス内容**を表す**3桁の数字**のこと。  
噛み砕いていうと、私たちサイトを運営している時に、「PCやスマホの画面にこのウェブサイトを表示させたい」というリクエストに対し、  
「現在このサイトは表示できません」「このサイトはURLが変更になりました」などの`ウェブサーバーからのレスポンスを表す数字がステータスコードという。`

![HTTPレスポンスで実行結果やHTMLが返送される](https://digiful.irep.co.jp/hs-fs/hubfs/76975541525_02.jpg?width=1600&name=76975541525_02.jpg)  
参考:[DIGIFUL](https://digiful.irep.co.jp/blog/76975541525)

### HTTPステータスコードの意味
|コード|意味|
|:---:|:---|
|200|OK【成功】。リクエスト成功。|
|202|Accepted【受理完了】。リクエストは受理されたが、まだ実行されていない。|
|400|Bad Request【不正】。リクエストが無効。|
|404|Not Found【未検出】。リソース・ページが存在しない。|
|500|Internal Server Error【サーバーエラー】。サーバー内部エラー。|

# レスポンスヘッダーとは
HTTPレスポンスヘッダ（HTTP response header）とは、Webコンテンツの伝送に用いられるHTTPで、  
`サーバからクライアントへの応答であるHTTPレスポンスの前半にある制御情報を記した領域のこと。` 

例えばServer、Set-Cookie、Content-Typeなど。

### レスポンスでよく使われるヘッダーフィールド
|フィールド名|意味|
|:---:|:---|
|Accept-Ranges|範囲として指定可能な単位|
|Allow|受理可能なメソッド|
|Cache-Control|キャッシュに対する制御情報|
|Connection|接続状態に関する通知(リクエスト処理後は即座に切断など)|
|Content-Encoding|内容のエンコーディング|
|Content-Language|内容の言語|
|Content-Length|内容のサイズ|
|Content-Type|内容のメディアタイプ(形式)|
|Date|生成した日時|
|ETag|内容を要約する情報(この変化により更新がわかる)|
|Expires|内容を古いと見なせる日時|
|Last-Modified|内容の最終更新日時|
|Retry-After|再リクエストまでの時間の要請|
|Server|サーバープログラムの名称やバージョン|
|Set-Cookie|保存すべきCookie情報|
|Transfer-Encoding|内容の転送に使用する形式(チャンク形式、圧縮形式など)
|Vary|レスポンス生成に影響を及ぼした可能性のあるヘッダー
|WWW-Authenticate|認証に関する基本情報(要求する認証の種類、領域名)


参考:[完全解説：HTTPヘッダーとは？それを確認する方法を紹介](https://apidog.com/jp/blog/how-to-check-http-headers/)

# レスポンスボディとは

# JSONとは

# JSONを使ってなにかのデータを表現してください
たとえば、ユーザー情報や商品情報など
