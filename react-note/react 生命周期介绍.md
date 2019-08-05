静态属性发生改变时触发

    static getDerivedStateFromProps(){
        //初始化数据更新 会触发
    }//出现警告 
        1：添加state
        2：没有启动服务
        
    componentWillMount(){
        //打开页面首先执行 接收上传的值
    }
    componentWillReceiveProps(){
        //当父级传递的值发生改变触发 props  为变后的值 state为空对象
        //this.props为改变之前的值
    }
    render(){
        return (<>
            //虚拟DOM
            //必须有返回值
            //渲染内容必须存放在第一个标签内
        </>)
    }
    componentDidMount(){
        //DOM 元素渲染完毕后执行
        //可运行异步函数 实例化对象等
        //可获取 DOM节点
    }
    shouldComponentUpdate(){
        //当改变state时，第一个参数为空对象
        //第二个参数为改变后数据,必须给返回值当 为true时继续执行，当为false时阻止执行
    }
    getSnapshotBeforeUpdate(){
       //必须有返回值
       //获取更新前的DOM信息传递给下一个生命周期
        return 123
    }
    componentDidUpdate(preprops,prestate,snap){
        //当改变state时
        //第一个参数为空对象
        //第二个参数为改变前数据
        //snap 接收上一个生命周期的返回值
    }
    componentWillUnmount(){
        //销毁阶段，
        //可摧毁 定时器 异步函数 等
        
        this.变量名.destroy //销毁
    }