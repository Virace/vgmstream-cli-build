# vgmstream-cli-build

[![GitHub release](https://img.shields.io/github/v/release/Virace/vgmstream-cli-build?display_name=tag&logo=github)](https://github.com/Virace/vgmstream-cli-build/releases/latest)

这是一个用于编译魔改版 `vgmstream-cli` 的项目。

您可以从上面的徽章或 [这里](https://github.com/Virace/vgmstream-cli-build/releases/latest) 下载最新编译的版本。

## 修改内容

1.  **为输出路径添加通配符**:
    *   `?p`: 代表源文件的完整路径 (包含最后的路径分隔符)。
    *   `?b`: 代表源文件的基础名称 (不含扩展名)。
2.  **支持目录输入**: 允许将文件夹作为输入，程序会自动递归扫描并转码其中所有的 `.wem` 文件。
3.  **增加 `-Y` 选项**: 在转码成功后删除源文件。**这是一个危险操作，请务必谨慎使用！**

## 使用示例

以下是使用新增功能的一个实例：

```bash
.\vgmstream-cli.exe -o "?p?b.wav" "E:\audios\Champions\2·olaf·狂战士\2000·基础皮肤" -Y
```

这个命令的含义：
- 将 `E:\audios\Champions\2·olaf·狂战士\2000·基础皮肤` 目录中的所有音频文件（包括子目录）转换为 WAV 格式
- 输出文件使用 `?p?b.wav` 模式命名，即保持原始文件的路径和文件名，仅将扩展名改为 `.wav`
- `-Y` 参数表示转换完成后删除原始文件

例如，对于输入文件 `E:\audios\Champions\2·olaf·狂战士\2000·基础皮肤\11111111.wem`，输出文件将是 `E:\audios\Champions\2·olaf·狂战士\2000·基础皮肤\11111111.wav`。

## 手动构建

由于上游代码和依赖可能存在不确定性，本项目的构建流程设置为手动触发。

1.  访问本仓库的 [Actions](https://github.com/Virace/vgmstream-cli-build/actions) 页面。
2.  在左侧选择 "Build and Release vgmstream-cli" 工作流。
3.  点击 "Run workflow" 按钮，即可开始构建和发布流程。

## 致谢

*   **灵感来源**: [@DoTheBetter/aria2_build](https://github.com/DoTheBetter/aria2_build)
*   **上游项目**: [@vgmstream/vgmstream](https://github.com/vgmstream/vgmstream)
