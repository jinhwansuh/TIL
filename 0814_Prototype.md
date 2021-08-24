# 자바스크립트는?

객체 위주로 설계하고 프로그래밍하는 방식이다. 즉, 객체지향언어;
이때, 각각의 객체는 메세지를 주고받을 수 있다.
**prototype based language(객체지향기반언어)**라고 부르기도 한다.


# Prototype?

본래 객체지향언어(java, python, ruby 등) 에는 클래스라는 개념이 있지만, 자바스크립트에는 클래스 개념이 없다. 대신 프로토타입이 있다. (ECMA6 표준부턴 Class 문법 추가, ~~class는 나중에~~)


[**단, 무조건 객체지향이 절차지향보다 좋은것은 아니다.**
- **간단한 프로그램**에서는 **절차지향**을 이용해 직관적으로 확인하고,
- **복잡한 프로그램**에서 **객체지향**을 이용한다. 
(복잡한 프로그래밍에서 **어떠한 방식으로 흐르는것을 직관적**으로 확인하기 위해) ]


## 그래서 왜 쓸까?
```
function Person(name, first, second, third){
    this.name = name,
    this.first = first,
    this.second = second,
    this.third = third,
    this.sum = function(){
        return this.first + this.second + this.third;
    }
}
```


라는 함수를 보자.

만약 나는 Person함수의 name만 쓰고싶지만, 
Person을 이용했기때문에 다른 함수도 실행이 된다. 

#### 계속해서 생성을 해야하기 때문에 시간이 들고, 메모리 낭비를 초래한다.
#### <u>즉, 성능저하를 불러일으킨다.</u>

```
function Person(name, first, second, third){
    this.name = name;
    this.first = first;
    this.second = second;
    this.third = third;
}

Person.prototype.sum = function(){
    return this.first + this.second + this.third;
}
```
그래서 필요한 함수가 있을때, prototype을 이용하여 따로 정리해 놓는것이 좋다. ( 메모리 낭비 방지 ) 

더 필요하다면, 추가해서 사용하면 된다. 

good이란 함수를 추가해보자.
<br>

```
Person.prototype.good = function(){
    return this.name + '님 안녕하세요';
}
var park = new Person('park',2,4,7);

console.log(park.name); // park
console.log(park.first); // 2
console.log(park.sum()); // 13
console.log(park.good()); // park님 안녕하세요.
```

park.sum()과 park.good() 함수가 필요할때만 호출하면 되기에 메모리 낭비를 방지한다.


![](https://images.velog.io/images/jins/post/386f95f8-a10a-4ccc-aae4-9ca20995f261/image.png)


콘솔에서 확인해보면 Prototype이란 객체가 따로 저장되어있는 것을 확인할수 있다!