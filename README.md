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
  { id: 0, text: "Wahyu" },
  { id: 1, text: "Agus" },
  { id: 2, text: "Arifin" },
];

export default function App() {
  const { items, getItemProps } = useDragList({
    initialItems,
  });

  const COLOR = (n: number) => {
    switch (n) {
      case 1:
        return "bg-red-600 hover:bg-red-800"
      case 2:
        return "bg-indigo-600 hover:bg-indigo-800"
      default:
        return "bg-lime-600 hover:bg-lime-800"
    }
  }
  return (
    <div className="flex justify-center items-center min-h-screen">
      <div className="max-w-3xl">
        <ul>
          {items?.map((item: any) => (
            <li className="flex gap-4 my-2 items-center" key={item.id}>
              <button
                className={`w-10 h-10 rounded-lg text-2xl ${COLOR(item.id)}`}
                {...getItemProps(item.id)}
              >
                ::
              </button>
              <span>{item?.id + 1} : {item.text}</span>
            </li>
          ))}
        </ul>
      </div>
    </div>
  );
}
```
You can customize the appearance and behavior of the DragList component according to your application requirements.
### Demo

[Here](https://react-draglist-example.vercel.app/)
