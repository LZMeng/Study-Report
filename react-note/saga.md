
active.js
    
    import TypeName from './className'
    import Fn from './Functions'
    const defaultState = {
        num: 0
    }
    export default (state = defaultState,active) => {
            let newState = {...state};
    
        switch (active.type) {
            case TypeName.ADD:
                var val = Fn.ADDFN(active.value);
                newState.num = val
            break;
            default:
            break;
        }
        return newState
    
    }

store.js 

    import {createStore, applyMiddleware} from 'redux'
    import active from './active'
    
    import createsaga from 'redux-saga'
    import {listsaga} from '../saga'
    
    let sagamidd = createsaga()
    const stores = createStore(active, applyMiddleware(sagamidd))
    
    sagamidd.run(listsaga)
    
    export default stores
    
saga.js

    import {takeEvery, take, put} from 'redux-saga/effects'
    function* Num(abs){
        yield put({
            type:'ADD',
            value:abs.value
        })
    }
    export function* listsaga(){
        // yield takeEvery('ADDS', Num, '789')  //针对既定的值
        var takestate = yield take('ADDS');  // 返回 通过 dispatch 传送来的值
        yield Num(takestate)
    }
    
react组件.js  

    <button onClick={()=>this.props.dispatch({type:'ADDS',value:'666'})}>saga</button> // 触发的saga listsaga 内定义的 ADDS