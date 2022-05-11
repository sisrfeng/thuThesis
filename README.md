FAQ重点:
    在 Windows 字体的环境中编译，并且在 \documenclass 中指定 fontset=windows。


# ThuThesis


下载途径：

* 发布版：
  * [GitHub Releases](https://github.com/tuna/thuthesis/releases)：最新版的及时发布途径。


## 更新日志

每个版本的详细更新日志，请见 [CHANGELOG.md](CHANGELOG.md)。使用文档中也包含了这一内容。

## 升级

手动更新

#### 发布版

下载发布版的的 zip 包，使用其中的 `thuthesis.cls` 等文件覆盖原有的即可，无须额外操作。

#### 开发版

从 GitHub clone 项目源码或者下载源码 zip 包，执行命令（Windows 用户在文件夹空白处按 `Shift + 鼠标右键`，点击“在此处打开命令行窗口”）：
```shell
xetex thuthesis.ins
```
即可得到 `thuthesis.cls` 等模板文件。

## 提问
按推荐顺序排序：

* 先到 [FAQ](https://github.com/tuna/thuthesis/wiki/FAQ) 看看常见问题
* [GitHub Issues](https://github.com/tuna/thuthesis/issues)

## Makefile的用法
```shell
make [{all|thesis|spine|doc|clean|cleanall|distclean}]
```

### 目标
* `make thesis`    生成论文 thuthesis-example.pdf；
* `make spine`     生成书脊 spine.pdf；
* `make doc`       生成模板使用说明书 thuthesis.pdf；
* `make all`       生成论文和书脊，相当于 `make thesis && make spine`；

* `make clean`     删除示例文件的中间文件（不含 thuthesis-example.pdf）；
* `make cleanall`  删除示例文件的中间文件和 thuthesis-example.pdf；
* `make distclean` 删除示例文件和模板的所有中间文件和 PDF。

