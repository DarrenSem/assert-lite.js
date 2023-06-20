# assert-lite.js
MINIMAL assertion library. Stand-alone vanilla JavaScript to mimic ChaiJS/node:assert (core minifies to 193 chars, yet still easily expandable)

```javascript
// 193 characters for core
((a,b,c)=>{a[b]||=c()})(this,"assert",_=>{let a=String,b=b=>`|${a(b)}|`,c=(a,c,d,e)=>{if(!c)throw Error(e.length?e.join(" "):`Expected ${b(d)} ${a}`)};return(a,...b)=>c(`to be truthy`,a,a,b)});

// 368 characters with .equal(==) and .strict(Object.is)
((a,b,c)=>{a[b]||=c()})(this,"assert",_=>{var a=Number.isNaN;let b=String,c=a=>`|${b(a)}|`,d=(a,b,d,e)=>{if(!b)throw Error(e.length?e.join(" "):`Expected ${c(d)} ${a}`)},e=(a,...b)=>d(`to be truthy`,a,a,b);{let b=a;e.equal=(a,e,...f)=>d(`to loosely equal ${c(e)}`,a==e||b(a)&&b(e),a,f)}return e.strict=(a,b,...e)=>d(`to strictly equal ${c(b)}`,Object.is(a,b),a,e),e});
```
