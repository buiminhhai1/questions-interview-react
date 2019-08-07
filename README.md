# questions-interview-react
## I. Core React
### 1. What is React? React là gì? 
React is a JavaScript library for building user interfaces. 
React là một thư viện JavaScript được dùng để xây dựng User Interface.

### 2. What are the major features of React? Những tính năng chính của React là gì? 
The major features of React are: 
- It uses VIrtualDOM instead RealDOM considering that RealDom manipulations are exspensive.
- Support server-side rendering
- Follows Unidirectional data flow or data binding
- User reuseable/ composable UI components to develop the view.

Tính năng chính của React là: 
- Nó sử dụng DOM ảo thay vì DOM thực vì thao tác trên DOM thực sẽ chậm và tốn nhiều chi phí hơn.
- Hỗ trợ server-side rendering
- Theo luồng dữ liệu một chiều hoặc 
- khả năng reUseable/ composable UI component.

### 3. What is JSX? JSX là gì? 
JSX is a XML-like syntax exntension to ECMAScript (the acronym stands for JavaScript XML). Basically it just provides syntactic sugar for the React.createElement() function, giving us expressiveness of JavaScript along with HTML like template syntax.

JSX là một cú pháp mở rộng của JavaScript nó cho phép người dùng có thể lồng code HTML vào trong đó. Nó được đề nghị dùng trong React để mô tả UI và nó có toàn bộ sức mạnh của JavaScript.

```python
class App extends React.Component {
  render(){
    return (
      <div>
        <h1> {'Hello React JS '} </h1>
      </div>
    );
  }
}
```
### 4. What is the difference between Element and Component? 
An Element is a plain object describing what you want to appear on the screen in terms of the DOM nodes or other components.
Elements can contain other Elements in their props. 
Creating a React element is cheap. 
Once an element is created, it is never mutated.
The object representation of React Element would be as follows:
```python
const element = React.createElement(
  'div',
  {id: 'login-btn'},
  'Login'
);
```
The above React.createElement() function returns an object:
```python
{
  type:'div',
  props: {
    children: 'Login',
    id: 'login-btn'
  }
}
```
and finally it renders to the DOM using ReactDOM.render();
```python
// this is result
<div id="login-btn">Login</div>
```
Whereas a Component can be declared in several different ways.
It can be a class with a render() method. 
Alternatively, in simple cases, it can be defined as a function. In either case, it takes props as an input, and returns as JSX tree as the output:
```python
const Button = ({onLogin}) => <div id="login-btn" onClick={onLogin}>Login</div>
```

### 6. When to use a Class COmponent over a Function Component? 
Nếu như bạn cần sử dụng lifecycle thì nên dùng class component, tài vì phiên bản mới của React bạn có thể quản lý trạng thái với function component thông qua use State.

### 7. What are Pure Components? 
  React.PureComponent is exactly the same as React.Component except that it handles the shouldComponentUpdate() method for you. When props or state changes, PureComponent will do a shallow comparision on both props and state. Component on the other hand won't compare current props and state to next out of the box. Thus, the component will re-render by default whenever shouldComponentUpdate is callled.

  React.PureComponent hoàn toàn giống như React.Component ngoài trừ nó xử lý phương thức shouldComponentUpdate() cho bạn. Khi props hay state changes, PureComponent sẽ thực hiện so sánh nông (so sánh địa chỉ con trỏ) trên cả props và state. Như vậy PureComponent sẽ re-render mỗi khi phương thức shouldComponentUpdate được gọi.

### 8. What is state in React? State là gì trong React? 
State of a component is an object that holds some information that may change over the lifetime of the component. We should always try to make our state as simple as possible and minimize the number of stateful components. 

State của một Component là một đối tượng nó giữ một số thông tin của component và nó có thể thay đổi trong vòng đời của Component. Chúng ta nên làm cho state đơn giản nhất có thể và làm giảm số lượng stateful components.

State giống như props, nhưng nó là của riêng và được điều khiển bởi component. còn props thì component chỉ có thể truy cập vào để đọc dữ liệu.

### 9. What are props in React? 
Props là đầu vào (input) của Component

### 11. Why should we not update the state directly? 
(tại sao ta không nên cập nhật state trực tiếp?)
Nếu như bạn thử cập nhật state trực tiếp thì nó sẽ không được re-render component.
(trừ khi bạn dùng trong constructor)

### 12. What is the purpose of callback function as an argument of setState()?
```python
 this.setState((prevState) => {
            return {showSideDrawer: !prevState.showSideDrawer};
        });
```
setState là một hàm bất đồng bộ, callback sẽ được gọi sau khi setState đã hoàn thành, (phiên bản mới nhất của state)
