静态属性发生改变时触发

    static getDerivedStateFromProps(){
        //初始化数据更新 会触发
    }//出现警告 
        1：添加state
        2：没有启动服务

当打开浏览器生命周期运行顺序

    componentWillMount(){
        //第一个执行
    }
    render(){
        //第二个执行
    }
    componentDidMound(){
        //第三个执行
    }


当state发生改变时触发生命周期顺序
    
    shouldComponentUpdate(){
        //第一个执行
        //当返回值为true时继续执行后面的生命周期 否则终止
    }
    render(){
        //第二个执行
    }
    componentDidUpdate(){
        //第三个执行
    }
    
当props发生改变时触发生命周期顺序

    componentWillReceiveProps(){
        //第一个执行
    }
    shouldComponentUpdate(){
        //第二个执行
        //当返回值为true时继续执行后面的生命周期 否则终止
    }
    render(){
        //第三个执行
    }
    componentDidUpdate(){
        //第四个执行
    }