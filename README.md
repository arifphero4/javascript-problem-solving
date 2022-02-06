### 1. [ ফাংশন নেম দিতে হবে anaToVori ]: একটা ফাংশন এ প্যারামিটার হিসেবে নিবে আনা (ana)। তারপর সেটাকে ভরি তে কনভার্ট করে কত মান হয় সেই সংখ্যা রিটার্ন করবে। শুধু সংখ্যাটা রিটার্ন করবে।

```
function anaToVori(ana) {
  if (ana <= 0) {
    return "please give a positive value";
  } else if (typeof ana != "number") {
    return "please give number as input value";
  } else {
    let total = ana / 16;
    return total;
  }
}

const totalVori = anaToVori(true);
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

### 3. [ ফাংশন নেম দিতে হবে picnicBudget]: প্যারামিটার হিসাবে নিবে কয়জন পিকিনিক এ যাবে সেই সংখ্যা।

যদি ১০০ বা তার কম যায় তাহলে প্রত্যেক এর জন্য খরচ হবে ৫০০০ টাকা করে।

যদি ১০০ এর বেশি কিন্তু ২০০ এর কম বা সমান যায় তাহলে প্রথম ১০০ জন এর প্রতি জন এর জন্য ৫০০০ টাকা করে দিতে হবে। আর ১০০ এর বেশি (অর্থাৎ ১০১ নম্বর থেকে) যতজন আছে তাদের প্রত্যেক ওই জন্য ৪০০০ টাকা করে দিতে হবে।

আর যদি ২০০ এর বেশি যায় তাহলে প্রথম ১০০ জন এর প্রতি জন এর জন্য ৫০০০ টাকা করে দিতে হবে। আর ১০০ এর বেশি যতজন আছে তাদের প্রত্যেকের জন্য ৪০০০ টাকা করে দিতে হবে। এর ২০০ এর বেশি (অর্থাৎ ২০১ নম্বর থেকে) যতজন আছে তাদের প্রত্যেক এর জন্য ৩০০০ টাকা করে দিতে হবে।

এখন আমি একটা প্যারামিটার দিবো। সেটা যেকোন সংখ্যা হতে পারে। সেই সংখ্যা অনুসারে তুমি ফাংশন থেকে রিটার্ন দিবে কতটাকা পিকনিক এর বাজেট হতে হবে। ইনপুট প্যারামিটার সংখ্যাটা ১০০ এর কম হতে পারে। ১০০ থেকে ২০০ এর মধ্যে হতে পারে। আবার ২০০ এর বেশিও হতে পারে। তাই সব কেইস ভালো করে টেস্ট করে নিবে।

```
function picnicBudget(person) {
  const first100People = 5000;
  const second100People = 4000;
  const restPeople = 3000;

  if (person <= 0) {
    return "please give a positive input value";
  } else if (typeof person != "number") {
    return "please give a number as input value";
  } else if (typeof person == "number") {
    if (person <= 100) {
      let totalBudget = first100People * person;

      return totalBudget;
    } else if (person > 100 && person <= 200) {
      let costForFirst100 = 100 * first100People;
      let costForSecond100 = (person - 100) * second100People;

      const totalBudget = costForFirst100 + costForSecond100;
      return totalBudget;
    } else if (person > 200) {
      let costForFirst100 = 100 * first100People;
      let costForSecond100 = 100 * second100People;
      let costForRestPeople = (person - 200) * restPeople;

      const totalBudget =
        costForFirst100 + costForSecond100 + costForRestPeople;
      return totalBudget;
    }
  }
}

const budget = picnicBudget(150);
console.log(budget);
```

### 4. [ ফাংশন নেম দিতে হবে oddFriend]: একটি অ্যারে এর ভিতরে তোমার বন্ধুদের নাম লিখবে। তোমার যেই বন্ধুর নাম বিজোড় সংখ্যায় আছে তার নাম আউটপুট হিসেবে দেখাতে হবে।

```
function oddFriend(friends) {
  if (Array.isArray(friends)) {
    for (let i = 0; i < friends.length; i++) {
      if (friends[i].length % 2 == 1) {
        return friends[i];
      }
    }
  }
  return "please give a valid input value";
}

const myfriends = ["sarfaraz", "narandra", "ali", "kopila", "aladin", "motin"];
const result = oddFriend(myfriends);
console.log(result);
```
