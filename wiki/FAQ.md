### 数学公式的字体为何不是 LaTeX 默认的 Computer Modern？

《写作指南》中要求西文字体使用 Times New Roman，而 Computer Modern 的字形比 Times 要细很多，所以两者并不搭配。其次，《写作指南》还要求数学符号遵守 GB/T 3102.11—1993（虽然在实际中可能要求并不严格），Computer Modern 的字形无法满足该标准，比如正体的 `$\pi$` 和正体的积分号。所以模板中使用了 `unicode-math` 宏包配置数学字体，用户可以选择 [`XITS`](https://ctan.org/pkg/xits)（默认）、[`STIX2`](https://ctan.org/pkg/stix2-otf)。

如果用户实在需要 LaTeX 默认风格的数学符号，可以设置 `math-font = newcm` 选择 [New Computer Modern](https://www.ctan.org/pkg/newcomputermodern)。


### 为何更新了模板后编译出的结果还是旧版的格式？

这是由于只更新了 `.dtx` 文件，没有更新 `.cls` 模板文件，导致编译时调用了旧版的 `.cls`。应该使用 `xetex thuthesis.dtx` 生成新版的 `.cls`。


### 为何编译出的文档中字体跟官方 Word 模板中的不一样？

ThuThesis 为了实现跨平台编译，会自动调用该对应台下的字体，所以与 Word 模板中的 Times New Roman、中易宋体、中易黑体可能不同。建议提交终稿时在 Windows 字体的环境中编译，并且在 `\documenclass` 中指定 `fontset=windows`。


### 参考文献出错之后怎么改都不对了
使用 `make clean` 或 `latexmk -c` 清理掉 `.aux`、`.bbl` 等辅助文件，然后重新编译。


### 为什么我使用 CTeX 2.9.2 套件无法编译？

CTeX 2.9.2 套件发布于 2012 年，ThuThesis 使用了新版本中文宏包 CTeX 2.2，旧版 CTeX 2.9.2 套件已不能支持。

可以运行`cmd`→ 输入`mpm`命令→ 进入 Repository 菜单→ 选择 Change Package Repository → 选择Packages shall be installed from the Internet → 选择一个可用的地址 → 更新`ctex`宏包。

别用CTeX套件, 但CTeX package还是要用?


### CTeX 2.9.2 明明版本号比 CTeX 2.2 要高，为什么是「旧版本」呢？ 
历史原因，目前使用 CTeX 这个名称的有 [CTeX 套件](http://www.ctex.org/HomePage)、[CTeX 宏包](https://www.ctan.org/pkg/ctex)、[CTeX 论坛](http://bbs.ctex.org)。
CTeX 套件是一套完整的 TeX 环境，
CTeX 宏包是各类 TeX 发行版都可以使用的中文支持宏包。
