---
icon: TiHelp
---

#Tutorial/VSCode

# settings.json

`settings.json`为`VS Code`的配置文件，下面为几项基本常用配置：
```json
{
// Default settings can be found from https://vscode-docs.readthedocs.io/en/stable/customization/userandworkspace/

//-------- Editor configuration --------

    // Controls the font family.
    // "editor.fontFamily": "Menlo, Monaco, 'Courier New', monospace",
    "editor.fontFamily": "Menlo",

    // Controls the font size.
    "editor.fontSize": 16,

    // Controls the rendering size of tabs in characters. Accepted values: "auto", 2, 4, 6, etc. If set to "auto", the value will be guessed when a file is opened.
    "editor.tabSize": 4,

    // Controls visibility of line numbers: "off", "on", "relative", "interval".
    "editor.lineNumbers": "relative",

    // Controls if the editor will insert spaces for tabs. Accepted values:  "auto", true, false. If set to "auto", the value will be guessed when a file is opened.
    "editor.insertSpaces": true,

    "editor.wordWrap": "on",

//-------- Files configuration --------
    "files.autoSave": "onFocusChange",
    
//-------- Git configuration --------
    "git.autofetch": true,
    "git.confirmSync": false,
    "git.enableSmartCommit": true,

    // Control whether a repository in parent folders of workspaces or open files should be opened.
    "git.openRepositoryInParentFolders": "never",

    // Contorls whether to automatically detect git submodules.
    "git.detectSubmodules": false,
}
```
# 常用插件
- Git Graph
- Remote Explorer
- LaTeX Workshop
- LTeX
- Markdown All in One
- Vim
- vscode-gmsh
- Data Preview
- Todo Tree
# Remote Explorer
1. 配置ssh config
`Connect to Host...->Configure SSH Hosts...->/Users/username/.ssh/config`
```
Host hostname
	HostName server_ip
	User username
```
2. 将ssh公钥添加到远程服务器
```
ssh-copy-id user_name@server_ip
```
# LaTeX Workshop
- [Texlive安装](https://mirrors.tuna.tsinghua.edu.cn/CTAN/systems/texlive/Images/ )
- 安装并配置LaTeX Workshop：
```json
{
//-------- LaTeX Workshop configuration --------
    "latex-workshop.latex.recipes": [
        {
            "name": "latexmk (xelatex)",
            "tools": [
                "xelatexmk"
            ]
        },
    ],
}
```
