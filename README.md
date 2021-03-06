# 同文安卓輸入法平臺/Trime/android-rime
[![自動編譯](https://travis-ci.org/nlpguyz/trime.svg?branch=develop)](https://travis-ci.org/nlpguyz/trime)
[![License: GPL v3](https://img.shields.io/badge/License-GPL%20v3-blue.svg)](http://www.gnu.org/licenses/gpl-3.0)
[![GitHub release](https://img.shields.io/github/release/osfans/trime.svg)](https://github.com/osfans/trime/releases)

[<img alt='Google Play立即下載' src='https://play.google.com/intl/en_us/badges/images/generic/zh-tw_badge_web_generic.png' height='80px'/>](https://play.google.com/store/apps/details?id=com.osfans.trime)
[<img alt='酷安' src='http://image.coolapk.com/apk_logo/2016/0108/12202_1452248424_4592.png' height='80px'/>](http://www.coolapk.com/apk/com.osfans.trime)

本輸入法享有優秀前端㞢源於開源[注音倉頡輸入法]啫，以及輸入法引擎㞢基於著名的[Rime]框架。JNI部分使用C/C++語言，安卓應用程序部分使用Java語言編寫。
旨在保護漢語各地的方言和母語，輸入法平臺通用于音碼和形碼。

## 維護者/Maintainers
- 本版本維護者：nlpguyz (nlpguyz@gmail.com）
- 主要聯繫方式：語言維基QQ群（562374735)

## 鳴謝/Credits
- 開發：[osfans](https://github.com/osfans)
- 貢獻：[boboIqiqi](https://github.com/boboIqiqi)、[Bambooin](https://github.com/Bambooin)
- [維基](https://github.com/osfans/trime/wiki)：[xiaoqun2016](https://github.com/xiaoqun2016)、[boboIqiqi](https://github.com/boboIqiqi)
- 翻譯：天真可愛的滿滿（繁體中文）、點解（英文）
- 鍵盤：天真可愛的滿滿、皛筱晓小笨鱼、吴琛11、熊貓阿Bo、默默ㄇㄛˋ
- 捐贈：[Releases](https://github.com/osfans/trime/releases)中的“打賞”實時更新
- 社區：在[Issues](https://github.com/osfans/trime/issues)、[QQ羣480159874](http://shang.qq.com/wpa/qunwpa?idkey=e31ecec8f92699597d9154f890841b3e477f5185902f10400e7c9e670a11202f)、[酷安](http://www.coolapk.com/apk/com.osfans.trime)、[Google Play](https://play.google.com/store/apps/details?id=com.osfans.trime)、[貼吧](http://tieba.baidu.com/f?kw=rime)中反饋意見的網友
- 項目：[Rime]、[OpenCC]、[注音倉頡輸入法]等開源項目

## 沿革/History
- 最初，輸入法是寫給[泰如拼音](http://taerv.nguyoeh.com/zidian/)（tae5 rv2）的，中文名爲“泰如輸入法”。
- 然後，添加了吳語等方言碼表，做成了一個輸入法平臺，更名爲“漢字方言輸入法”。
- 後來，兼容了五筆、兩筆等形碼，在太空衛士、徵羽的建議下，更名爲“[同文輸入法平臺2.x](https://github.com/osfans/trime-legacy)”。寓意音碼形碼同臺，方言官話同文。
- 之後，藉助JNI技術，享受了[librime](https://github.com/rime/librime)的成果，升級爲“同文輸入法平臺3.x”，簡稱“同文輸入法”。
- 所以，TRIME是Tongwen RIME或是ThaeRvInputMEthod的縮寫。
- 現在，為了進一步促進TRIME的發展，包括採用人工智能技術，甄選、引入更多用戶喜愛的輸入方案等，語言維基網站 (https://langwiki.org) 主導和維護此新版本。

## 新增輸入方案/Submit a new input schema
- 歡迎大家參與開發本輸入法，提交新的輸入方案（如吳語拼音、小語種字母輸入等）
- 管理員會每月考慮新提交的輸入法，將完善的方案加到安裝文件中。加入後，本軟件用戶只要安裝便可使用您提交的輸入方案，無須額外操作。
- 新的輸入法文件可以用git提交到 https://github.com/nlpguyz/trime/tree/develop/contrib 目錄下。也可以在github網頁上直接上載。

## 編譯/Build

  Clone the project, **pay attention** it will take a while for large submodule boost and make sure your disk is enough to hold the source(about 1.5GB).
```bash
cd $your_folder
git clone --recursive https://github.com/osfans/trime.git trime
```
  If you want to test the application, run the command:
```bash
cd $trime_folder
make debug
```
  Or you can build signed application for release and make sure you create a file named gradle.properties which contains:
```bash
storePassword=myStorePassword
keyPassword=mykeyPassword
keyAlias=myKeyAlias
storeFile=myStoreFileLocation
```
for [signing information](https://developer.android.com/studio/publish/app-signing.html). And run the command:
```bash
cd $trime_folder
make release
```
The following guide is for the specific platform prebuild setting:
- [Arch Linux](https://www.archlinux.org/)
  ```bash
   yaourt -S android-{ndk,sdk,sdk-build-tools,sdk-platform-tools,platform} gradle
   make release
  ```

- Other Linux distributions

  Use the package manager to install the dev environment and Android SDK NDK.

- macOS

  Install Android [SDK](https://developer.android.com/studio/index.html)
  and [NDK](https://developer.android.com/ndk/index.html)
  (You'd better install it by Android Studio or manually instead of by Homebrew).

  Install [Homebrew](http://brew.sh/) and set
  [Homebrew mirror](https://lug.ustc.edu.cn/wiki/mirrors/help/brew.git) of it if your network is slow.

  ```bash
   brew install automake cmake opencc boost python gradle doxygen
  ```

  Set the path environment in ~/.bashrc if you use bash like this
  ```bash
   # Android
   export ANDROID_HOME="your_android_sdk"
   export ANDROID_NDK="your_android_ndk"
   export PATH=${PATH}:$ANDROID_HOME/tools:$ANDROID_HOME/platform-tools:$ANDROID_NDK
  ```
## 第三方庫/3rd Party Library
- [minilog](http://ceres-solver.org/) (New BSD License)
- [OpenCC](https://github.com/BYVoid/OpenCC) (Apache License 2.0)
- [RIME](http://rime.im) (BSD License)
 - [Boost C++ Libraries](http://www.boost.org/) (Boost Software License)
   - [libiconv](http://www.gnu.org/software/libiconv/) (LGPL License)
 - [darts-clone](https://code.google.com/p/darts-clone/) (New BSD License)
 - [marisa-trie](https://code.google.com/p/marisa-trie/) (BSD License)
 - [UTF8-CPP](http://utfcpp.sourceforge.net/) (Boost Software License)
 - [yaml-cpp](https://code.google.com/p/yaml-cpp/) (MIT License)
 - [LevelDB](https://github.com/google/leveldb) (New BSD License)
   - [snappy](https://google.github.io/snappy/)(BSD License)
 
[注音倉頡輸入法]: https://code.google.com/p/android-traditional-chinese-ime/
[Rime]: http://rime.im
[OpenCC]: https://github.com/BYVoid/OpenCC

【注】本文使用实验性的新汉语定语语法，长定语置于中心词之后，用“㞢“引导，以“啫”结束。如，”美丽而又伟大的祖国“可以表达为”祖国㞢美丽而又伟大啫“。
