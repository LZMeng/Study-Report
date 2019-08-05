注意事项
    
    1：state 或 props 不可以直接修改
        必须通过 this.setState({
            需要修改的属性：修改后的值
        })
        
    2：只有state 或 props 发生改变后 页面才会更新
    
创建组件方法

    import Home from "./home"
        引入组件是或调用使用时组件首字母必须大写
    
    
基本 react 搭建

    import React, {Component} from "react"
    
    定义组件分为 2 种
    1：class类组件
        //有生命周期
        //可以定义内部 state 值
        class 组件名称 extends Component{
            render(){
                 return (<>
                    //必须有返回值必
                    //内容必须存放在第一个标签内否则报错
                </>)
            }
           
        }
        export default 组件名称
    2：函数表达式定义
        //没有生命周期
        //不可以定义内部state
        function 组件名称(){
            return (<>
                 //必须有返回值必
                    //内容必须存放在第一个标签内否则报错
            </>)
        }
        export default 组件名称
        
默认设置

    static defaultProps={
        title:1
    }//只针对当前组件生效
    //接收的值 优先级大于 静态设置 优先展示接收的值
    
    static getDerivedStateFromProps(){
        //初始化数据更新 会触发
    }//出现警告 
        1：添加state
        2：没有启动服务