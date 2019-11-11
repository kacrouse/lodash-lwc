# lodash-lwc
lodash-es (4.17.15) as a Lightning Web Component

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