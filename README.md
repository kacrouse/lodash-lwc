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
1. Run the following command with the [lodash CLI](https://www.npmjs.com/package/lodash-cli): `lodash modularize exports=es -o ./`
2. Rename all default files from `<filename>.default.js` to `<filename>Default.js`, updating imports in each file appropriately. The component will fail to compile if a filename contains multiple `.`s—although not explicitly stated in the documentation, it seems that filenames have the same [restrictions as directory names](https://developer.salesforce.com/docs/component-library/documentation/lwc/lwc.create_components_folder) (excluding the extension).
3. Create a new `modules` directory and move all files except `lodash.js` and `lodashDefault.js` into it, renaming imports in each file appropriately.

## Future Considerations
- Script the build process
- Include `lodash/fp` modules
