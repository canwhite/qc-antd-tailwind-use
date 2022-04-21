## qc-antd-tailwind-use

css modules 、 sass 、antd and tailwind


### how to use tailwind

```
1.装包，这三个，npm或yarn都可以
"autoprefixer": "*",
"postcss": "*",
"tailwindcss": "*"

2.添加craco配置层
npm install @craco/craco
接着更改scripts
"scripts": {
    "start": "craco start",
    "build": "craco build",
    "test": "craco test",
    "eject": "react-scripts eject"
},
然后根目录手动创建一个craco.config.js文件，加入插件
主要就是这俩插件，当然我们可以eject之后，去更改内置的postcss配置
module.exports = {
    style: {
        postOptions: {
            plugins: [
                require('tailwindcss'),
                require('autoprefixer'),
            ],
      },
    },
}

3.创建配置文件
npx tailwind init
编辑：
module.exports = {
  purge: ['./src/**/*.{js,jsx,ts,tsx}', './public/index.html'],
  darkMode: false, 
  theme: {
    extend: {},
  },
  variants: {
    extend: {},
  },
  plugins: [],
}

4.将tailwind引入src/index.css头部
@tailwind base;
@tailwind components;
@tailwind utilities;


最后将index.css引入到你的src/index.js文件中 

import './index.css';


5.使用
<div className='text-red-500'>xxx</div>
```


### how to use antd

```
1.yarn add antd

2.修改 src/App.css，在文件顶部引入 antd/dist/antd.css
@import '~antd/dist/antd.css';

3.使用
import React from 'react';
import { Button } from 'antd';
import './App.css';

const App = () => (
  <div className="App">
    <Button type="primary">Button</Button>
  </div>
);

export default App;

```

## css modules

```
原始的直接引入，然后找到classname !important就可以修改了
css modules稍微有些变化
命名改为 xxx.module.css | sass
import引入，改andt就可以:global了
``` 