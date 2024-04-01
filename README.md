# libcrypto
GNU Emacs30.0.50に含まれる`java/INSTALL`にしたがってパッチを適用したlibcryptoモジュールのレポジトリ。

# 作成した手順
1. [Google Gitのboringssl](https://android.googlesource.com/platform/external/boringssl)をclone

```bash
$: git clone https://android.googlesource.com/platform/external/boringssl
```

2. `nougat-release`ブランチから修正用ブランチ`my/nougat-release`をcheckout

```bash
$: cd boringssl
$: git checkout nougat-release
$: git checkout -b my/nougat-release
```

3. `java/INSTALL`にしたがいpatchを適用

```bash
$: patch -p1 < PATCH_FOR_BORINGSSL.patch
```

4. 上記patch ファイルとpatch適用後ファイルをcommitしてgithubに準備した空レポジトリにpush

```bash
$: git add -A
$: git commit -m 'nanika commit messages...'
$: git remote add mine https://github.com/JIBUN/my-boringssl.git
$: git branch -M my/nougat-release
$: git push -u mine my/nougat-release
```
