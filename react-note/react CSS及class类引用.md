正常引入

    import "./style.css"
    //容易造成全局污染
    
避免全局污染

    1:引入前css 文件必须跟后缀 .module
        例如：style.module.css
    2:引入后声明 名称
        import homecss from "./style.module.css"
    3:引用时
        <div className={homecss.active}>
        
添加多重类名 使用模板字符串不同类名使用空格间隔

    <div className={${homecss.active} ${homecss.header}}></div>