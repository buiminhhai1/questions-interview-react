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
