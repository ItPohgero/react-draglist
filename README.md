## React Drag List

This package facilitates the creation of draggable lists in React applications.

### Installation

You can install the react-draglist-ipo package using npm, yarn, or pnpm.

npm

```bash
npm install react-draglist-ipo
```

yarn

```bash
yarn add react-draglist-ipo
```

pnpm

```bash
pnpm add react-draglist-ipo
```

### Usage

Once installed, you can import and use the DragList component in your React application.

```tsx
"use client";
import React from "react";
import { useDragList } from "react-draglist-ipo";

const initialItems = [
  { id: 0, text: "Wahyu", color: "#4d7c0f" },
  { id: 1, text: "Agus", color: "#7e22ce" },
  { id: 2, text: "Arifin", color: "#9f1239" },
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

### Demo

