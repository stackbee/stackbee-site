# stackbee-site

株式会社スタックビーのコーポレートサイト。**会社概要**と**電子公告**を掲載する。

公開URL: https://stack-bee.io/

---

## ⚠️ このサイトの重要性

`/koukoku/` は **登記簿に記載された法的な公告掲載先**である。

履歴事項全部証明書の「公告をする方法」に `https://stack-bee.io/koukoku/` が記載されており、
定款第4条にも同様の定めがある。**このページが恒常的に閲覧できない状態は、公告義務の履行に影響する。**

URL を変更する場合は**変更登記が必要**になるため、パスは動かさないこと。

---

## 構成

```
index.html          会社概要・事業内容
koukoku/index.html  電子公告
assets/style.css    スタイル（外部依存なし）
CNAME               カスタムドメイン設定（stack-bee.io）
```

外部のCDN・フォント・JSライブラリに依存していない。可用性を他サービスに預けないための意図的な設計。

## 公開の仕組み

- **ホスティング**: GitHub Pages（`main` ブランチのルート）
- **ドメイン**: `stack-bee.io`（レジストラは **Squarespace Domains**。Google Workspace 契約時に同時取得）
- **HTTPS**: GitHub Pages が Let's Encrypt で自動発行

### DNS

`stack-bee.io` は **Google Workspace のメールでも使用している**。

> ⚠️ **MX レコードは絶対に触らないこと。** 削除すると会社のメールが停止する。
> GitHub Pages 用に変更するのは **A レコード**と **CNAME（www）**のみ。

## 更新のしかた

### 方法1: ブラウザだけで更新（Gitの知識が不要）

1. GitHub でこのリポジトリを開く
2. 編集したいファイル（例: `koukoku/index.html`）をクリック
3. 鉛筆アイコン → 編集 → **Commit changes**
4. 1〜2分で https://stack-bee.io/ に反映される

### 方法2: ローカルから

```bash
git clone https://github.com/stackbee/stackbee-site.git
# 編集
git commit -am "update"
git push
```

## 決算公告の掲載手順

第1期は 2026年7月10日 ～ 2027年6月30日。定時株主総会は事業年度末日の翌日から3か月以内（定款第13条）＝ 2027年7月1日～9月30日。**その終結後に掲載する。**

1. `koukoku/index.html` の「掲載中の公告はありません」のブロックを、貸借対照表の要旨に差し替える
2. 掲載開始日を明記する
3. **掲載期間**（継続して掲載しておく必要がある期間）は税理士に確認すること

## 関連

- 経営記録・意思決定の台帳: `stackbee/biz-repo`（private）
- ドメインの引き継ぎ資料: Google Drive 共有ドライブ「会社運営」
