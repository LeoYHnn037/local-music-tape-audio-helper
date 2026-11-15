# 本地音乐助手 / Local Music Tape Audio Helper

作者：Naushica

《深空当铺：可能是偷的》“未定义”本地音频模组的独立 Windows x64 解码助手。用于按需读取 FLAC、M4A（AAC、ALAC）、DSF，生成游戏可以播放的 WAV 缓存。MP3、OGG、WAV 使用游戏原有解码流程。

## 下载与启动

在本仓库 Releases 页面下载 LocalMusicTape-AudioHelper-0.4.0-win-x64.zip，解压到普通文件夹，双击“启动本地音乐助手.cmd”。保持窗口打开，再进入游戏选择音乐目录并播放。

首次启动会从 PyPI 下载约 39 MB 的解码器，并验证固定 SHA256。完成后可离线使用。随包包含 .NET 运行环境，用户可直接运行。完整步骤和第三方组件说明见 ZIP 中 README.md。

退出时可关闭助手窗口，或双击“关闭本地音乐助手.cmd”。

## 处理范围

助手按游戏保存的配置读取当前音乐目录。音频处理在本机完成，接口仅绑定 127.0.0.1，使用每次启动生成的随机口令。源音乐内容只读，缓存为 48 kHz、双声道、16 位 WAV，按最近使用顺序保留约 2 GiB，加上当前生成的一首。

缓存位于当前 Windows 用户的游戏存档目录 ModData/local_music_tape/audio-cache。助手与游戏退出后可删除缓存，下次播放重新生成。目录链接暂不支持。

## 免责声明与第三方组件

本助手为 Naushica 制作的玩家工具，与游戏开发商及音乐版权方无隶属关系。本仓库及发布包不附带音乐；请使用拥有合法使用权限的本地音频。软件按当前发布状态提供，可能存在编码或游戏版本兼容问题，使用前建议备份游戏存档。

FFmpeg 由启动脚本在用户本机从 imageio-ffmpeg 0.8.1 Windows wheel 下载；分发 ZIP 包含下载脚本，未内置 FFmpeg。FFmpeg 使用 GPL v3 或更新版本，imageio-ffmpeg 使用 BSD-2-Clause；下载脚本会保存 imageio-ffmpeg 许可证。包内包含 .NET 许可证与第三方声明。

- [FFmpeg 项目](https://ffmpeg.org/)
- [imageio-ffmpeg 0.8.1](https://pypi.org/project/imageio-ffmpeg/0.8.1/)