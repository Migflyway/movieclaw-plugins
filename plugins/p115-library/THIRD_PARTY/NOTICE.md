# Third-party notices

`p115_rsa.py` is an adapted RSA-only subset of p115cipher 0.0.6, copyright ChenyangGao (https://chenyanggao.github.io). Its source header declares GPLv3 and its included LICENSE is GPLv3. This distribution follows GPL-3.0-or-later. The wheel metadata's MIT label conflicts with the included source/license; the GPL license is preserved here rather than relying on that metadata label.

Changes: extracted RSA constants and functions only; replaced filewrap's byte-view helper with built-in memoryview; added deferred annotations. No AES, LZ4, executable tools, binary extension or p115client dependency is included. The complete modified source is supplied in this package; LICENSE is at package root.

115 wire contracts were checked against p115client 0.0.9.7.2 client.py and MoviePilot p115disk's use of that version. MoviePilot modules are not imported and have not been copied wholesale. STRM integration follows MovieClaw v0.35.0's cloud_strm example using host operations, files and signed routes.

Sources:
- https://pypi.org/project/p115cipher/0.0.6/
- https://pypi.org/project/p115client/0.0.9.7.2/
- https://github.com/DDSRem-Dev/MoviePilot-Plugins/tree/main/plugins.v3/p115disk
- https://github.com/DDSRem-Dev/MoviePilot-Plugins/tree/main/docs/p115strmhelper
- https://github.com/movieclaw/MovieClaw/blob/v0.35.0/src/movieclaw_agent/builtin-skills/movieclaw-plugin-dev/references/examples/cloud_strm.py

## 1.1.0 新增

p115_aes.py（AES）与 p115_ecdh.py（ECDH 响应信封子集：固定密钥 AES-CBC + 带边界检查的 LZ4）来自 p115cipher 0.0.6（ChenyangGao，GPL-3.0-or-later）；提取纯 Python 实现、替换依赖并增加 LZ4 边界检查，上传专用部分已随 2.0.0 移除上传功能一并删除。原许可证见 p115cipher-LICENSE_zh。
p115_m115.py 不来自 p115cipher，是 SheltonZhu/115driver pkg/crypto/m115 的逐行移植（GPL-3.0-or-later）。
扫码登录二维码由主程序（MovieClaw）自带的 `qrcode` 库生成，插件不再内置该库。
上传 wire contract 参考 p115oss 0.1.2（https://pypi.org/project/p115oss/0.1.2/）；插件异步上传和队列实现独立编写。
