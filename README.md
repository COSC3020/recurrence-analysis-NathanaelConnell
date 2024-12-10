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
I had ai help with understanding the master theorum.  

Let T(n) represent the runtime.  The function consists of three recursive calls to mystery(n/3), contributing 3T(n/3), and a triple nested loop with bounds O(n^2), O(n), and O(n^2), resulting in O(n^5) work.  This gives the recurrence T(n) = 3T(n/3) + O(n^5).  Using the Master Theorem for divide and conquer recurrences, we calculated p = log(base three) 3 = 1.  Comparing p and d = 5, we find p < d, meaning the non recursive work O(n^5) dominated the runtime.  The tight big-O bound for the runtime of the function is O(n^5).

"I certify that I have listed all sources used to complete this exercise, including the use of any Large Language Models. All of the work is my own, except where stated otherwise. I am aware that plagiarism carries severe penalties and that if plagiarism is suspected, charges may be filed against me without prior notice."
