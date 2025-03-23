---
title: "ModuleNotFoundError: No module named 'cgi'"
emoji: "🐍"
type: "tech" # tech: 技術記事 / idea: アイデア
topics: ["python", "python3"]
published: true
---

Python のバージョンを 3.12 から 3.13 にあげたところ、以下のエラーが出た。

```
ModuleNotFoundError: No module named 'cgi'
```

これは、v3.13 で、モジュールの `cgi` が標準サポートされなくなったことが原因。

https://docs.python.org/3/library/cgi.html

> cgi — Common Gateway Interface support
> Deprecated since version 3.11, removed in version 3.13.

対応方法としては、cgi を使っているコードを `html` モジュールなどに書き換える方法が推奨されるが、それが難しい場合は、[`legacy-cgi`](https://pypi.org/project/legacy-cgi/) を代替モジュールとして使う方法がある。


legacy-cgi インストール方法
```
$ pip install legacy-cgi
```


今すぐ v3.13にバージョンアップしなければならない場合や、刷新が決まっているシステムの古いコードのような場合は、`legacy-cgi
` を使う方法も検討してみる。
