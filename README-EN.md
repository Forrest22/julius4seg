# julius4seg

Scripts to simulate interacting with [Julius Japanese Dictation-kit](https://github.com/julius-speech/dictation-kit) from Python.

Positioned as a combination of the grammar-kit and segmentation-kit.

## Usage

### For Cloning and Usage

see: https://github.com/forrestd22/julius4seg/blob/master/sample/README-EN.md

### Using Docker

see: https://hub.docker.com/r/yamachu/julius4seg

```sh
docker build .
```

#### For Segmentation

Command example:

```sh
docker run --rm -v `pwd`/sample:/tmp yamachu/julius4seg sp-segment /tmp/sample_voice.wav /tmp/sample_kana.txt /tmp/seg.txt
```

Put `sp-segment` as the first argument, followed by the arguments similar to `run_segment.py` in the [sample](https://github.com/yamachu/julius4seg/blob/master/sample/README.md).

Since it is designed for file input, mount the local directory and specify the file accordingly.

#### For Silence Removal

Command example:

```sh
docker run --rm -v `pwd`/sample:/tmp yamachu/julius4seg sp-remove /tmp/sample_voice.wav /tmp/seg.txt /tmp/out.wav
```

Put `sp-segment` as the first argument, followed by the arguments similar to `run_segment.py` in the [sample](https://github.com/yamachu/julius4seg/blob/master/sample/README.md).

## Notes

Note that the Dictation-kit, which this script depends on, cannot clone the acoustic model together if Git LFS is not installed.

It targets the standard supported format of Julius, which is 16kHz, 16-bit, mono audio.

Tested on macOSX with Python 3.6.
