# homebrew-ffmpeg-with-librsv

[FFmpeg](https://ffmpeg.org/)のインプットとしてSVGを利用可能にするため、[homebrew-core/Formula/f/ffmpeg.rb at master · Homebrew/homebrew-core](https://github.com/Homebrew/homebrew-core/blob/master/Formula/f/ffmpeg.rb)のフォーミュラを手動で修正し、`--enable-librsvg`オプションを追加しました。

本Formulaをビルドし、インストールすることで、SVG対応版の **FFmpeg** が利用可能になります。

## 事前準備

すでに、**FFmpeg** がインストールされている場合には、以下を実行し、あらかじみ削除してください。

```shell
brew uninstall --ignore-dependencies ffmpeg
```

## ビルド方法

[ffmpeg.rb](./ffmpeg.rb) を自環境にダウンロードし、以下を実行することで、SVG対応版の **FFmpeg**をビルドし、インストールすることができます。

```shell
brew install --build-from-source --formula ffmpeg.rb
```

ビルド(ビルドには、時間がかかります。)とインストールが完了したら、以下を実行し、`--enable-librsv`が有効になっているか確認してください。

```shell
$ ffmpeg
ffmpeg version 7.0.1 Copyright (c) 2000-2024 the FFmpeg developers
  built with Apple clang version 15.0.0 (clang-1500.3.9.4)
  configuration: --prefix=/usr/local/Cellar/ffmpeg/7.0.1 --enable-shared --enable-pthreads --enable-version3 --cc=clang --host-cflags= --host-ldflags='-Wl,-ld_classic' --enable-ffplay --enable-gnutls --enable-gpl --enable-libaom --enable-libaribb24 --enable-libbluray --enable-libdav1d --enable-libharfbuzz --enable-libjxl --enable-libmp3lame --enable-libopus --enable-librav1e --enable-librist --enable-librubberband --enable-libsnappy --enable-libsrt --enable-libssh --enable-libsvtav1 --enable-libtesseract --enable-libtheora --enable-libvidstab --enable-libvmaf --enable-libvorbis --enable-libvpx --enable-libwebp --enable-libx264 --enable-libx265 --enable-libxml2 --enable-libxvid --enable-lzma --enable-libfontconfig --enable-libfreetype --enable-frei0r --enable-libass --enable-libopencore-amrnb --enable-libopencore-amrwb --enable-libopenjpeg --enable-libspeex --enable-libsoxr --enable-libzmq --enable-libzimg --enable-librsvg --disable-libjack --disable-indev=jack --enable-videotoolbox --enable-audiotoolbox
  libavutil      59.  8.100 / 59.  8.100
  libavcodec     61.  3.100 / 61.  3.100
  libavformat    61.  1.100 / 61.  1.100
  libavdevice    61.  1.100 / 61.  1.100
  libavfilter    10.  1.100 / 10.  1.100
  libswscale      8.  1.100 /  8.  1.100
  libswresample   5.  1.100 /  5.  1.100
  libpostproc    58.  1.100 / 58.  1.100
Universal media converter
usage: ffmpeg [options] [[infile options] -i infile]... {[outfile options] outfile}...

Use -h to get full help or, even better, run 'man ffmpeg'
```
