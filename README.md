# 📘 React Hooks: useState, useEffect, useLayoutEffect, useRef, useContext

## 🧩 useState
Хук useState позволяет добавлять состояние в функциональные компоненты.

Пример:
```jsx
import React, { useState } from 'react';

function Counter() {
  const [count, setCount] = useState(0);

  return (
    <div>
      <p>Счётчик: {count}</p>
      <button onClick={() => setCount(count + 1)}>Увеличить</button>
    </div>
  );
}
```
## 🎬 Пример видео
[![видео](https://img.youtube.com/vi/O6P86uwfdR0/maxresdefault.jpg)](https://www.youtube.com/watch?v=O6P86uwfdR0)

## ⚙️ useEffect
Хук useEffect выполняет побочные эффекты в функциональных компонентах, такие как запросы к API или подписки.

Пример:
```jsx
import React, { useState, useEffect } from 'react';

function FetchData() {
  const [data, setData] = useState(null);

  useEffect(() => {
    fetch('https://api.example.com/data')
      .then(response => response.json())
      .then(data => setData(data));
  }, []); // Пустой массив означает, что эффект выполнится только при монтировании компонента

  return <div>{data ? JSON.stringify(data) : 'Загрузка...'}</div>;
}
```
## 🎬 Пример видео
[![видео](https://img.youtube.com/vi/dH6i3GurZW8/maxresdefault.jpg)](https://www.youtube.com/watch?v=dH6i3GurZW8)

## 🖼️ useLayoutEffect
Хук useLayoutEffect работает аналогично useEffect, но выполняется синхронно сразу после всех изменений DOM, что позволяет избежать визуальных сдвигов.

Пример:
```jsx
import React, { useState, useLayoutEffect } from 'react';

function LayoutEffectExample() {
  const [width, setWidth] = useState(0);

  useLayoutEffect(() => {
    setWidth(window.innerWidth);
  }, []);

  return <div>Ширина окна: {width}</div>;
}
```
## 🎬 Пример видео
[![видео](https://img.youtube.com/vi/wU57kvYOxT4/maxresdefault.jpg)](https://www.youtube.com/watch?v=wU57kvYOxT4)

## 🔗 useRef
Хук useRef сохраняет изменяемые значения, которые не вызывают повторный рендер компонента. Он также используется для доступа к DOM-элементам.

Пример:
```jsx
import React, { useRef } from 'react';

function FocusInput() {
  const inputRef = useRef();

  const handleClick = () => {
    inputRef.current.focus();
  };

  return (
    <div>
      <input ref={inputRef} placeholder="Нажмите кнопку, чтобы сфокусироваться" />
      <button onClick={handleClick}>Фокус на поле ввода</button>
    </div>
  );
}
```
## 🎬 Пример видео
[![видео](https://img.youtube.com/vi/t2ypzz6gJm0/maxresdefault.jpg)](https://www.youtube.com/watch?v=t2ypzz6gJm0)

## 🌐 useContext
Хук useContext позволяет подписаться на контекст React и получать его значение.

Пример:
```jsx
import React, { useContext } from 'react';

const ThemeContext = React.createContext('light');

function ThemedComponent() {
  const theme = useContext(ThemeContext);

  return <div style={{ background: theme === 'dark' ? '#333' : '#fff' }}>Тема: {theme}</div>;
}

function App() {
  return (
    <ThemeContext.Provider value="dark">
      <ThemedComponent />
    </ThemeContext.Provider>
  );
}
```
## 🎬 Пример видео
[![видео](https://img.youtube.com/vi/5LrDIWkK_Bc/maxresdefault.jpg)](https://www.youtube.com/watch?v=5LrDIWkK_Bc)
