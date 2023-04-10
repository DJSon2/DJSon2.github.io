---
layout: single
title: ModifyMode with useState and Hook in React
---

# Modify Mode in React

## ModifyMode를 찾은 이유

ERP 관련 프로젝트 진행 중 데이터 update가 필요한 부분이 있었다.
update 방법을 찾던 중 수정 모드를 클릭 시 수정 모드가 활성화되어서 값을 변경할 수 있고 저장시 변경한 값이 저장되는 방식이였다.
해당 방법이 신기하여서 프로젝트 당시 그 방법을 적용하기 위해 원리를 찾아보고 적용했다.

## ModifyMode란?

처음에는 ModifyMode란 React에서 공식적으로 제공하는 상태 변수나 Hooks의 종류 중 하나인줄 알았지만 그런것은 아니였다.
단지 커스텀 변수 이름으로 ModifyMode를 사용했던 것이였다.
        
그럼 여기서 이 수정 모드를 만들었던 방법은 일반적으로 React 애플리케이션에서 상태를 관리하는 'useState'를 사용하면된다.
여기서 'useState'는 함수형 컴포넌트에서 상태 변수를 선언하고 관리할 수 있도록 해준다.
        
'useState' 사용 시 첫 번째 요소는 상태(state)변수의 현재 값을 나타내고, 두 번째 요소는 상태 변수를 갱신할 수 있는 함수이다.
이 함수를 호출하면 첫 번째 요소의 값을 갱신할 수 있다.

먼저 코드로 보면
```
 function 수정 모드 실행할 함수명() {
    const [modifyMode, setModifyMode] = useState(false);        // 수정 모드 적용할 useState
    const [form, setForm] = useState(null);                     // 변경된 값 적용할 useState
```
다음 코드와 같이 useState를 수정 모드를 위한 modifyMode와 수정된 값을 데이터에 적용할 form을 각각 만들어줬다.
그리고 수정 모드 버튼을 누르면 수정모드가 되기위한 onClick이벤트 함수도 만들어준다.

```
  const onClickModifyModeHandler = () => {
        setModifyMode(true);                // 상태값을 true로 바꿔 수정 가능하게 만들어준다.
        setForm({
           변경된 값을 적용할 데이터들       // 적용할 값을 state에 저장하기 위해 설정해준다.
        });
    }
```

이후 새로 적용될 데이터를 정상적으로 update하기위한 onClick이벤트를 하나 더 만들어준다.
```
  const 수정적용할 버튼명 = () => {        
        dispatch(백단과 통신할 리듀서 함수명({	              // 리듀서 함수를 실행시키는 dispatch를 이용해 데이터 수정을 실행시킨다.
            form: form
        }));         
        alert('급여 수정이 완료되었습니다')                   // 확인 창
        navigate(`/hr-team2/salary`, { replace: true});      // 수정 후 이전 화면으로 돌아가기
    }    
```

이와같이 만들고 난 후 화면에 보여질 부분을 작성해주면 

```
    return (
        <>
        { salary &&
            <div>
                <table>
                <colgroup>
                        <col width="5%" />
                        <col width="10%" />
                    </colgroup>
                    <tbody>            
                        <tr>
                            <th>남은 연차 일</th>
                            <td>
                                <input 
                                    name='vacationPay'
                                    readOnly={modifyMode ? false : true}                         // input으로 만들었기 때문에 수정모드가 아닐 때는 수정이 불가하게 readOnly를 사용해주었고
                                    style={ !modifyMode ? { backgroundColor: 'gray'} : null}     // 수정이 불가한 상태를 표시하기 위해 회색으로 표시를 해주었다.
                                    type='number'
                                    onChange={ onChangeHandler }                                 
                                    value={ form == null ? salary?.vacationPay : form?.vacationPay } // 값을 표시할 부분
                                />
                            </td>
                        </tr>
                    </tbody>                    
                </table>            
            </div>
            }
        </>
```
이와같이 작성을 해주면 화면상에는 수정모드가 아닐 때는 회색 처리가 되며 값 변경이 불가하지만 수정 모드를 눌렀을 때 색이 바뀌면서 값의 변경이 가능하게 된다.
이후 바꾼 값을 적용 시킬 클릭 이벤트를 활성화 시키면 설정해둔 함수가 실행되면서 백단과의 통신과 DB의 데이터가 변경될 수 있다.

       
       
       
지금까지 프로젝트에서 사용해봤던 수정 모드를 리뷰했었는데 결론적으로 말하자면 React에 있는 useState를 응용한 방식이며 똑같이 값을 변경해 사용이 가능하지만 어떤 방식으로 사용하냐에 따라 사용자가 좀 더 효율적으로 혹은 창의적으로 사용할 수 있을 것 같다.
