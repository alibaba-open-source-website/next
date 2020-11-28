# 基本用法

-   order: 0

最基本的用法。可以通过 `onChange` 监听选中值的变化。

:::lang=en-us

# Basic

-   order: 0

A basic usage case.

:::

---

```jsx
import { useState } from 'react';
import { DatePicker2, Switch } from '@alifd/next';

function App() {
    const [mode, setMode] = useState('date');

    const onChange = v => {
        setMode(v ? 'date' : 'range');
    };

    return (
        <div>
            mode：
            <Switch size="small" onChange={onChange} />
            <div>
                <DatePicker2
                    showTime
                    // visible
                    // preset={[{ name: 'now', label: '此刻', value: Date.now(), type: 'secondary' }]}
                    key={mode}
                    format="YYYY-MM-DD HH:mm:ss"
                    type="date"
                />
            </div>
            <div>
                <DatePicker2
                    // showTime
                    // visible
                    // preset={[{ name: 'now', label: '此刻', value: Date.now(), type: 'secondary' }]}
                    key={mode}
                    type="range"
                />
            </div>
        </div>
    );
}

ReactDOM.render(<App />, mountNode);
```