---
icon: TiHelp
---

#Tutorial/LaTeX 

# 图片相关
# 表格相关
- 三线表
```latex

```
# 公式相关
- 下限多行
$$
\mathop{\max}_{\mathcal V^k\subset \mathcal V \atop \boldsymbol v\in \mathcal V^k}
$$

# latexdiff 相关
`latexdiff`主要用来编译生成审稿后带有标记的修订版本，主要命令如下：
```shell
latexdiff [option] old.tex new.tex > diff.tex
```
常用的`option`包括：
1. `--math-markup = 1,2,3,4`；控制公式标记格式，主要用来公式编译错误时调整公式标记格式。
2. `--flatten`：所有文件编译到一个文件中(不推荐使用)。

## 使用流程
1. 采用 `latexdiff` 命令编译所有 `.tex` 文件分别生成相应的 `diff.tex` 文件；
2. 采用 `latexdiff` 命令编译 `.bbl` 文件分别生成相应的 `diff.bbl` 文件；
3. 修改 `main_diff.tex` 文件，将 `\include` 的文件换成相应的 `diff.tex` 文件；
4. 将 `diff.bbl` 文件的内容替换 `main_diff.tex` 中的 `\bibliography`。

