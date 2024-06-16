# 2.1 JSX란

JavaScript XML(eXtensible Markup Language)의 약어로, HTML 요소에 유효한 자바스크립트 객체를 내장할 수 있는 자바스크립트 확장이다. XML과 유사한 내장형 구문이며, 리액트에 종속적이지 않은 독자적인 문법이다.

JSX는 자바스크립트 표준코드가 아닌 메타가 임의로 만든 새로운 문법이기 때문에 반드시 트랜스파일러를 거쳐야 비로소 자바스크립트 런타임이 이해할 수 있는 js코드로 변환된다.

리액트에서는 보통 HTML과 JS를 별도로 작성하기보다는, JSX를 이용하여 두가지를 모두 포함하고 있는 ‘컴포넌트’를 생성한다.

JSX는 HTML보다는 자바스크립트에 가깝다고 한다.

</br>

## 💡 브라우저가 JSX 파일을 읽을 수 있는가?

    브라우저는 직접 읽을 수 없으며, 바벨과 같은 컴파일러를 통해 JSX를 JS객체로 변환을 해야한다.

</br>

## 📌 JSX의 구성요소?

1.  **JSXElement**
    - JSX를 구성하는 가장 기본 요소
    - HTML의 element와 비슷한 역할
    - 다음의 형태 중 하나를 가져야 한다.
      - `<JSXOpeningElement>` : 여는 태그
      - `</JSXClosingElement>`: 닫는 태그
      - `<JSXSelfClosingElement />` : 내부적으로 자식 포함이 불가한 형태
      - `<></>` : 아무런 요소가 없는 형태 (JSXFragment)
2.  **JSXAttributes**
    - JSXElement에 부여할 수 있는 속성
    - 필수값이 아니기때문에, 존재하지 않아도 에러가 나지 않는다.
3.  **JSXChildren**
    - JSXElement의 자식 값을 나타낸다.
    - JSX는 속성을 가진 트리 구조를 나타내기 위해 만들어져, JSX로 부모와 자식 관계를 나타낼 수 있으며, 그 자식을 JSXChildren이라고 한다.
4.  **JSXStrings**
    - <>문자열</>
    - html에서 사용가능한 문자열은 모두 JSXStrings에서도 가능함.
    - 개발자가 HTML 내용을 손쉽게 JSX로 가져올 수 있도록 의도적으로 설계되었다.

</br>

## 💡 리액트에서 사용자 정의 컴포넌트 이름은 대문자로 시작하는 이유

    SXElement에 명시되어있는 표준규칙은 아니지만 리액트에서는 HTML 태그명과 사용자 정의 컴포넌트 태그명을 구분하기 위해 반드시 대문자로 시작하는 컴포넌트를 만들어야만 사용이 가능하다.

```jsx
function hello(text) {
  return <div>hello {text}</div>;
}

export function App() {
  //Property 'hello' does not exist on type 'JSX.IntrinsicElements'
  return <hello text="안녕하세요" />;
}
```
