# イラストでわかるDockerとKubernetes Software Design plus 

## 1. コンテナ技術の概要

### 1-1. コンテナを見てみよう

コンテナ技術とは1つの共有されたOS上で複数の独立したアプリケーション実行環境を作成する技術

### 1-2. コンテナ技術の基本的な特徴

1. 軽量な実行環境
2. 高いポータビリティ
3. エコシステム

#### 1-2-1. 軽量な実行環境

##### 仮想マシン

ハイパーバイザ型の完全仮想化技術

ハードウェアとOSの間にハイパーバイザという管理層を挟み，仮想的なハードウェア上で複数のOSを同時に動作させる

#### コンテナ技術

コンテナの中は仮想マシンのように隔離されたOS環境が作成される

ホストOSのカーネル上で環境を作りだし，アプリケーションを実行するプロセス

コンテナ自体はOSカーネルを持たない

通常のプロセスとは違い，強く環境が隔離されている

#### 1-2-2. 高いポータビリティ

##### コンテナイメージが軽量かつ再現性が高い

実行するアプリケーションと依存する最低限のコンポーネントだけが含まれるコンテナ
GB単位の容量になる仮想マシンに対して，コンテナイメージは数十から数百MB程度

イメージにコンポーネント全てを詰め込むことで，異なる環境であっても再現性が高い

基本的な操作方法にコンセンサス(合意)が取れている

Dockerはコンテナの実行に限らず，コンテナにまつわるワークフローを包括的に管理できるツール

ワークフローは"Build, Ship, Run"いったフレーズに表される
* Build: コンテナイメージの作成
* Ship: コンテナイメージの共有
* Run: イメージを元にしたコンテナの実行

オープンな組織によってコンテナイメージ，コンテナレジストリ，コンテナランタイムそれぞれに標準仕様が定められている

#### 1-2-3. 巨大なエコシステム

