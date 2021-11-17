# Draw

1. We get the list of purchases from the canister: https://ic.rocks/principal/bid2t-gyaaa-aaaah-qcdea-cai > addressesForDraw()
2. We confirm the number of addresses in the list matches the number of purchased tokens (1113) - Check
3. We will confirm on twitter a future number to be drawn and used - https://twitter.com/toniqlabs/status/1461070305825214466
4. We will use the following function to generate a number between 0 - 1112 (array position of the winner):
```
function xmur3(str) {
   for (var i = 0, h = 1779033703 ^ str.length; i < str.length; i++)
      h = Math.imul(h ^ str.charCodeAt(i), 3432918353),
      h = h << 13 | h >>> 19;
   return function() {
      h = Math.imul(h ^ h >>> 16, 2246822507);
      h = Math.imul(h ^ h >>> 13, 3266489909);
      return (h ^= h >>> 16) >>> 0;
   }
}
var positionOfWinnerInArray = xmur3(seed)() % 1113;
```

# Winner
