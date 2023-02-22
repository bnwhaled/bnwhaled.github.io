---
layout: single
title: "Input값 Num 정규표현식(콤마표현)"
categories: React
tag: [Sail99, TIL]
---



# 클릭시 모달창 띄우기



```react
const Input = () => {

const [id, setId] = useState('');
const [price,setPrice] = useState('');


const idChangeHandler = (e) => {
setId(e.target.value);
console.log('id :', id);
}

const priceChangeHandler = (e) => {
const res = e.target.value.replaceAll(',','').replace(/\B(?<!\.\d*)(?=(\d{3})+(?!\d))/g, ",");
setPrice(res);
}

return (
<>
<StMain>
<Box>
<Margin>
<P>Input</P>
이름 &nbsp; <InputName placeholder='이름을 입력해 주세요.' type="text" value={id} onChange={idChangeHandler}/>

가격 &nbsp; <InputPrice placeholder='가격을 입력해 주세요.' id="number" type="text" value={price} onChange={priceChangeHandler}/>

<AddBtn onClick={()=>{
alert(`name은 ${id}이며 price는 ${price}입니다.`)
}}>저장</AddBtn>
</Margin>
</Box>
</StMain>
</>
)
}

export default Input;
```

