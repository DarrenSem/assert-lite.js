# assert-lite.js
MINIMAL assertion library. Stand-alone vanilla JavaScript to mimic ChaiJS/node:assert (core minifies to 194 chars, yet is very easily expandable)

```js
// 366 characters with .equal(via ==/isNaN) and .strictEqual(via Object.is)
((a,b,c)=>{a[b]||=c()})(this,"assert",_=>{var a=Number.isNaN;let b=String,c=a=>"`"+b(a)+"`",d=(a,b,d,e)=>{if(!b)throw Error(e.length?e.join(" "):`expected ${c(d)} ${a}`)},e=(a,...b)=>d(`to be truthy`,a,a,b);{let b=a;e.equal=(a,e,...f)=>d(`to equal ${c(e)}`,a==e||b(a)&&b(e),a,f)}return e.strictEqual=(a,b,...e)=>d(`to strictly equal ${c(b)}`,Object.is(a,b),a,e),e});

// 194 characters for core
((a,b,c)=>{a[b]||=c()})(this,"assert",_=>{let a=String,b=b=>"`"+a(b)+"`",c=(a,c,d,e)=>{if(!c)throw Error(e.length?e.join(" "):`expected ${b(d)} ${a}`)};return(a,...b)=>c(`to be truthy`,a,a,b)});
```
