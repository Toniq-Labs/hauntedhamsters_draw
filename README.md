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
*Note - we ended up doing a redraw. The first winner was 888 which was a Toniq employee*
```
var seed = "83983cc464c23d7cee6468b431dadc65b830bdcea9e47afed2babc7b902528a4"; //as per 22620 from https://ptodj-lqaaa-aaaah-qaeaq-cai.raw.ic0.app/
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
console.log(positionOfWinnerInArray);
```
**Position 179 in the buyers array is the winner**
Winner: 3e95f5562382fb9a0c2f5eb41f4107d46ffa76256813b803f4168d9008fc4e06
