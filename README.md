# react-thailand-address-typeahead 
> for v1.0 please refer to `v1.0` branch

> Work In Progress

Reimplementation of jquery Thailand in pure React focus on highly customizable rendering

![Demo](./assets/demo.gif)

## Feature
- ✅ Customizable layout
- ✅ Fully customizable CSS
- ✅ Custom datasource option (See [Storybook Custom Option](https://rungsikorn.rocks/react-thailand-address-typeahead/v2#custom-datasource-usage))
- ✅ Keyboard navigation support
- 🚧 datasource compression
- 🚧 Lazy Loading address datasource
- 🚧 Lazy Server Side datasource support
- ️🚧 Form validation support

## Demo
[Example with storybook](https://rungsikorn.rocks/react-thailand-address-typeahead/v2)

## Installation
```
$ npm install react react-dom react-thailand-address-typeahead
```
or
```
$ yarn add react react-dom react-thailand-address-typeahead
```

## Usage
see storybook link here https://rungsikorn.rocks/react-thailand-address-typeahead/v2

```tsx
import React from 'react'
import {
  ThailandAddressTypeahead,
  ThailandAddressValue,
} from "react-thailand-address-typeahead";
const App = () => {
  const [val, setVal] = React.useState<ThailandAddressValue>(
    ThailandAddressValue.fromDatasourceItem({
      d: "Khongteoy",
      p: "Bangkok",
      po: "10110",
      s: "Khongteoy",
    })
  );
  return (
    <ThailandAddressTypeahead
      value={val}
      onValueChange={(val) => setVal(val)}
      datasouce={customDatasource}
    >
      <ThailandAddressTypeahead.SubdistrictInput placeholder="Tumbon" />
      <ThailandAddressTypeahead.DistrictInput placeholder="Amphoe" />

      {/** you can put any customizable layout like below */}
      <div>
        <ThailandAddressTypeahead.ProvinceInput placeholder="Province" />
        <ThailandAddressTypeahead.PostalCodeInput placeholder="Postal Code" />
      </div>

      <ThailandAddressTypeahead.Suggestion />
      { /** or custom our own suggestion with CustomSuggestion */ }
    </ThailandAddressTypeahead>
  );
};
```

### With Create React App
```tsx
// App.js
import './App.css';
import { ThailandAddressTypeahead, ThailandAddressValue } from 'react-thailand-address-typeahead'
import { useState } from 'react';

function App() {
  const [val ,setVal] = useState(ThailandAddressValue.empty())
  return (
    <div className="App">
      <ThailandAddressTypeahead value={val} onValueChange={(val) => {
        setVal({...val})
      }}>
        <ThailandAddressTypeahead.PostalCodeInput />
        <ThailandAddressTypeahead.Suggestion />
      </ThailandAddressTypeahead>
    </div>
  );
}

export default App;
```


# Stats for nerd 🤓
- The gzip result will be around `69KB` according to https://unpkg.com/react-thailand-address-typeahead@2.0.1/dist/index.js
- The performance of searching is WIP




## Original fork and idea 

[earthchie](https://github.com/earthchie/) - Project Owner, Original fork
(you should treat him a beer 😎🍺)
## License
MIT
