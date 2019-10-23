#book
古籍整理项目
### 通用接口/common
#### 获取书内的文章
    url:queryArticle[get]
    req:
        bookId 书籍id
    resp:
        id 文章标识
        userId 发布者id
        account 发布者账号
        nickName 发布者昵称
        name 文章名
        author 作者
        date 发布时间
#### 获取文章内容
    url:queryPage
    req:
        articleId 文章Id
    resp:
        id 唯一标示
        page 页码
        svg 内容
### 管理员部分接口
#### 获取高级用户升级申请 /admin
    url:queryUserApplication[get]
    req:
    resp:
        id 申请id
        date 申请时间
        userId 申请人的id
        account 申请人的账户
        nickName 申请人的昵称
        registerDate 注册时间
#### 处理申请
    url:handleUserApplication[post]
    req:
        0 驳回
        1 同意
    resp:
#### 获取待审核的书籍
    url:queryUnexaminedBook
    req:
    resp:
        id 书籍id
        account 申请人账户
        nickName 申请人昵称
        name 书名
        publishedDate 出版日期
        author 作者
        writtenDate 成书日期
        date 申请日期
#### 处理待审核书籍
    url:handleUnexaminedBook
    req:
        0 驳回
        1 同意
    resp:
#### 获取被专家审核结束的书籍
    url:queryExpertBook
    req:
    resp:
        id 书籍id
        account 申请人账户
        nickName 申请人昵称
        name 书名
        publishedDate 出版日期
        author 作者
        writtenDate 成书日期
        date 申请日期
        expertDate 专家审核通过的时间
#### 处理被专家审核的书籍
    url:handleExpertBook
    req:
        0 驳回
        1 同意
    resp:
### 专家用户相关接口:/expert
#### 获取所有待审核书籍
    url:queryUnexaminedBook
    req:
    resp:
#### 获取待审核文章
    url:queryUnexaminedArticle
    req:
    resp:
#### 处理待审核书籍
    url:handleBook
    req:
        bookId 书籍Id
    resp:
#### 处理待审核文章
    url:handleArticle
    req:
        0 驳回(删除)
        1 同意入库
    resp:
### 高级用户相关接口/super
#### 申请一本书
    url:applyBook[post] requestBody
    req:
        author 作者
            id 作者id
            name 作者名字，
        writtenDate 成书日期
        authorId 作者Id
        name 书名
        publishedDate 出版时间
    resp:
#### 发布一篇文章
    url:publish[post]
    req:
        xml 文章的xml
        bookId 所属book的id
        pageCount 文章页多少
        pageStart 文章开始页
        name 文章名
        author 作者
            id 作者id
            name 作者name
    resp:
### 普通用户相关接口/normal
#### 申请成为高级用户
    url:apply[post]
    req:
    resp:"# Book" 
