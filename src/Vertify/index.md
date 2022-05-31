### basic use:

```tsx
import React from 'react';
import { Vertify } from 'react-slider-vertify';

export default () => {
  return <Vertify />;
};
```

### set width and height:

```tsx
import React from 'react';
import { Vertify } from 'react-slider-vertify';

export default () => {
  return <Vertify width={330} height={80} />;
};
```

### set slider side length and radius:

```tsx
import React from 'react';
import { Vertify } from 'react-slider-vertify';

export default () => {
  return <Vertify width={320} height={160} l={28} r={5} />;
};
```

### callback when setting succeeded, failed and refreshed:

```tsx
import React from 'react';
import { Vertify } from 'react-slider-vertify';

export default () => {
  return (
    <Vertify
      width={320}
      height={160}
      onSuccess={() => alert('success')}
      onFail={() => alert('fail')}
      onRefresh={() => alert('refresh')}
    />
  );
};
```

### user defined check logic:

The component exposes the 'oncustomverify' method and accepts the incoming parameter 'verify' object. We can control whether the verification succeeds by controlling the 'split' and 'verified' attributes, that is, the function return value must contain attribute objects with Boolean values of 'split' and 'verified'

```tsx
import React from 'react';
import { Vertify } from 'react-slider-vertify';

export default () => {
  const handleCustomVertify = (vertify) => {
    console.log(vertify, Math.abs(left - destX) < 5);
    const { destX, left, spliced, verified } = vertify;
    return {
      spliced: Math.abs(left - destX) < 5,
      verified,
    };
  };
  return (
    <Vertify
      width={320}
      height={160}
      onCustomVertify={handleCustomVertify}
      onSuccess={() => alert('success')}
      onFail={() => alert('fail')}
      onRefresh={() => alert('refresh')}
    />
  );
};
```

### Dynamic settings show / hide:

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

<API></API>
