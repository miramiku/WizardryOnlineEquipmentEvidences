# Cypress 装備エビデンス
[Cypress](https://miramiku.github.io/Cypress/) で利用する装備データの根拠およびデータ品質保持用の**画像コレクション**です。
その画像の事を該当する装備データの**エビデンス**と呼んでいます。

## 分類方法
本来ならばデータベースに記載されているカタログ番号をファイル名にしたいところですが、カタログ番号が現在不定のため装備名で命名されています。
画像ファイルは装備分類でフォルダ分けされており、フォルダ名は分類の英語名をキャメルケースで命名されています。

### 装備分類・フォルダ名対応表
| 分類     | フォルダ名          |
| :------- | :------------------ |
| 片手剣   | OneHandedSwords     |
| 両手剣   | TwoHandedSwords     |
| 片手斧   | OneHandedAxes       |
| 両手斧   | TwoHandedAxes       |
| 片手鈍器 | OneHandedClubs      |
| 両手鈍器 | TwoHandedClubs      |
| 槍       | Spears              |
| 暗器     | HandWeapons         |
| 短剣     | Daggers             |
| 両手杖   | TwoHandedStaffs     |
| 刀       | Katanas             |
| 双刃     | DoubleBladedWeapons |
| 弓       | Bows                |
| 矢       | Arrows              |
| 銃       | Guns                |
| 弾       | Bullets             |
| 兜       | Helmets             |
| 帽子     | Hats                |
| 頭巾     | Hoods               |
| 鎧       | Armors              |
| 外衣     | Coasts              |
| 上衣     | Tops                |
| 脚鎧     | Greaves             |
| 衣服     | bottoms             |
| 下衣     | Bottoms             |
| 手甲     | Gauntlets           |
| 手袋     | Gloves              |
| 腕輪     | Bracelets           |
| 鉄靴     | SolidShoes          |
| 革靴     | LeatherShoes        |
| 靴       | Shoes               |
| 大型盾   | LargeShields        |
| 中型盾   | MediumShields       |
| 小型盾   | SmallShields        |
| マント   | Capes               |
| 指輪     | Rings               |
| 耳飾り   | Earrings            |
| 首飾り   | Necklaces           |
| ベルト   | Belts               |

`＊`（全角アスタリスク）のフォルダはエビデンスの要求用件を満たさない装備品の画像です。
参考として利用し要求用件を満たす画像の入手が出来次第削除します。

## 画像の仕様（エビデンスの要求用件）
* ファイル名： 装備データ中の装備名と同等
* ファイル形式： JPEG
* 縦幅： 不定
* 横幅： `270px` （固定）

### エビデンスとして好ましい装備
* ランダムパラメータの項目が少ない
* 特殊な能力が少ない（付与されていないものが望ましい）
	* 耐久値・重量・GP は避けたい（装備の性能値が直接書きかえられる）
		* 重量補正値の末尾が `0` は避けたい（計算ミスを行うリスクが高まる）
* ジェムソケットが少ない（ジェムソケットがないものが望ましい）
* 未強化であること
* オークションから取得する場合、コメントがないこと

### 撮影に関して
* 無地の黒背景が望ましい
	* 実用的にはレーヴェンアンタイルの空を利用している
* 装備可能なキャラクターで撮影するのが望ましい（赤文字はつぶれてしまう）

### その他
撮影状況により画像の背景にキャラクター名が写り込んでいることがありますが目をつぶって見なかったことにしてください。

## エビデンスの存在確認方法
### データベース原本
* [equipment.json](https://dl.dropboxusercontent.com/u/6164477/wizon/equipment.json)

```` javascript
"5101553":[51,"3周年記念ウサギリュック",5,1,0,0,0,0,0,40,0.3,1,0,0,0,1023,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,1,0,0,0,0,0,1,-1,"","クリティカル耐性上昇",1,"",0,"3rd anniversary.<br>thank you for playing!","","","",1]
````

オブジェクトの値（配列）の `index: 64` （６５番目・末尾）が `false (0)` の場合はエビデンスがない装備になります。
上記のサンプルコードの場合は `1` つまり `true` ですのでエビデンスが存在するということを示しています。

### スプレッドシート （ Excel ファイル）
* [equipment.db.xlsm](https://onedrive.live.com/redir?resid=716b8a626fb713c5!2372&authkey=!AFFFx02yh8Ck5Ss&ithint=file%2cxlsm)

`BZ` 列がエビデンスの有無を保持しており `true` の場合はエビデンスが存在し、 `false` の場合はエビデンスが存在しないことを示しています。

### エビデンスが存在しない装備のリスト
* [要データ取得装備リスト](https://miramiku.github.io/post/wizon/non-evidence-list/)

このリストはデータベース原本から生成されております。
そのため、ここに記載されている装備はエビデンスがないということを表しています。

## エビデンスの提供
エビデンスをお持ちの方はエビデンスの要求用件に合致する画像（整形は必要ありません）を提供していただけると幸いです。

1. [dbinbox](https://dbinbox.com/miramiku) で送付（簡単でおすすめ）
1. [ファイルリクエスト](https://www.dropbox.com/request/6YQlM4clyqPDsY88eKV4) を利用（安全ですが氏名とメールアドレスの記入が必要）
1. このリポジトリにコントリビュートするまたはプルリクエストを送る（全ファイルをローカルに同期する事になるのでおすすめできません）

## スクリーンショットに関する著作権表記
"Wizardry(R)" of GMO Gamepot Inc. All rights reserved.<br>
Wizardry Renaissance(TM) (c)2009 GMO Gamepot Inc. All rights reserved.
