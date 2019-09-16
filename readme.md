## React hoạt động như thế nào?

- Babel: https://babeljs.io/docs/en/

- Demo về Babel: https://babeljs.io/repl

```javascript
const arr = [1, 2, 3];

const arrCopy = [...arr, 4, 5];
```

- `React` và `ReactDOM`: https://codepen.io/no197/pen/jONKxop

  - `ReactDOM`: Tương tác với `DOM` của trang web

  - `React`: Tạo ra các `Component`, các thành phần giao diện và xử lý logic giữa các thành phần đó

- `React` được sử dụng ở đâu mà phải `import`?

  - `JSX` trong `React`?

    ```XML
        <JSXName JSXAttributes> // --> OpenTag
        ....                    // ---> Children(Content or Nested Component)
        </JSXName>          // --> CloseTag
    ```

  - Ví dụ:

    ```XML
    <MyButton color="blue" shadowSize={2}>
    Click Me
    </MyButton>
    ```

  * Self Closing:

    ```XML

    <div className="sidebar" />

    ```

  - Trước khi có `JSX`?

    ```javascript
    React.createElement(MyButton, { color: "blue", shadowSize: 2 }, "Click Me");
    ```

    --> Babel chuyển từ `JSX` sang `React.createElement` nên cần import `React`

  - Nhúng `javascript` vào `JSX`

    ```javascript
    const a = 1;
    <h1> {a} </a>
    ```

    --->Dùng cặp `{}` để thêm `javascript` vào `JSX`

## Component

