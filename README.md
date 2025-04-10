# blind-10-75
Container with most water
Container with Most water

At the core ,simple program.
First we find mathematical formulae.
result= max(result, (right-left)*min(height[right],height[left])
Then , think programatically .

basic brute force approach takes O(n^2).
i.e we iterate through the list .
we fix an element ,and then keep checking all the elements on right subarray,by applying the formula.

But Two pointer approach ,is actually  much better approach bcoz it takes O(n) time.
(Sweep through the list once, at each step update the pointer with less value.

one left pointer and one right pointer.
left , right=0 , len(height)-1
now apply formula on both of them.
Then we update one of the pointers.
Which pointer should be updated?
This is the main question.
The pointer at which least element is present will be updated.
if it is left, increase by one.
if it is right, decrease by one.
i.e At the core,width of container reduces by one. But we making sure our maximum height is kept as benchmark for further internal elements calculation purpose.

One more interesting question is that, if both left and right pointers have same value , then which pointer should be updated.
After spending sometime,by checking various test cases , I understood that, either pointer can be updated.
because all possible container combinations will be covered in formulae.

To put it more simple, at each step, width anyhow gets reduced by one.
if both are different , we take forward max value as benchmark for internal calculations.
if both are same, our work is even simple. we can set either as benchmark.
At the end of the end , the formula involves multiplication, which we are trying to maximize.
it is like a*b.
a will anyhow gets reduced by 1 at each step.
b= min(x,y).
maximizing b = retain maximum from x,y and update the minimum value.
let's say x is maximum .if we retain x as it is and y be pushed to deal with internal values.
we hope that y , i.e there exist some internal value which is much larger than what we already have multiplied. i.e looking to maximize height , i.e looking to fill more water into container.

Time complexity : O(n)
Space complexity : O(1)
