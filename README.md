### 1. [ ফাংশন নেম দিতে হবে anaToVori ]: একটা ফাংশন এ প্যারামিটার হিসেবে নিবে আনা (ana)। তারপর সেটাকে ভরি তে কনভার্ট করে কত মান হয় সেই সংখ্যা রিটার্ন করবে। শুধু সংখ্যাটা রিটার্ন করবে।

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

### 2. [ ফাংশন নেম দিতে হবে pandaCost]: তিনটা প্যারামিটার লাগবে। ভিডিও ভালো করে দেখবে।

১ টি সিঙ্গারা এর দাম – ৭ টাকা

১ টি সমুচা এর দাম – ১০ টাকা

১ টি জিলাপি এর দাম – ১৫ টাকা

এখন সে যদি বিভিন্ন সংখ্যার সিঙ্গারা, সমুচা, আর জিলাপি এর অর্ডার দেয় তাহলে টোটাল কত টাকা খরচ হবে হলো সেই সংখ্যা রিটার্ন করতে হবে।

```
function pandaCost(singgara, somucha, jalebi) {
  const perSinggaraPrice = 7;
  const perSomuchaPrice = 10;
  const perJalebi = 15;

  if (singgara <= 0 || somucha <= 0 || jalebi <= 0) {
    return "please give positive value";
  } else if (
    typeof singgara == "number" &&
    typeof somucha == "number" &&
    typeof jalebi == "number"
  ) {
    const singgaraPrice = perSinggaraPrice * singgara;
    const somuchaPrice = perSomuchaPrice * somucha;
    const jalebiPrice = perJalebi * jalebi;

    const totalCost = singgaraPrice + somuchaPrice + jalebiPrice;
    return totalCost;
  } else {
    return "please give number as input value";
  }
}

const productCost = pandaCost("2", "2", "2");
console.log(productCost);
```
