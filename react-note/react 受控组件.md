在所有 input 上使用的onChange 来进行控制

refs 获取 Dom 元素

    1：第一种方式
        在react元素上定义一个 ref=一个字面量
        通过refs对象获取-----不建议使用
        
    2：第二种方式
        通过回调函数把 Dom 挂载到组件的一个变量上
        例如：ref={(item)=>this.state.dom=item}
        
    3：定义变量
        this.变量名=React.createRef()
        当refs作用在类组件上获取的是 未实例化的组件
        如果想要获取Dom元素，使用react-dom下的findDomNode(this.变量名.current)
        findDomNode(this.变量名.current)