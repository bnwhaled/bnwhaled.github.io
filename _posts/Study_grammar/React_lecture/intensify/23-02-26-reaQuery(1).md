---
layout: single
title: "JSON data 맛보기"
categories: JSON
tag: [reactQuery ,Sail99, Practice, setting]
---





# React-Query (1)





> ## 설치 및 세팅

```react
yarn add react-query
```

```react
//react Query 셋팅 1) 전역세팅

import { QueryClient, QueryClientProvider, useMutation } from "react-query";
import Router from "./shared/Router";
const queryClient = new QueryClient();

function App() {
  return (
    <QueryClientProvider client={queryClient}>
      <Router />
    </QueryClientProvider>
  );
}

export default App;
```

```react
//react Query 


//env파일의 환경변수에 URL 설정해두면 전역으로 사용가능
//=====src/.env 
REACT_APP_URL="";

//=====src/api/api.js 생성

//axios 요청 들어가는 모든 모듈
import axios from "axios";

//조회
const getblogs = async () => {
  const response = await axios.get("http://localhost:4010/blogs");//여기에 환경변수/폴더 들어감

  return response.data;
};


//export 해서 쓸수있게
export { getblogs };
```



