## React Drag List

This package facilitates the creation of draggable lists in React applications.

### Installation

You can install the react-draglist package using npm, yarn, or pnpm.

npm

```bash
npm install react-draglist
```

yarn

```bash
yarn add react-draglist
```

pnpm

```bash
pnpm add react-draglist
```

### Usage

Once installed, you can import and use the DragList component in your React application.

```tsx
"use client";
import React from "react";
import useDragList from "react-draglist";

const initialItems = [
  { id: 0, text: "One", color: "#616AFF" },
  { id: 1, text: "Two", color: "#2DBAE7" },
  { id: 2, text: "Three", color: "#fd4e4e" },
  { id: 3, text: "Four", color: "#FFBF00" },
  { id: 4, text: "Five", color: "#e66139" },
  { id: 5, text: "Six", color: "#3577ef" },
  { id: 6, text: "Seven", color: "#ababab" },
  { id: 7, text: "Eight", color: "#21C8B7" },
  { id: 8, text: "Nine", color: "#FED67D" },
  { id: 9, text: "Ten", color: "#013540" },
];

export default function App() {
  const { items, getItemProps } = useDragList({
    initialItems,
  });
  return (
    <div className="flex justify-center items-center min-h-screen">
      <ul>
        {items?.map((item: any) => (
          <li className="flex gap-4 my-2" key={item.id}>
            <button
              className="w-10 h-10"
              {...getItemProps(item.id)}
              style={{ background: item.color }}
            >
              ::
            </button>
            <span>{item.text}</span>
          </li>
        ))}
      </ul>
    </div>
  );
}
```
You can customize the appearance and behavior of the DragList component according to your application requirements.
