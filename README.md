# julius4seg

English readme: https://github.com/Forrest22/julius4seg/blob/master/README-EN.md

[Julius Japanese Dictation-kit](https://github.com/julius-speech/dictation-kit)を Python から叩いている風にするためのスクリプト．

grammer-kit と segmentation-kit を足して 2 で割ったような立ち位置．

## Usage

### Clone して使う方

see: https://github.com/yamachu/julius4seg/blob/master/sample/README.md

### Docker で使う方

see: https://hub.docker.com/r/yamachu/julius4seg

```sh
$ docker pull yamachu/julius4seg:latest
```

#### segmentation したい方

コマンド例

```sh
$ docker run --rm -v `pwd`/sample:/tmp yamachu/julius4seg sp-segment /tmp/sample_voice.wav /tmp/sample_kana.txt /tmp/seg.txt
```

第一引数に `sp-segment` を入れて、その後に続く引数は[sample](https://github.com/yamachu/julius4seg/blob/master/sample/README.md)の `run_segment.py` と同様

ファイル入力前提で作られているので、ローカルのディレクトリをマウントして、そのファイルを指定するようにして下さい。

#### silence を除去したい方

コマンド例

```sh
$ docker run --rm -v `pwd`/sample:/tmp yamachu/julius4seg sp-remove /tmp/sample_voice.wav /tmp/seg.txt /tmp/out.wav
```

第一引数に `sp-remove` を入れて、その後に続く引数は[sample](https://github.com/yamachu/julius4seg/blob/master/sample/README.md)の `run_remover.py` と同様

## 注意事項

このスクリプトを実行するのに依存している Dictation-kit は git lfs がインストールされていないと音響モデルも一緒にクローンできないため注意．

Julius の標準的なサポートフォーマットである 16kHz, 16bit, mono の音声を対象としている．

macOSX, Python3.6 で動作を確認．
