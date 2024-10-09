# Recurrence Analysis -- Mystery Function

Analyze the running time of the following recursive procedure as a function of
$n$ and find a tight big $O$ bound on the runtime for the function. You may
assume that each operation takes unit time. You do not need to provide a formal
proof, but you should show your work: at a minimum, show the recurrence relation
you derive for the runtime of the code, and then how you solved the recurrence
relation.

```javascript
function mystery(n) {
  if (n <= 1) return;
  else {
    mystery(n / 3);
    var count = 0;
    mystery(n / 3);
    for (var i = 0; i < n * n; i++) {
      for (var j = 0; j < n; j++) {
        for (var k = 0; k < n * n; k++) {
          count = count + 1;
        }
      }
    }
    mystery(n / 3);
  }
}
```

Add your answer to this markdown file. [This
page](https://docs.github.com/en/get-started/writing-on-github/working-with-advanced-formatting/writing-mathematical-expressions)
might help with the notation for mathematical expressions.

To start of with, the function recursivly calls itself 3 times and is calling n/3 so we get T(n) = 3T(n/3) then we add the constant time of the operations inside the loops which is n _ n on the first loop and n on the middle and n _ n for the last loop giving us n^5 as the constant. So the full equation is T(n) = 3T(n/3) + n^5. If we use the n ^ log of base b of a and plug in 3 as a for the times called recursivley and plug in 3 for be which is the times the function is divided, we get that it equals n^1. Comparing the fuction constant from before of n^5 to n^1 the n^5 grows faster so we can set T(n) and f(n) to n^5 giving us O(n^5).

I had ai help with the last part of the analysis with how to compare the two answers of n and get the final big o

"I certify that I have listed all sources used to complete this exercise, including the use of any Large Language Models. All of the work is my own, except where stated otherwise. I am aware that plagiarism carries severe penalties and that if plagiarism is suspected, charges may be filed against me without prior notice."
