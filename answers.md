  # CMPS 6610 Problem Set 02
## Answers

**Name:** Adam Ledet


Place all written answers from `assignment-01.md` here for easier grading.

1. **Prove that logn! ∈ Θ(nlogn).**<br>
log(1) + log(2)... + log(n-1) + log(n) <= n*logn; this means that log(n!) is upper bounded by nlogn.<br>
Stirling's approximation proves that logn! = nlogn; this means that log(n!) is lower bounded by nlogn.<br>
If logn! is upper and lower bounded by nlogn, it is Θ(nlogn).<br>

2. **Asymptotic notation**<br>
* **T(n) = 2T(n/6)+1** is leaf dominated, so the upper bound is <u>O(n^(log_6(2)))</u>. We can tell that this is root dominated by using the Master's Theorum to compare log_6(2) and 1 and see that 1 is asymptotically larger.
* **T(n) = 6T(n/4)+n** is leaf dominated, so the upper bound is <u>O(n^log_4(6))</u>. Using the brick method, we can tell that our cost is increasing from n to (6/4)n at each iteration which is how we know it is leaf doinated.
* **T(n) = 7T(n/7)+n** is balanced, so the upper bound is <u>O(nlogn)</u>>. Our input cost does not change on each iteration which is how we know that it is balanced; so we multiply logb(a) by our base case's cost to get our upper bound.
* **T(n) = 9T(n/4) + n^2** is root dominated, so the upper bound is <u>O(n^2)</u>. We know it is root dominated because our cost decreases from n^2 to (9/16)n^2 on each iteration.
* **T(n) = 4T(n/2) + n^3** is root dominated, so the upper bound is <u>O(n^3)</u>. We know it is root dominated because our cost decreases from n^3 to n^3/2 on each iteration.
* **T(n) = 49T(n/25) + (n^(3/2))logn** is root dominated, so the upper bound is <u>O((n^(3/2))logn)</u>. At our first iteration, we compare our cost of (n^(3/2))logn to 49*(n^(3/2))/(25^(3/2))log(n/25) which simplifies to (n^(3/2))logn > (49/125)n^(3/2)log(n/25). Because our base cost is asymptotically dominant, we use the base cost for our upper bound.
* **T(n) = T(n-1) + 2** is balanced, so the upper bound is <u>O(n)</u>. Using the brick method, we see that our cost remains the same as we decrease to our base case a number of times equal to our tree height which will be n because we are decreasing by 1 each time.
* **T(n) = T(n-1) + n^c** is root dominated, so the upper bound is <u>O(n^(c+1))</u>. This is because we will have a cost of n^c a number of times equal to our tree height which is n. Multiplying n and n^c gives us our n^(c+1) upper bound.
* **T(n) = T(sqrt(n)) + 1** is Root dominated, so our upper bound is <u>O(loglogn)</u>. We can rewrite sqrt(n) as (n^1/2). We can say each input level has a size of (n^(1/(2^k))) such that level 1 has an input size of n^(1/2), level 2 has a size of n^(1/4), and level 3 has a size of n^(1/8). Setting (n^(1/(2^k))) = c means that we can simplify to loglog(n)=k which is our upper bound.

3. **Algorithm Selection**<br>
A)  W(n) = 2W(n/5) + n^2 = *O*(n^2)<br>
    S(n) = S(n/5) + n^2 = *O*(n^2)<br><br>
B)  W(n) = W(n-1) + logn = *O*(nlogn)<br>
    S(n) = S(n-1) + logn = *O*(nlogn)<br><br>
C)  W(n) = W(n/3) + W(2n/3) + n^1.1 = *O*(n^1.1)<br>
    S(n) = S(n/3) + S(2n/3) + n^1.1 = *O*(n^1.1)<br><br>
The best algorithm appears to be B as it completes the smallest amount of work in the least amount of time to solve the problem. 

4. **More Algorithm Selection**<br>
A)  W(n) = 5W(n/2) + n = *O*(n^log_2(5))<br>
    S(n) = S(n/2) + n = *O*(n)<br><br>
B)  W(n) = 2W(n-1) + c = *O*(2^n)<br>
    S(n) = S(n-1) + c = *O*(n)<br><br>
C)  W(n) = 9W(n/3) + n^2 = *O*((n^2)logn)<br>
    S(n) = S(n/3)+n^2 = *O*(n^2)<br><br>
The best algorithm is A because it has one of the better spans and the lowest amount of work. 2^n dominates n^log_2(5) meaning that A's work is asymptotically smaller. If using fewer processors (less parallelism), you will complete the job faster than B. Both A and B will outperform C which has a larger span and is therefore relatively slower when using more processors.
 
5. **Integer Multiplication Timing Results**<br>
I am unable to make my quadratic and subquadratic times consistently distinct. Running the comparison multiple times, occasionally the quadratic will outperform the subquadratic or vise versa for any given problem. This may be because of my own computer or the python compiler I use. I know that, logically, my subquadratic algorithm should complete more complex problems faster at a rate increasing as the problems become more complex; but I am unable to demonstrate this with my work.

6. **Black Hats and White Hats**
<br>6a. Assuming more than half the students are black hats, you cannot trust the truth of any given student's result. A single student tested against every other could have a majority of instances that state they are good, bad, or evenly split. If, however, more than n/2 students are white hat hackers, then any given student will have a truth value of their actual value when paired with every other student.
<br>6b. 
<br>6c. 