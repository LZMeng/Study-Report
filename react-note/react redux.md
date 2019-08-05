基本框架

    1：创建reducer.js文件
    定义默认
        const defaultState={}
    定义函数
        const reducer=(state=defaultState,action)=>{
            var newstate=JSON.pase(JSON.stringfiy(state))
            
            return newstate
        }
        export default reducer
    
    2：创建store.js库
        import {createStore} from "react"
        import reducer from "./reducer"
        const store=createStore(reducer)
        expore default store
    
    使用redux 单一下载redux
        import store from "./redux/store"
        引用四种方法
            1：store.dispatch({type:类型})
            2：store.replaceReducer()
            3：store.subscribe(()=>{
                //监听数据变化
                this.getState({})//必须传参{}
            })
            4：store.getState({})
    
    使用react-redux  必须下载 redux和react-redux
        在主 index 内对<App/>进行包装
            import {Provider} from "react-redux"
            import store from "./redux/store"
            ReactDOM.render(<Provider store={store}><App /></Provider>, document.getElementById('root'));
        
        组件引用仓库
            import {connect} from "react-redux"
            
            定义class组件
            class home extends Component{
                constructor(props){
                    super(props)
                    this.state={}
                    
                },
                render(){
                    this.props //接收mygetstate和mysetstate 的返回值
                    return (<>
                    </>)
                }
            }
            
            定义获取函数
            var mygetstate=state=>{//必须有返回值
                return state
            }
            定义抛出函数
            var mysetstate=dispatch=>{
                //上传到仓库对数据进行更新 自动监听并渲染页面
                return {
                   //定义触发方法
                   add(){
                       dispatch({type:类型})
                   },
                   del(){
                       dispatch({type:类型})
                   }
                }
            }
            mygetstate和mysetstate的返回值全部传入 home 内的this.props 内
            使用高阶函数挂载抛出
            export default connect(mygetstate,mysetstate)(home)