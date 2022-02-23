# Note

# FAKE API

https://reqres.in/

# Configure import alias

https://koprowski.it/import-alias-in-react-native-and-vscode/

# Json icon

https://icomoon.io/

# Optimize image

https://imageoptim.com/mac

# Over API

https://overapi.com/

# ES6

https://github.com/lukehoban/es6features

# Javascript Interview Questions

https://www.interviewbit.com/javascript-interview-questions?fbclid=IwAR3140uhzPwvaFY60t2qb66Gj-bx_R0JvYr2_dcshC0zMpX831tRAHT-3sI

# Json severe

https://github.com/typicode/json-server

# React native not running on M1

https://gist.github.com/ildfreelancer/c161628115e590749599ceb6e623125c

# React Native vs TypeScript

https://github.com/anywhichway/nano-memoize

# Update version React Native

https://react-native-community.github.io/upgrade-helper/

# Lifecycle React Native

https://projects.wojtekmaj.pl/react-lifecycle-methods-diagram/

- Mounting:
  - componentWillMount: được thực thi trước khi giao diện được render ra màn hình (tạo ra các state và giao diện)
  - componentDidMount: được thực thi sau khi render đầu tiên được sinh ra ở phía client (dùng để call API, setTimeout, setInterval, thay đổi state, props,... )
- Update:
  - componentWillUpdate: được gọi trước khi component được rendering (update state, props)
  - componentDidUpdate: được gọi sau khi component được rendering ( sau khi re-render thành công)
- Unmount:
  - componentWillUnmount: được gọi sau khi component unmount từ dom ( bước cuôi xong hết mọi thứ)

# Props

- Props là cách để bạn có thể truyền dữ liệu từ component cha xuống component con.
- Example:
  - ```
    <ClickMe name="Click me" />
    ```
  - ```
    const ClickMe = (props) => {
      <View>
      <Text>props.name</Text>
      </View>
      }
    ```

# State

- State dùng để quản lý trạng thái ở mức độ component và state thì có thể thay đổi

# Components

- là các thực thể độc lập, tự duy trì mà mô tả một phần giao diện người dùng của bạn. Giao diện người dùng của một ứng dụng có thể chia thành các component nhỏ hơn, mỗi component sẽ có cấu trúc, code, API riêng của nó. Kiến trúc component cho phép bạn nghĩ đến từng thành phần cô lập với nhau. Mỗi component có thể cập nhật mọi thứ trong phạm vi của nó mà không cần phải quan tâm đến việc nó ảnh hưởng đến các component khác như thế nào. Các components cũng có thể tái sử dụng.

# React Hooks ( React version >= 16.8)

## useState

- Quản lí state của function component
- Gồm 2 phần là tên của state và 1 method để cập nhật lại state
- Muốn thay đổi trên giao diện thì sử dụng useState thay vì useRef
- Example
  - ```
    const [count, setCount] = useState(0) or const [count, setCount] = useState(() => {
      //function
      });
    ```
  - ```
    setCount(count + 1);
    ```

## useEffect

- Sử dụng khi :
  - Call API
  - Các sự kiện (click, scroll, ...)
  - Thao tác DOM
  - setTimeout, setInterval, ...
- Có 2 tham số là 1 function và 1 dependencies.
- Luôn luôn chạy khi component được mount.
- Có 3 dependencies chính là [], [dependencies] và không truyền
- Example
  - ```
    useEffect(() => {
    //componentDidMount & componentDidUpdate
    // your code
    return () =>{
    //componentWillUnMount
    }
    },[] or [dependencies] or )
    ```

## useMemo

- Chỉ sử dụng khi tính toán nặng.
- Có 2 tham số là 1 function và 1 dependencies.
- Tránh chạy các hàm tính toán lại nếu k có sự thay đổi của dependencies.
- Example
  - ```
    const example = useMemo(() => {
      // function
      },[dependencies])
    ```

## useRef

- Lưu lại tham chiếu
- Truy xuất vào DOM
- Không bị khởi tạo lại như object
- Không làm re-render như useState
- Example
  - ```
    const example = useRef(0);
    ```
  - ```
    example.current;
    ```

## useCallback

- Tránh gán lại tham chiếu cho function
- Không tạo lại tham chiếu mới
- Xài khi function đó được truyền từ cha và con
- Example
  - ```
    const example = useCallback(() => {
     // function
     })
    ```

## useContext

- Truyền giá trị từ component cha đến component cháu mà không cần qua props và không đi qua component con
- Example

```
  import React, {createContext} from 'react';

  const ThemeContext = React.createContext();

  const example = () => {
    <ThemeContext.Provider value='dark'>
     <View>
        // your code
     </View>
    </ThemeContext.Provider>
  }

How to Use It

  import {useContext} from 'react';

  const theme = useContext(ThemeContext);
```

# React.Memo

- Lưu input của component đó khi có sự thay đổi prop mới render lại
- Example
  - ```
    const example = React.memo((props) {
      // return
      });
    ```

# Scale font in numbers

```

Text.defaultProps = {
...(Text.defaultProps || {}),
allowFontScaling: true,
maxFontSizeMultiplier: ${number},
};
TextInput.defaultProps = {
...(TextInput.defaultProps || {}),
allowFontScaling: true,
maxFontSizeMultiplier: ${number},
};

```

# Axios request not working in IOS simulator (React Native)

- Update your Info.plist with :

```

<key>NSAppTransportSecurity</key>
<dict>
<key>NSAllowsArbitraryLoads</key>
<true/>
</dict>

```

# Run device by Wifi

Connect device via wifi
http://facebook.github.io/react-native/docs/running-on-device.html#method-2-connect-via-wi-fi

1. Connect your mobile device via usb (just this once)
2. Establish a port with your mobile device using 'adb tcpip <port number>'. eg. adb tcpip 5555
3. Remove USB and 'adb connect <mobile device ip><above mentioned port number>'. Eg . adb connect 192.160.0.124:5555
4. 'React-native run-android' in your project folder

# adb

- adb device
- adb logcat
