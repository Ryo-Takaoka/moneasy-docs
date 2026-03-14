# App Store Connect プライバシーラベル申告チェックリスト

## moneasy 用設定手順

App Store Connect → アプリ → App のプライバシー → 編集

---

## 収集するデータカテゴリ

### 1. Financial Info（財務情報）
- **データの種類:** その他の財務情報
- **利用目的:** App Functionality（アプリの機能）
- **データの収集方法:** User Provided（ユーザーが提供）
- **ユーザーとの関連付け:** いいえ（ローカル保存のみ）
- **トラッキングに使用:** いいえ

### 2. Photos or Videos（写真またはビデオ）
- **データの種類:** 写真
- **利用目的:** App Functionality（レシートOCR処理）
- **データの収集方法:** User Provided（ユーザーが任意で提供）
- **ユーザーとの関連付け:** いいえ
- **トラッキングに使用:** いいえ
- **注意:** レシート画像はOCR処理のためにGoogle Gemini Flash APIに送信されます。画像はAPIによって保存されません。

### 3. Diagnostics（診断）
- **データの種類:** クラッシュデータ
- **利用目的:** App Functionality
- **データの収集方法:** Automatically Collected
- **ユーザーとの関連付け:** いいえ
- **トラッキングに使用:** いいえ

---

## 収集しないデータカテゴリ（明示的にチェックしないこと）

以下は一切収集していません：
- [ ] Contact Info（連絡先情報）
- [ ] Health & Fitness（ヘルスケア＆フィットネス）
- [ ] Location（位置情報）
- [ ] Sensitive Info（機密情報）
- [ ] Contacts（連絡先）
- [ ] User Content（ユーザーコンテンツ）— ※レシート画像はPhotosカテゴリで申告
- [ ] Browsing History（閲覧履歴）
- [ ] Search History（検索履歴）
- [ ] Identifiers（識別子）
- [ ] Purchases（購入）— ※App内課金はAppleが処理、開発者は収集しない
- [ ] Usage Data（使用状況データ）

---

## サードパーティへのデータ送信

### Google Gemini Flash API
- **送信データ:** レシート画像（OCR処理時のみ）
- **目的:** テキスト抽出・支出情報の構造化
- **保存:** APIは画像を保存しない
- **オプション:** Pro機能のみ、ユーザーが能動的に使用
- **Privacy Policy:** https://policies.google.com/privacy

### Apple CloudKit
- **送信データ:** 財務データ（支出・収入・予算等）
- **目的:** iCloud同期（オプション機能）
- **暗号化:** 家族共有データはHKDF(SHA-256)で暗号化
- **Privacy Policy:** https://www.apple.com/legal/privacy/

---

## App Store Connect 設定手順

1. App Store Connect にログイン
2. 「マイApp」→ moneasy を選択
3. 左メニューの「App のプライバシー」をクリック
4. 「データ収集の管理」→「はじめる」
5. 上記のカテゴリに従ってチェックを入れる
6. 各カテゴリの詳細設定で利用目的・関連付け・トラッキングを設定
7. 「公開」をクリック

---

## プライバシーポリシーURL

App Store Connect → アプリ情報 → プライバシーポリシーURL:
```
https://yuriti-1.github.io/moneasy/privacy-policy/
```

## サポートURL

App Store Connect → アプリ情報 → サポートURL:
```
https://yuriti-1.github.io/moneasy/support/
```
