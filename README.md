# sumodules
git submodules测试


## submodules 添加（git submodules add)
```
$ git submodule add https://github.com/holidaying/typescriptVue.git src/apps/typescriptVue
Cloning into 'E:/liudan/sumodules/src/apps/typescriptVue'...
remote: Enumerating objects: 57, done.
remote: Counting objects: 100% (57/57), done.
remote: Compressing objects: 100% (41/41), done.
remote: Total 57 (delta 7), reused 57 (delta 7), pack-reused 0
Unpacking objects: 100% (57/57), done.
warning: LF will be replaced by CRLF in .gitmodules.
The file will have its original line endings in your working directory.
```
> 进入typescriptVue

+ 可以执行自己的pull push

## 下载已经关联submodules的项目 
+ 下载主项目 git clone
+ git submodule init -> git submodule update  或者(git clone --recurse-submodules https://github.com/holidaying/typescriptVue.git)

```
$ git submodule init
Submodule 'src/apps/typescriptVue' (https://github.com/holidaying/typescriptVue.git) registered for path 'src/apps/typescriptVue'

ld289@DESKTOP-DU7527P MINGW64 /e/liudan/sumodules (master)
$ git submodule update
Cloning into 'E:/liudan/sumodules/src/apps/typescriptVue'...

```

## 常用命令
+ git submodule foreach pull 遍历更新子模块
+ git config alias.spush 'push --recurse-submodules=on-demand'
+ git config alias.supdate 'submodule update --remote --merge'
+ git spush
+ git supdate
```
$ git supdate

ld289@DESKTOP-DU7527P MINGW64 /e/liudan/sumodules (master)
$ git spush
fatal: AggregateException encountered.
   ·¢ÉúÒ»¸ö»ò¶à¸ö´íÎó¡£
Username for 'https://github.com':

ld289@DESKTOP-DU7527P MINGW64 /e/liudan/sumodules (master)
$ git supdate
remote: Enumerating objects: 4, done.
remote: Counting objects: 100% (4/4), done.
remote: Compressing objects: 100% (2/2), done.
remote: Total 3 (delta 1), reused 0 (delta 0), pack-reused 0
Unpacking objects: 100% (3/3), done.
From https://github.com/holidaying/typescriptVue
   66be908..a5f8bba  master     -> origin/master
Updating 66be908..a5f8bba
Fast-forward
 test | 1 +
 1 file changed, 1 insertion(+)
 create mode 100644 test
Submodule path 'src/apps/typescriptVue': merged in 'a5f8bba35547cd54f859cc4d955691b6c5da5798'
```
+ cat .gitmodules
+ git submodule deinit <子模块名> git rm --cached <子模块名>
+ vi .gitmodules (手动删除连接)

参考项目:[submodules](https://github.com/holidaying/sumodules)