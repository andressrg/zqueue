# ZQueue

Queue and run promise based jobs. Can be used to control the use of resources like upload bandwith effectively.

### Example

```javascript
import { ZQueue } from 'zqueue';
import axios from 'axios';

const queue = new ZQueue({ max: 3 });

queue.run(() => axios.put(myUrl1, file1));
queue.run(() => axios.put(myUrl2, file2));
queue.run(() => axios.put(myUrl3, file3));
queue.run(() => axios.put(myUrl4, file4));
queue.run(() => axios.put(myUrl5, file5));

// A maximum of 3 uploads will be ran at the same time.

```
