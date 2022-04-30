# 用 ansible 部署 django 项目
用 ansible 在 ubuntu server 20.04 LTS 部署Django 项目 

## 准备
1. 源代码要求
    > 1. `static` 目录在 [项目根目录](https://docs.djangoproject.com/zh-hans/4.0/ref/settings/#std:setting-STATICFILES_DIRS) 
    > 2. `requirements.txt` 在源代码根目录
2. 上传源代码到 `github` 并获取 链接
3. 配置部署服务器免密码等入 `ssh-copy-id  name@server`
4. 安装 `ansible` 

## 配置安装变量
1. 修改 `hosts`， 添加部署服务器
    > `cp hosts.example hosts`  
    >   
    > `vim hosts`   
    > > stage ansible_ssh_host=**192.168.31.52.nip.io** ansible_ssh_port=22 ansible_ssh_user=jingwang
    >
    >  **ansible_ssh_host** 用于 nginx **server_name**
2. 设置 `project_name` 和 `repo_url`
    > `vim  vars/custom.yml`
    > 
    > > project_name: '**super_lists**'  
 name
    > > repo_url: '**https://github.com/jingwangnet/2022-super-list.git**'

## 安装
`ansible-play deployment.yml`

