---
title: URL Schemes
date: 2021-08-13 11:25
---
> 注意事项:
> 1. 后续中出现的**work_folder_name**是指工作目录的名称(不支持外部挂载的目录)。
> 2. URL 中传递的值，最好都经过 URL 编码，特别比如 text 这个参数。

## 创建新文档
metion://file?action=new&root=work_folder_name&path=filename.md&text=text

## 创建新文档并自动下载图片到本地
metion://file?action=new&root=work_folder_name&path=filename.md&text=text&download_images=true
创建新文档之后，会自动尝试下载内部的图片到本地，但因为防盗链等原因，可能不会成功，另外在文档内容的头部 Metadata 中声明 source (也就是来源 URL) 会提高图片下载的成功率。

## 添加内容到文档
metion://file?action=append&root=work_folder_name&path=filename.md&text=text

## 在编辑器中打开文档
metion://editor?action=open&root=work_folder_name&path=filename.md

## 动态匹配树状图模式的知识库
metion://knowledge?action=dynamic&root=work_folder_name&text=text
会根据 **text** 传入的内容，动态匹配当前的工作目录

## Git
metion://git?action=pull&root=work_folder_name
metion://git?action=push&root=work_folder_name&text=message_to_commit
