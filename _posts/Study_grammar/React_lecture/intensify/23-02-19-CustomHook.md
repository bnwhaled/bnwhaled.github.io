---
layout: single
title: "Custom Hook"
categories: React
tag: [Sail99, custom_hook ]
---

​	

# Custom Hook

어떤 상황일떄 사용할까?
: 반복되는 보일러 플레이트의 경우 독자적인 로직을 가진 함수(custom hook)
를 만들어 Hook으로 사용

```react
import React, { useState } from "react";

function App() {
  const [name, setName] = useState("");
  const [pw, setPw] = useState("");

  const onChangeNameHandler = (e) => {
    setName(e.target.value);
  };
  const onChangePwHandler = (e) => {
    setPw(e.target.value);
  };
  return (
    <div>
      <input type="text" value={name} onChange={onChangeNameHandler} />
      <input type="password" value={pw} onChange={onChangePwHandler} />
    </div>
  );
}

export default App;
```

해당 경우 input값이 1,2개면 관리가능

하지만 많아질수록 관리 힘듦

==> 고로, React 내장 훅을 사용해 만든 나만의 hook == **CustomHook**



## custom hook만들기

```react
import { useState } from "react";

const useInput = () => {
  //state
  const [value, setValue] = useState("");

  //handler
  const inputHandler = (e) => {
    setValue(e.target.value);
  };
};

export default useInput;

```



### main 페이지 훅  custom hook으로 변경

```react
// import React, { useState } from "react";
import useInput from "./hooks/useInput";

function App() {
  const [name, onChangeNameHandler] = useInput();
  const [pw, onChangePwHandler] = useInput();

  // const [name, setName] = useState("");
  // const [pw, setPw] = useState("");

  // const onChangeNameHandler = (e) => {
  //   setName(e.target.value);
  // };
  // const onChangePwHandler = (e) => {
  //   setPw(e.target.value);
  // };
  return (
    <div>
      <input type="text" value={name} onChange={onChangeNameHandler} />
      <input type="password" value={pw} onChange={onChangePwHandler} />
    </div>
  );
}

export default App;

```

==> 코드 양과 반복이 감소하였음



#### 