- ### Component ????

  Một `function` hoặc `class` mô tả một thành phần giao diện và trả về thành phần giao diện đó

  ![alt text](https://i2.wp.com/programmingwithmosh.com/wp-content/uploads/2018/08/React-Components-Example-1024x556.jpeg?resize=700%2C380&ssl=1 "Component")

  ![alt text](https://miro.medium.com/max/303/1*7AM6LF0vaLNt9UPTOo5JPw.png "Component")

  - render
  - state
  - props
  - context
  - lifecycle events

* ### Khi nào tách một `Component` thành cách phần nhỏ hơn?

  Khi `Component` đó có các thành phần được dùng đi dùng lại nhiêu lần hoặc được sử dụng ở nhiều nơi trong project

  ![alt text](https://ihatetomatoes.net/wp-content/uploads/2017/08/01-collapsible-component-with-props-1024x639.png "Component")

- PROPS

  `Props` là properties của một `component` . Chúng ta có thể set giá trị `props` của một `component` bằng cách truyền dữ liệu từ ngoài vào. Khi một `props` được truyền vào `component` thì giá trị của nó là không thay đổi .

* STATE

  `State` biểu hiện trạng thái của `component`, state là private và chỉ thay đổi bên trong bản thân `component` đó.

* STATE vs PROPS

  ![alt text](https://ihatetomatoes.net/wp-content/uploads/2017/08/03-state-vs-props-1024x460.png "Component")

- ### Có bao nhiêu cách tạo component?

  Có 2 cách là dùng `class` và dùng `function`

- ### Tại sao lại có 2 cách?

  - Nếu một `component` sử dụng `state` thì nó `nên` được dùng với `class` và được gọi là `stateful component`

  ![alt text](https://miro.medium.com/max/2800/1*gv0YJ8Z1QwkDlQPkraSUDw.png "Component")

* Ngược lại `component` không sử dụng `state` thì nó `nên` dùng `function` và được gọi là `stateless component`

  -Điểm khác nhau giữa ful và less :))
  ![alt text](https://miro.medium.com/max/2400/1*mPWvIvfhzLpnzkgUg7sePg.png "Component")

- ### Em chưa học OOP nên không biết dùng class :)) em có thể dùng function để tạo stateful component không ?

  Đã giải thích rồi còn hỏi nhiều quá 😒 cơ mà được nha! React mới đây đã cung cấp cho chúng ta một tính năng mới là `Hooks` nếu dùng `function` + `Hooks` ==> `stateful component`

- ### Thực hành tạo các Component và hướng dẫn các phím tắt

  - Sử dụng `create-react-app` để tạo project: npx `create-react-app`
  - Sử dụng thư mục `react-component`
  - Cài các `package`: `npm install`
  - Run project: `npm start`
  - html to JSX tool

  - `Đề bài`: Tạo một form gồm một thanh input và một button ADD

- ## Handling Events trong react

  Trong react ta có một số hàm bắt sự kiện cho handle như `onClick`, `onChange`, `onSubmit`

  Ví dụ:

  ```javascript

  const handleClick = ()=> console.log("Clicked!")

  <button onclick={handleClick!}>Click me!</button>
  ```

  `LƯU Ý`: Do con trỏ `this` nên để tránh rắc rối nên dùng `arrow function` cho các handle event

  - `Thực hành:` ứng dụng Click me!: https://codesandbox.io/s/magical-morning-po7zn

* ## Một vài vấn đề với state

  - `State` không thể modify trực tiếp để thay đổi state ta phải dùng hàm `setState()`
    ![alt text](https://cdn-media-1.freecodecamp.org/images/1*qle8858T8Amobp6-WCrLZA.png "Component")

  - `State` là private nên chỉ tồn tại trong nội bộ component

- ## Hooks căn bản với useState

  - ### Chuyển Class sang Function + useState

    - Xây dựng đồng hồ đơn giản:

      ![alt text](https://cdncontribute.geeksforgeeks.org/wp-content/uploads/Renderingclock_ReactJS.gif "Component")


    - `Demo`: https://d5c28.csb.app/

    - `Code`: https://codesandbox.io/s/pedantic-cookies-d5c28

- ## Tách component và cách truyền dữ liệu giữa các component thông qua props

  Viết lại ứng dụng click me bằng cách tách component

  ![alt text](https://www.kirupa.com/react/images/color_property_144.png "Component")

  `CHÚ Ý:` List & key

- ## React Lifecycle

  ![alt text](https://i0.wp.com/blogs.innovationm.com/wp-content/uploads/2018/05/React-Compnonent-Lifecycle-final.png?fit=777%2C650 "Component")

* `Ví dụ`: https://about.phamvanlam.com/demo/understand-react-component-lifecycle/

* `THAM KHẢO`: https://programmingwithmosh.com/javascript/react-lifecycle-methods/

* ## Thực hành: Ứng dụng nuôi cá và trồng thêm rau 😂😂

  ![alt text](https://i.imgur.com/bR31pIl.png "Component")

- API: https://5d7c82296b8ef80014b29af9.mockapi.io/api/v1/farm
- Demo: https://dxrce.csb.app/#
- Code: https://codesandbox.io/s/modest-fast-dxrce

- ## useRef, useEffect, useContext trong Hooks

  - Sử dụng useEffect thay thế cho cdm, cdu và cwum

  - Giới thiệu về uncontroled form

  - useContext

- ## Thực hành xây dựng app todo

* ## Bất lợi của việc one-way data bindings trong react và giới thiệu về redux

  - State có thể rất phức tạp

    ![alt text](https://cloud.netlifyusercontent.com/assets/344dbf88-fdf9-42bb-adb4-46f01eedd629/cbd8cb0f-97ee-4da0-8913-ac9892621c91/redux-example-css-tricks-opt.pg_ "Component")

- Để quản lý các state phức tạp người ta sử dụng đến các mô hình State management như redux, flux, mobX, contextAPI...

- Mỗi một mô hình có một ưu nhược điểm riêng

- Ở đây ta sẽ làm quen với redux

### 3 nguyên tắc cơ bản của redux

1. Single source of truth: State của toàn bộ ứng dụng được lưu trong trong 1 store duy nhất là 1 Object mô hình tree.

   - Tất cả những thay đổi của state là rõ ràng và có thể đoán trước được

   ```javascript
   {
   todos: [{
    text: 'Eat food',
    completed: true
   }, {
    text: 'Exercise',
    completed: false
   }],
   visibilityFilter: 'SHOW_COMPLETED'
   }

   ```

2) State is read-only: Chỉ có 1 cách duy nhất để thay đổi state đó là tạo ra một action (là 1 object mô tả những gì xảy ra)

   - Nếu cần thay đổi một state hãy `dispatch` một `function`. Function là một javascript Object mô tả hành động thay đổi.

3) Changes are made with pure functions: Để chỉ rõ state tree được thay đổi bởi 1 action bạn phải viết pure reducers

![alt text](https://camo.githubusercontent.com/9de527b9432cc9244dc600875b46b43311918b59/68747470733a2f2f73332e616d617a6f6e6177732e636f6d2f6d656469612d702e736c69642e65732f75706c6f6164732f3336343831322f696d616765732f323438343739302f415243482d5265647578322d657874656e6465642d7265616c2d6465636c657261746976652e676966 "Component")

### Imutable trong redux và một số trick cơ bản

- `Pure function` ?

  - Là hàm nhận tham số đầu vào và trả về một giá trị được tính toán dựa trên giá trị đầu vào nhưng không làm thay đổi nó

  - Ví dụ:

  ```javascript
  function square(x) {
    return x * x;
  }
  ```

* `Impure function` là gì?

  ```javascript
  function square(x) {
    updateXInDatabase(x);
    return x * x;
  }
  ```

- `immutable`:
  Thử với đoạn code sau

  ```javascript
  //Khai báo biến String
  var a = "123";

  //Tiến hành thay đổi giá trị của a

  a[2] = "1"; // Kết quả mong muốn a = "121"

  console.log(a); // "123"

  a = "121";

  console.log(a);
  ```

* Trick immutable:

- Nối hai mảng và cộng thêm giá trị vào mảng:

```javascript
let a = [1, 2, 3];
const b = [4, 5, 6];
const c = 0;

// Cộng mảng b và c vào a

//es6
a = [...a, ...b, c];
```

- Xóa một phần tử trong mảng

```javascript
let a = [1, 2, 3];

// Xóa số 2 trong mảng

//es6
a = a.filter(item => item !== 2);
```

- Thay đổi giá trị một phần tử trong mảng

```javascript
let a = [1, 2, 3];

// Thay đổi số 2 thành số 4

//es6
a = a.map(item => {
  if (item !== 2) return item;

  return 4;
});
```

- Nối một Object vào Object và thay đổi một thuộc tính của Object

```javascript
let todo = { name: "Learn React", teacher: "Dan Abramov" };
const isCompeleted = { isCompeleted: false, teacher: "Fb dev team" };

todo = { ...todo, isCompeleted };

//Có thể tìm hiểu thêm về Object.assign()
```

- Xóa một thuộc tính của Object

```javascript
let todo = { name: "Learn Redux", teacher: "Dan Abramov", isCompeleted: true };

const { isCompeleted, ...rest } = todo;

todo = rest;
```

#### Các thành phần của redux

- Actions

  Trong Redux action là 1 pure object định nghĩa 2 thuộc tính là : type: kiểu mô tả action, và payload: giá trị tham số truyền lên

  ```javascript
  {
  type: "KIEU_ACTION",
  payload: //tham số
  }
  ```

- Reducers

  Action có nhiệm vụ mô tả những gì xảy ra nhưng lại không chỉ rõ phần state nào của response thay đổi -> Việc này sẽ là của Reducer đảm nhiệm:

  Reducer nhận 2 tham số vào: 1 state cũ và action được gửi lên sau đó trả ra một state mới, ko làm thay đổi state cũ.

  ```
  (previousState, action) => newState
  ```

- Store
  Store là 1 object lưu trữ state của toàn bộ ứng dụng có 3 phương thức sau:

  - `getState()`: Giúp lấy ra state hiện tại
  - `dispatch(action)`: Thực hiện gọi 1 action
  - `subscrible(listener)`:Nó có vai trò cực quan trọng, luôn luôn lắng nghe xem có thay đổi gì ko rồi ngay lập tức cập nhật ra View

  - Khởi tạo store thông qua hàm `createStore(reducer)`

Ví dụ: https://jsbin.com/beremuyime/edit?js,output
