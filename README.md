# 巡回ルート最適化

今日行く場所（最大10ヶ所）を地図で選ぶと、家から全部回って帰る最短の順番と道順を表示するウェブアプリです。HTML 1ファイル（`index.html`）だけで動きます。

## できること

- 店舗・施設・住所を検索して行き先に追加（地図をクリックして追加することもできます）
- 車・自転車・徒歩の所要時間をもとに、回る順番を最適化
- 行き先ごとの営業時間と滞在時間を考えて、閉店に間に合う順番を選ぶ
- 選んだ順番のまま Google マップのナビを開く

## 順番の決め方

道路網上の最短経路で、家と各行き先のすべての組の所要時間を求め、時間枠付き巡回セールスマン問題として解いています。解き方は Held-Karp 法（動的計画法）を営業時間に合わせて広げたもので、全通りを比べたのと同じ最適解になります。

## 使っているデータ・サービス

- 施設検索: [OpenPOI API](https://openpoiapi.com/attribution.html)
- 地図: [地理院タイル](https://maps.gsi.go.jp/development/ichiran.html)
- 住所・地名検索: 国土地理院
- OpenStreetMap の検索: [Photon（komoot）](https://photon.komoot.io/)
- 経路: [FOSSGIS OSRM](https://routing.openstreetmap.de/about.html)、[OSRM](https://project-osrm.org/)（© [OpenStreetMap contributors](https://www.openstreetmap.org/copyright)）
