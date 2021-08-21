
> Javascript가 발전하면서 브라우저(클라이언트) 단에서 렌더링을 하고, 서버에서는 브라우저 렌더링에 필요한 데이터만 제공하는 형태로 기술이 변화했다.


그래서, 직접적으로 `DOM을 다루는 행위가 감소`했고, 
`상태(State)를 기준`으로 DOM을 렌더링하는 형태로 발전했다.

그래서 두가지 개념이 생겼다.

### SSR(Server-Side Rendering)
- JSP, PHP, ASP 등 서버에서 HTML을 만들어서 클라이언트에 넘겨주는 것
- 브라우저에서는 데이터를 정교하게 관리할 필요가 없었다.

### CSR(Client-Side Rendering)
- 브라우저 단에서 모든 렌더링을 처리 하려는 시도를 하였고, React Angular Vue 같은 프레임워크가 탄생
- 브라우저 단에서 렌더링에 필요한 상태를 정교하게 관리해야 한다. (Redux 탄생)


## 컴포넌트 

![네이버](https://images.velog.io/images/jins/post/816328c7-f957-403f-948a-39f7fc3fbed7/image.png)

- 서로의 기능을 간섭하지 않기위해
- 생성과 수정 등 재사용이 간편하다.

> 효율적인 개발과 유지보수를 위해 계층구조 컴포넌트를 사용한다.



### 참조
https://junilhwang.github.io/TIL/Javascript/Design/Vanilla-JS-Component/
