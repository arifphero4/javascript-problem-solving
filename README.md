### 1. [ ফাংশন নেম দিতে হবে anaToVori ]: একটা ফাংশন এ প্যারামিটার হিসেবে নিবে আনা (ana)। তারপর সেটাকে ভরি তে কনভার্ট করে কত মান হয় সেই সংখ্যা রিটার্ন করবে। শুধু সংখ্যাটা রিটার্ন করবে।

/_ problem-1 _/

```
function anaToVori(ana) {
  if (ana <= 0) {
    return "please give a positive value";
  } else if (typeof ana == "string") {
    return "please give number as input value";
  } else if (typeof ana == "number") {
    let total = ana / 16;
    return total;
  }
}

const totalVori = anaToVori(32);
console.log(totalVori);
```

###
