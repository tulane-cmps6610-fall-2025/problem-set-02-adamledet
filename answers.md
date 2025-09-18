  # CMPS 6610 Problem Set 02
## Answers

**Name:**Adam Ledet


Place all written answers from `assignment-01.md` here for easier grading.

1. **Prove that logn! is a member of theta(nlogn).**
log(1) + log(2)... + log(n-1) + log(n) <= n*logn; this means that log(n!) is upper bounded by nlogn.
[PUT REASON HERE]; this means that log(n!) is lower bounded by nlogn.
If logn! is upper and lower bounded by nlogn, it must be a memebr of theta(nlogn).

2. **Asymptotic notation**
* T(n) = 2T(n/6)+1 is root dominated, so the upper bound is O(n^(log_6(2))). We can tell that this is root dominated by using the Master's Theorum to compare log_6(2) and 1 and see that 1 is asymptotically larger.
* T(n) = 6T(n/4)+n is leaf dominated, so the upper bound is O(n^log_4(6)). Using the brick method, we can tell that our cost is increasing from n to (6/4)n at each iteration which is how we know it is leaf doinated.
* T(n) = 7T(n/7)+n is balanced, so the upper bound is O(nlogn). Our input cost does not change on each iteration which is how we know that it is balanced; so we multiply logb(a) by our base case's cost to get our upper bound.
* T(n) = 9T(n/4) + n^2 is root dominated, so the upper bound is O(n^2). We know it is root dominated because our cost decreases from n^2 to (9/16)n^2 on each iteration.
* T(n) = 4T(n/2) + n^3 is root dominated, so the upper bound is O(n^3). We know it is root dominated because our cost decreases from n^3 to n^3/2 on each iteration.
* T(n) = 49T(n/25) + (n^(3/2))logn is root dominated, so the upper bound is O((n^(3/2))logn). At our first iteration, we compare our cost of (n^(3/2))logn to 49*(n^(3/2))/(25^(3/2))log(n/25) which simplifies to (n^(3/2))logn > (49/125)n^(3/2)log(n/25). Because our base cost is asymptotically dominant, we use the base cost for our upper bound.
* T(n) = T(n-1) + 2 is balanced, so the upper bound is O(n). Using the brick method, we see that our cost remains the same as we decrease to our base case a number of times equal to our tree height which will be n because we are decreasing by 1 each time.
* T(n) = T(n-1) + n^c is root dominated, so the upper bound is O(n^(c+1)). This is because we will have a cost of n^c a number of times equal to our tree height which is n. Multiplying n and n^c gives us our n^(c+1) upper bound.
* T(n) = T(sqrt(n)) + 1 is Root dominated, so our upper bound is O(loglogn). We can rewrite sqrt(n) as (n^1/2). We can say each input level has a size of (n^(1/(2^k))) such that level 1 has an input size of n^(1/2), level 2 has a size of n^(1/4), and level 3 has a size of n^(1/8). [UNFINISHED]

3. **Algorithm Selection**
A)  W(n) = 2W(n/5) + n^2 = O(n^2)
    S(n) = S(n/5) + n^2 = O(n^2)
B)  W(n) = W(n-1) + logn = O(nlogn)
    S(n) = S(n-1) + logn = O(nlogn)
C)  W(n) = W(n/3) + W(2n/3) + n^1.1 = O((n^1.1)logn)
    S(n) = S(n/3) + S(2n/3) + n^1.1 = O(n^1.1)
The 'best' algorithm appears to be B as it completes the smallest amount of work in the least amount of time to solve the problem. 

4. **More Algorithm Selection** 
A)  W(n) = 5W(n/2) + n = O(n^log_2(5))
    S(n) = S(n/2) + n^2 = O(n^log_2(5))
B)  W(n) = 2W(n-1) + c = O(2^n)
    S(n) = S(n-1) + c = O(n)
C)  W(n) = 9W(n/3) + n^2 = O((n^2)logn)
    S(n) = S(n/3)+n^2 = O(n^2)
The 'best' algorithm is again B as it completes the task in the smallest span, but it does require a great amount of work to do so. When using a relatively small number of processors, this could be expecially slow as a great deal of work is calculated, but this algorithm will work best when you have a theoretical 'infinite' number of processors. In a practical scenario where you do have a finite number of processors, both algorithm A and C could be appropriate. While algorithm C has a lower span, it also requires more work while algorithm A has a more balanced 'work/span' ratio.
 
5. **Integer Multiplication Timing Results**
[FINISH CODING ASSIGNMENT]

6. **Black Hats and White Hats**
[WRITE ANSWER HERE]