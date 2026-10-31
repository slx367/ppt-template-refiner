# 发布到 GitHub

只上传本技能包，不上传整个课题项目目录。

## 网页方法

1. 登录 GitHub，点击右上角 `+` → `New repository`。
2. 名称填 `ppt-template-refiner`，选择 Public 或 Private。包内已有 README，可不自动创建。
3. 创建后点击 `uploading an existing file`，或 `Add file` → `Upload files`。
4. 解压安装 ZIP，进入里面的 `ppt-template-refiner` 文件夹，将其中所有文件和子文件夹拖入上传区。仓库根目录应直接看到 `SKILL.md`、`README.md`、`agents/`、`references/`。不要只上传 ZIP。
5. 提交说明填 `Initial release`，点击 `Commit changes`。
6. 要授权他人开源复用时，选择合适许可证并填写真实权利人；本包未替你选定许可证。
7. 可在 `Releases` → `Draft a new release` 创建 `v1.0.0`，填写功能说明并发布。GitHub 会按标签提供源码 ZIP，也可附上安装包。

## 命令行方法

需要 Git 和 GitHub CLI。在独立解压后的技能目录执行，不要在整个课题根目录执行：

```powershell
Set-Location '填写解压路径/ppt-template-refiner'
git init
git add SKILL.md README.md PUBLISH.md agents references
git commit -m "Initial release"
git branch -M main
gh auth login
gh repo create ppt-template-refiner --public --source=. --remote=origin --push
```

私有发布改用 `--private`。已有仓库则不要重复创建，使用 GitHub 提供的远端地址配置并推送。本交付未登录账号或推送仓库。

官方依据：

- [网页上传文件](https://docs.github.com/en/repositories/working-with-files/managing-files/adding-a-file-to-a-repository)
- [本地项目发布](https://docs.github.com/en/migrations/importing-source-code/using-the-command-line-to-import-source-code/adding-locally-hosted-code-to-github)
- [gh repo create](https://cli.github.com/manual/gh_repo_create)
- [Releases](https://docs.github.com/en/repositories/releasing-projects-on-github/about-releases)
