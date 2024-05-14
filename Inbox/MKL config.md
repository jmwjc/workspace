---
icon: TiHelp
---

#Tutorial/Program #Group/徐洋涛  

# Windows
1. [下载Intel® oneAPI Base Toolkit](https://www.intel.com/content/www/us/en/developer/tools/oneapi/base-toolkit-download.html) 
	选择对应的系统下载安装；

2. [配置环境变量](https://www.intel.com/content/www/us/en/docs/onemkl/developer-guide-windows/2023-0/setting-environment-variables.html) 
	在安装路径Intel\oneAPL中以管理员身份运行setvars
	查看环境变量：右击此电脑$\rightarrow$属性$\rightarrow$高级系统设置$\rightarrow$环境变量

3. Julia安装Paradiso
	pkg>build Pardiso

4. 测试安装是否成功
	Julia 输入
```julia
using Pardiso
ps = MKLPardisoSolver()
```

输出：
```terminal
KLPardisoSolver:
    Matrix type: Real nonsymmetric
    Phase: Analysis, numerical factorization, solve, iterative refinement
```
即安装成功

# Linux server
1. [下载Intel® oneAPI Base Toolkit](https://www.intel.com/content/www/us/en/developer/tools/oneapi/base-toolkit-download.html) 
	选择对应的系统下载安装；
2. [配置环境变量](https://www.intel.com/content/www/us/en/docs/oneapi-base-toolkit/get-started-guide-linux/2023-0/before-you-begin.html) 
	在`~/.bashrc`中加入
```
. /opt/intel/oneapi/setvars.sh
```