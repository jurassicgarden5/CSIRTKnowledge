### オプション
|オプション | 説明 |
| ---- | ---- |
| -A	| OSとバージョンの検知 |
| -sL	| 指定したネットワーク内のホスト一覧を表示する（リストスキャン）|
-sP	pingに応答するホストの一覧を表示する（Pingスキャン）
-sS	TCPのSYNパケットを送ってSYN+ACKが返ってくるか調べる（TCP SYNスキャン/TCPハーフスキャン）
-sT	TCPでポートに接続できるか調べる（TCP Connectスキャン）
-sV	ソフトウェア名とバージョンの表示を有効にする
-sU	UDPポートをスキャンする（UDPスキャン）
-sF	FINフラグだけのパケットを送って調べる（TCP FINスキャン）
-sN	まったくフラグなしのパケットを送って調べる（TCP Nullスキャン）
-sX	FIN/PSH/URGフラグを立てたパケットを送って調べる（Xmasスキャン）
-sA	ACKフラグだけのパケットを送って調べる（TCP ACKスキャン）
-b FTP_HOST	FTP_HOSTのFTPサーバを利用して調べる（FTPバウンススキャン）
-O	OSを検出しようとする
-P0	Pingスキャンを行わない（アクティブなマシンを割り出すためのホスト発見プロセスが省略される）
-PS [PORTLIST]	PORTLISTで指定したポート（デフォルトは80番）にSYNフラグ付きの空TCPパケットを送信する（TCP SYN Ping）
-PA [PORTLIST]	PORTLISTで指定したポート（デフォルトは80番）にACKフラグ付きの空TCPパケットを送信する（TCP ACK Ping）
-PU [PORTLIST]	PORTLISTで指定したポート（デフォルトは31338番）に空UDPパケットを送信する（UDP Ping）
-PE [PORTLIST]	ICMPタイプ8（エコー要求）パケットをターゲットに送信する（ICMP Ping）
-PR	IPベースのスキャンより高速なARPスキャンを行う（ARP Ping）
-n	DNSによる逆引き名前解決を行わない
-R	すべてのターゲットに対して常にDNSによる逆引き名前解決を行う
-p PORT	スキャンするポートをPORTで指定する（1-1023、U:53,T:80）UはUDPポート、TはTCPポートを示す
-F	限定したポートのみ調べる（約1200ポート）
-r	調べるポートの順番を無作為（デフォルト）ではなく順に選ぶ
ターゲット
ターゲット	説明
IPADDR	IPアドレスで指定(「xxx.xxx.xxx.1-250」「xxx.xxx.xxx.1,3,5」といった指定も可能)
IPADDR/MASK	IPアドレスとサブネットマスクでNWの範囲を指定
HOSTNAME/MASK	HOSTNAMEで指定したホストのIPアドレスとサブネットマスクでNWの範囲を指定する
-iL TARGETFILE	ファイルTARGETFILEから指定するターゲットを読み込む
-iR NUM	NUMで指定した数のホストを無作為に生成する（0なら無制限）
--exclude HOST1,HOST2	指定したホストHOSTやネットワークをスキャン対象から除外
--excludefile EXCLUDE_FILE	ファイルEXCLUDE_FILEから除外するターゲットを読み込む
返り値のステータス
返り値のステータス	説明
open	ポートが開いている（TCPコネクションやUDPパケットをアクティブに受け入れている状態）
closed	ポートが閉じている（探査パケットを受け入れたり応答したりするが、待機しているアプリケーションがない）
filtered	パケットフィルタリングで、ポートが開いているかどうか判別できない
unfiltered	ポートにアクセスできるがポートが開いているかどうか判別できない
open/filtered	ポートが開いているのかパケットフィルタリングされているのか判別できない
closed/filtered	ポートが閉じているのかパケットフィルタリングされているのか判別できない
