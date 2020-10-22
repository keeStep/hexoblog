---
date: 2020-10-19 23:23
tags: hexo
---

累了困了，喝乐虎！红红火火恍恍惚惚hhhh

## 关于hexo md文件头配置的理解

---
- 标题会默认取md配置 title， 没有则取文件名
- date只有日期时，在页面的排序是：日期相同则以文件名排序
- 时间会默认取md配置 date， 没有则取文件创建时间
- 子文件夹的文章标题【子文件夹名/子文件名】，格式不满意时，则需在md头配制title

## 切换主题时出现的bug

- 1.图片路径
    有些是利用根路径是可以的，有些则不行，比如：
     - "/themes/dispora/source/css/diaspora.css" 中30行末尾对于 */img/logo.png* 的引用根路径就不行，我采用了相对路径才可
     - "/themes/diapora/layout/_partial/categories.ejs"中对于 */img/welcome-cover.jpg* 的引用根路径就可以
    
    才学疏浅，不知道为什么，待探索

- 2.一些页面路径404
    比如页面 分类，标签就404了，这是因为没有初始化分类的子目录，我们手动初始化一下就可， 如：*hexo new page "categories"*

    问题来了，为什么一定要手动，自动初始化的命令 *hexo g* 不行？
