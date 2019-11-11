# lodash-lwc
lodash (4.17.15) as a Lightning Web Component

## Usage
1. Copy the `force-app/main/default/lwc/lodash` directory into your org and deploy.
2. Import lodash functions in your components and use as normal!

```javascript
import {LightningElement} from 'lwc';
import {sortBy, groupBy, isNil} from 'c/lodash';

export default class MyComponent extends LightningElement {
  // use sortBy, groupBy, isNil...
}
```

## Build Process
I did this by hand, but it could probably be scripted without too much effort.

1. Run the following command with the [lodash CLI](https://www.npmjs.com/package/lodash-cli): `lodash modularize exports=es -o ./`
2. Rename all files ending in `<filename>.default.js` to `<filename>Default.js`, renaming imports in each file appropriately. The component will fail to compile if a filename contains multiple `.`s, not sure if this is called out in the documentation anywhere...
3. Create a new `modules` directory and move all files except `lodash.js` and `lodashDefault.js` into it, renaming imports in each file appropriately.
