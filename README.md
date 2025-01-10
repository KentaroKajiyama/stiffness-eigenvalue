## 各ファイルについて

### .env
ここにグラフや繰り返し回数など各パラメータを書いています。

### framework.py
ほとんど rigidpy の frameworkライブラリそのものです。計算を軽くするためにデフォルトで scipy の csr 形式の疎行列を使って framework を作るようにしています。

### optimize_eigenvalue.py
ここで固有値の最適化をしています。
max_p_eigenvalue_lib 関数で 埋め込み p を MAX_ITER_FOR_EIGENVALUE 回更新しています。
armijo 関数で埋め込み p を armijo 条件を使って上昇方向に更新しています。
ascent_dir 関数で stiffness matrix L(p) の上昇方向を計算しています。

### test.py
この関数を実行して実験をします。グラフなどを初期化したのち、最適化計算関数を呼び出して、最後に結果を描画します。

### visualize.py
結果を描画するための関数です。

### pyproject.toml, poetry.lock
poetry という python の仮想環境管理ツールを使っており、その設定ファイルとロックファイルです。ライブラリやインタープリターの依存関係はここにすべて書かれています。

## poetry を使って実行する場合
- poetry を install します。
- このディレクトリのルートディレクトリで poetry install を実行してライブラリをインストールします。
- poetry run python test_max_eigenvalue.py で実験を開始できます。

pip などを使って実行することも可能です。pyproject.toml に書かれたライブラリをインストールして python test_max_eigenvalue.py を実行します。
