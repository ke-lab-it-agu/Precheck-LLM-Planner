# 家庭環境知識に基づく行動前提条件の検証を伴う<br>LLMエージェントの逐次的行動計画生成

## 環境構築

### Jupyter Notebook
ソースコードの実行にはJupyter Notebookを使用します。JupyterはPythonのパッケージとして提供されているため、Jupyter Notebookを使用するには[Python](https://www.python.org/)がインストールされている必要があります。

※Jupyter Notebookの詳しいインストール方法や使い方は[公式サイト](https://jupyter.org/)を参照してください。

### VirtualHome
- [VirtualHome](http://virtual-home.org/)シミュレータを用いるため、セットアップする必要があります。VirtualHomeの[GitHubリポジトリ](https://github.com/xavierpuigf/virtualhome)を参照してセットアップし、VirtualHomeが正しく動作することを確認してください。<br>※バージョン2.3をインストールすることに注意

- VirtualHomeの動作確認後、このプロジェクトフォルダを、virtualhomeディレクトリの直下（simulationフォルダと同じ階層）に置く。

## ソースコード実行方法
- single-prompt.ipynb または multi-prompt.ipynb が実行ファイルです。
- single-prompt.ipynbはプロンプトを単一でLLMに提供する方法、multi-prompt.ipynbはプロンプトを分割してLLMに提供する方法で実装している。

以下が実行方法の手順

1. VirtualHomeを起動（virtualhome/simulation/unity_simulator/VirtualHome.exe を実行（Windowsの場合））
2. 実行ファイル（single-prompt.ipynb または multi-prompt.ipynb）を開く。
3. 実行には、[OpenAI](https://openai.com/)のAPIが必要であるため、該当箇所に有効なAPIキーを記載する。また、使用するモデルの指定も行う。
4. 実験タスク（状態変化または配置）の選択を行う。
5. 実行ファイルのセルを上から順に実行する。実行ファイル中のDemoのマークダウン以下でデモの実行、評価実験のマークダウン以下で再現実験を行うことができる。

実験の結果は、json形式のファイルで保存され、cal_score.ipynb で結果のファイルを読み込んで最終的なスコアを算出する

### 補足
- result以下は実験結果であり、タスクタイプ毎に結果ファイルを保存している。
- ablation以下はアブレーションスタディの結果である。
- 各jsonファイル名に、プロンプティング手法と利用したモデルが記載されている。