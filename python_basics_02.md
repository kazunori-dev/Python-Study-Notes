# Python学習ノート
## 第1回 WAV → MP3変換プログラム

## 目的

Pythonを学びながら、WAVファイルをMP3へ変換するプログラムを作成する。

---

# 作成したプログラム

```python
from pydub import AudioSegment

sound = AudioSegment.from_wav("test.wav")

sound.export("test.mp3", format="mp3")

print("変換がおわりました！")
```

---

# 学んだこと

## ライブラリ

```python
from pydub import AudioSegment
```

- `pydub` はライブラリ
- `AudioSegment` はクラス
- `from ～ import ～` を使って機能を利用できるようにする

---

## オブジェクト

```python
sound = AudioSegment.from_wav("test.wav")
```

- WAVファイルを開く
- `AudioSegment` オブジェクトが作成される
- そのオブジェクトを `sound` という変数へ保存する

---

## メソッド

```python
sound.export("test.mp3", format="mp3")
```

- `sound` が持っている `export()` メソッドを実行する
- MP3形式で保存する

---

## print()

```python
print("変換がおわりました！")
```

画面へメッセージを表示する。

---

# VS Code

## コード補完

- Tabキーで候補を確定できる
- `AudioSegment.` を入力するとメソッド候補が表示される
- コードを書くスピードが向上する

---

# Python環境

最初は Python 3.14 を使用した。

しかし、

```
ModuleNotFoundError
```

が発生。

原因は、使用していた `pydub` が Python 3.14 で正常に動作しなかったため。

Python 3.13でも同様の問題が発生したため、最終的に **Python 3.12** を使用した。

実行コマンド

```powershell
py -3.12 wav2mp3.py
```

---

# pydub

インストール

```powershell
py -3.12 -m pip install pydub
```

---

# FFmpeg

MP3へ変換するためには FFmpeg が必要。

インストール後

```powershell
ffmpeg -version
```

で確認できる。

---

# Git

Gitをインストール。

VS Codeで

```
Initialize Repository
```

を実行し、Git管理を開始した。

---

# Git設定

最初に一度だけ設定する。

```powershell
git config --global user.name "kazunori-dev"
git config --global user.email "メールアドレス"
```

設定確認

```powershell
git config --global --list
```

---

# .gitignore

```text
*.wav
*.mp3
.vscode/
*.code-workspace
```

不要なファイルをGitHubへ公開しないために使用する。

---

# GitHub

公開したファイル

- wav2mp3.py
- README.md
- .gitignore

コミットメッセージ

```text
Create first WAV to MP3 converter
```

---

# 今日学んだこと

- コピペせず、自分で入力すると理解が深まる。
- エラーは失敗ではなく、原因を教えてくれるメッセージ。
- プログラムを書くことだけでなく、環境構築も重要である。
- Gitは変更履歴を管理する仕組みである。
- GitHubはプログラムを保存し、成長の記録を残す場所でもある。

---

# 今後の目標

- ファイル名を自由に指定できるようにする。
- ドラッグ＆ドロップで変換できるようにする。
- フォルダ内のWAVファイルを一括変換する。
- GUI（画面付きアプリ）へ発展させる。

---

# 成果

🎉 **自分でコードを入力し、理解しながらPythonで初めて実用的なプログラムを完成させ、GitHubへ公開することができた。**
