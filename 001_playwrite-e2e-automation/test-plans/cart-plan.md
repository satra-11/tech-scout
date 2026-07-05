# テスト計画書: カート金額計算テスト

## 1. テスト概要
- **テストケース**: `test-cases/cart.md`
- **対象システム**: Saucedemo (`https://www.saucedemo.com/`)
- **目的**: 商品をカートに追加し、チェックアウト画面での合計金額（Item total + Tax = Total）の計算結果が正しいかを厳密に検証する。

## 2. 前提条件
- テスト環境へアクセス可能であること。
- テスト用アカウント（`standard_user` / `secret_sauce`）が利用可能であること。

## 3. テストデータ
- **追加商品**: Sauce Labs Backpack ($29.99)
- **宛先情報**:
  - First Name: `Taro`
  - Last Name: `Yamada`
  - Zip/Postal Code: `123-4567`

## 4. テスト実行手順
1. `https://www.saucedemo.com/` にアクセスする。
2. `standard_user` / `secret_sauce` でログインする。
3. 「Sauce Labs Backpack」の「Add to cart」をクリックする。
4. カートアイコンをクリックして `/cart.html` に遷移する。
5. 「Checkout」をクリックして `/checkout-step-one.html` に遷移する。
6. 宛先情報（First Name, Last Name, Zip）を入力して「Continue」をクリックする。
7. 「Checkout: Overview」画面で画面上の「Item total」と「Tax」を取得する。
8. 取得した値（Item total + Tax）を合計し、画面上の「Total」と厳密に一致するか検証する。
9. 画面のスクリーンショットを `playwrite-e2e/screenshots/cart-result.png` に保存する。

## 5. 期待される結果
- 各画面遷移が正常に行われること。
- 金額検証において `Item total ($29.99) + Tax ($2.40) = Total ($32.39)` が厳密に成立し、検証がパスすること。
- スクリーンショットが正常に保存されること。
