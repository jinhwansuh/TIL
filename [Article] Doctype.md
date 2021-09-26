## DOCTYPE
![](https://images.velog.io/images/jins/post/9397958a-edd2-4d0d-af1e-1b94cfd02ae2/image.png)

기본적이고 필수적인 태그들을 자동으로 만들어줌
<br>
**<\!DOCTYPE html>**
![](https://images.velog.io/images/jins/post/178cbe11-52d1-407f-8fa6-d6a54b77ac17/image.png)

## Version

### HTML5

HTML5은 구조상 DTD로 충분히 정의될 수 없으나 표준 문서를 명시할 필요성이 있으므로 아래와 같은 문서 형식 선언을 갖는다.

`<!DOCTYPE html>`


### HTML 4.01

HTML 4.01의 문서 형식은 Strict, Transitional, Frameset으로 나뉘며, 선언도 마찬가지이다. HTML 4.01 Strict는 표현 효과 위주의 마크업 태크들(<b>, <i> 등)을 금지한다. ex)

```
 <!DOCTYPE HTML PUBLIC
     "-//W3C//DTD HTML 4.01//EN"
     "http://www.w3.org/TR/html4/strict.dtd">
```


### XHTML 1.0


XHTML 1.0도 HTML 4.01과 같이 세 가지 DTD로 구분된다. ex)

```
<!DOCTYPE html PUBLIC
     "-//W3C//DTD XHTML 1.0 Strict//EN"
     "http://www.w3.org/TR/xhtml1/DTD/xhtml1-strict.dtd">
```


### XHTML 1.1


XHTML 1.1은 XHTML 모듈화에 따라 정의되었으며, XHTML 1.0 Strict와 동등하게 엄격하다.

```
 <!DOCTYPE html PUBLIC
     "-//W3C//DTD XHTML 1.1//EN"
     "http://www.w3.org/TR/xhtml11/DTD/xhtml11.dtd">
```

...


<br>


## 모드

"문서 형식 선언"(Document Type Declaration) 또는 **DOCTYPE**이란 어떤 SGML이나 XML 기반 문서 내에 그 문서가 특정 Document Type Definition(DTD)를 따름을 지정하는 것이다.

> SGML *(Standard GeneralStandard Generalized Markup Language) : 다른 마크업 언어를 기술하는 또 다른 마크업 언어*
>
> *XML (Extensible Markup Language) : W3C에서 개발한 마크업 언어를 만드는데 사용되는 다목적 마크업 언어*

브라우저는 **선언된 DOCTYPE**에 따라 렌더링할 모드를 선택하게 된다. 

이 과정을 doctype sniffing OR doctype switching이라 한다.

<br>

### 쿼크모드 (Quirks mode)

- 예전문서라고 판단할 때

이전 세대의 브라우저에 맞는 비표준적 방법의 CSS를 적용

> 목적 : 오래된 웹페이지들이  최신 버전의 브라우저에서  깨져보이지 않게

### 표준모드 (Standard mode)

- 브라우저가 출력하고자 하는 문서가 최신이라고 판단할 때



먼저 DTD의 구성은 **PUBLIC 문자열과 FPI(formal public identifier), FSI(formal system identifier)** 로 이루어져 있다. 

```
<!DOCTYPE 최상위요소 PUBLIC "FPI" "FSI">
<!DOCTYPE 최상위요소 PUBLIC "FPI" "FSI" [
(추가 DTD 선언)
]>
```

  <br>


### doctype선언 2가지


1. FPI와 FSI 모두를 포함하는 doctype 선언 예

<\!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01//EN" "http://www.w3.org/TR/html4/strict.dtd[**Viewer**](http://www.w3.org/TR/html4/strict.dtd?iframe=true&width=100%&height=100%)">

2. FPI만 선언되어있는 doctype 선언 예

<\!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN">



> Doctype의 FPI, FSI가 기술되어 있을 경우  ->  표준모드
>
> FSI가 없는경우, Doctype 무선언 경우  ->  쿼크모드



#### 출처 


http://chongmoa.com/html/441

https://ko.wikipedia.org/wiki/%EB%AC%B8%EC%84%9C_%ED%98%95%EC%8B%9D_%EC%A0%95%EC%9D%98

https://ko.wikipedia.org/wiki/%EB%AC%B8%EC%84%9C_%ED%98%95%EC%8B%9D_%EC%84%A0%EC%96%B8
