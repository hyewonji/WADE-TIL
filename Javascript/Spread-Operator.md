### Spread Operator

```jsx
const days = ["Mon", "Tues", "Wed"];
const otherDays = ["Tue", "Fri", "Sat"];

const allDays1 = days + otherDays;
let allDays2 = [days + otherDays];
let allDays3 = [days, otherDays];

console.log(allDays1);
//Mon,Tues,WedThu,Fri,Sat
//배열이 아니고 String이 됨

console.log(allDays2);
//['Mon,Tues,WedThu,Fri,Sat']

console.log(allDays3);
//[Array[3],Array[3]]
```

```jsx
const days = ["Mon", "Tues", "Wed"];
const otherDays = ["Tue", "Fri", "Sat"];

let allDays = [...days, ...otherDays, "Sun"];

console.log(allDays);
//['Mon', 'Tues', 'Wed', 'Tue', 'Fri', 'Sat', 'Sun']
```

- Array 뿐만 아니라 Object에도 적용된다.
