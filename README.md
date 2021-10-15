# push_swap_tester

## 機能

1. push_swapのテスト
   - `push_swap` を実行し、`checker` を使って出力を確認します。
     - オプションで、引数の個数、数値の範囲、テスト回数、push_swapのディレクトリを指定できます。
2. テスト用の引数生成
   - テスト用の引数を生成し、標準出力に出力します。

## 使い方

Python 3.8.2で動作を確認しています。

push_swapのプロジェクト内にリポジトリをcloneします。
```bash
git clone https://github.com/nafuka11/push_swap_tester.git
```

### ヘルプ

```bash
python3 push_swap_tester.py -h
```

### テストの実行

```bash
python3 push_swap_tester.py
```

- 引数5個の順列を作成してテストします。
  - 順列の個数がデフォルトのテスト回数を下回る場合、順列を生成します。
- checkerでOK/KOを判定します。OKなら緑色の `.` を、KOなら赤色の `F` を標準出力します。
- push_swap命令数の最大値、中央値、最大値を標準出力します。
- `result.log` に詳細な情報を出力します。

オプションで、引数の個数、数値の範囲、テスト回数、push_swapのディレクトリを指定できます。

|オプション|内容|デフォルト値|
|--|--|--|
|-l <個数>|push_swapに渡す引数の個数を指定します|5|
|-c <回数>|テストする回数を指定します|200|
|-r <最小値, 最大値>|push_swapに渡す引数の範囲を指定します|1, `-l`の値|
|-d <ディレクトリ>|push_swapのディレクトリを指定します|`..`|
|-g, --gen|指定すると、テストをする代わりに引数を生成して出力します|無効|

#### 例

引数100個のテストを500回実行

```bash
python3 push_swap_tester.py -l 100 -c 500
```

出力

```bash
Test 500 cases: arg_length=100 range=(1, 100)
....................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................
---- Result ----
max   : 688
median: 644
min   : 595
See result.log for details
```

### テスト用の引数生成

```bash
python3 push_swap_tester.py --gen
```
オプションで、引数の個数、数値の範囲を指定できます。

#### 例
INT_MINからINT_MAXの範囲で10個の引数を生成
```bash
python3 push_swap_tester.py --gen -r -2147483648 2147483647 -l 10
```
出力
```bash
-1110677087 -738511178 1555694097 1972999663 989665463 -2116604533 819005173 -895360136 -613437200 1767332339
```
