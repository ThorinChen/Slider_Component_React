# Slider-Vertify_Component_React
 Slider-Vertify component for mobile and web terminal Based on React&JavaScript

## description
 
Slider-vertify is a sliding verification code component implemented by the front end. Through it, we can easily control the entire verification life cycle (when refreshing, when the verification is successful, and when the verification fails), and have certain configurational capabilities.

![demo.gif](slider.gif)

## doc

[react-slider-vertify](https://github.com/ThorinChen/Slider_Component_React/blob/main/src/Vertify/index.md)

## Getting Started

Install dependencies,

```bash
$ npm i react-slider-vertify
```

## Use

```tsx
import React, { useState } from 'react';
import { Vertify } from 'react-slider-vertify';

export default () => {
  const [visible, setVisible] = useState(false);
  const show = () => {
    setVisible(true);
  };
  const hide = () => {
    setVisible(false);
  };
  const style = {
    display: 'inline-block',
    marginRight: '20px',
    marginBottom: '20px',
    width: '100px',
    padding: '5px 20px',
    color: '#fff',
    textAlign: 'center',
    cursor: 'pointer',
    background: '#1991FA',
  };
  return (
    <>
      <div onClick={show} style={style}>
        show
      </div>
      <div onClick={hide} style={style}>
        hide
      </div>
      <Vertify
        width={320}
        height={160}
        visible={visible}
        onSuccess={() => alert('success')}
        onFail={() => alert('fail')}
        onRefresh={() => alert('refresh')}
      />
    </>
  );
};
```

#### Example
 **Demo source：[click](https://github.com/ThorinChen/Slider_Component_React/blob/main/src/Vertify/index.md)**
