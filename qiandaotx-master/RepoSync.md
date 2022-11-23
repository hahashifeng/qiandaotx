# 通过reposync方式进行代码同步

## Why

通过下面的方法重新创建分支，同步代码

此方式亲测可行，请放心食用

当然别忘了对源仓库进行*Star* 

## How

### 创建新仓库

[点击创建自己的仓库](https://github.com/new)

填入`Repository name`后点击最下方的`Create repository`即可完成创建
###可选 将默认分支修改为master
如默认分支非`master`可以请自行修改当前分支名称

如不修改自行`切换分支`即可.

![1](https://cdn.jsdelivr.net/gh/BlueskyClouds/Script/img/2021/05/20/img/1.png)
![2](https://cdn.jsdelivr.net/gh/BlueskyClouds/Script/img/2021/05/20/img/2.png)
![3](https://cdn.jsdelivr.net/gh/BlueskyClouds/Script/img/2021/05/20/img/3.png)



### 自己创建工作流

在创建完成页面点击`Actions`再点击`set up a workflow yourself`

<img src="icon/set_up_workflow.png" alt="set_up_workflow" style="zoom:75%;" />

复制https://github.com/MayoBlueSky/My-Actions/blob/master/.github/workflows/repo_sync.yml 里面的代码

复制完毕后直接点击右上角的`Start commit`后直接`Commit new file`即可

<img src="icon/create_new_sync_yaml.png" alt="create_new_sync_yaml" style="zoom: 67%;" />

### 申请PAT

点击 GitHub [用户设置页面](https://github.com/settings) 最下方的`Developer setting` ，然后选择 [`Personal access tokens`(点击快捷到达指定页面)](https://github.com/settings/tokens/new) 来生成一个 token，把 `repo`和`workflow` 两部分勾上即可。

![image-20201111142402212](icon/new_access_token.png)

点击最下面的创建按钮后，图示部分即为你的PAT(图示的已经删除了,仅为演示)，复制下来马上就要使用了`如使用双击复制,粘贴后请手动删除多余的空格`建议使用Github自带的复制

![image-20201111145314326](icon/your_new_token.png)



### 填写PAT到Secrets

申请完毕后，在分支中点击`Settings`-`Secrets`-`New secret`

<img src="icon/new_repository_secret.png" alt="set_up_workflow" style="zoom:80%;" />

`name`填`PAT`，`Value`填入上方申请到的PAT,保存即可

![image-20201111144804807](icon/set_sectet_pat.png)



### 手动触发一次代码同步

点击`Actions`,找到指定的脚本,按图示运行一次

![image-20201111145720191](icon/run_reposync_actions.png)

等待两分钟左右,能够发现代码全部同步过来了

![image-20201111145920788](icon/reposync_result.png)

## Enjoy

操作到这一步,表示您已经全部完成了

剩下的去配置cookie等secrets就好啦

## 删除Actions日志
设置需要保留日志天数即可
![1](https://cdn.jsdelivr.net/gh/BlueskyClouds/BlueskyClouds.github.io/2021/05/21/img/1.png)
