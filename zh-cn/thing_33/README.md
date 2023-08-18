# 浮点数不是真实的

Floating-point numbers are not "real numbers" in the mathematical sense, even though they are called *real* in some programming languages, such as Pascal and Fortran. Real numbers have infinite precision and are therefore continuous and non-lossy; floating-point numbers have limited precision, so they are finite, and they resemble "badly-behaved" integers, because they're not evenly spaced throughout their range.

浮点数不是数学意义上的 "实数"，尽管在某些编程语言（如 Pascal 和 Fortran）中被称为 "实数"。实数的精度是无限的，因此是连续的、无损耗的；浮点数的精度是有限的，因此是有限的，它们类似于 "不乖 "的整数，因为它们在整个范围内的间距并不均匀。

To illustrate, assign 2147483647 (the largest signed 32-bit integer) to a 32-bit float variable (x, say), and print it. You'll see 2147483648. Now print `x - 64`. Still 2147483648. Now print `x - 65` and you'll get 2147483520! Why? Because the spacing between adjacent floats in that range is 128, and floating-point operations round to the nearest floating-point number.

举例说明，将 2147483647（最大的有符号 32 位整数）赋值给一个 32 位浮点变量（例如 x）并打印出来。你会看到 2147483648。现在打印 `x - 64`。还是 2147483648。现在打印 `x - 65`，结果是 2147483520！Why? 因为在这个范围内，相邻浮点数之间的间距是 128，而浮点运算四舍五入到最接近的浮点数。

IEEE floating-point numbers are fixed-precision numbers based on base-two scientific notation: 1.d<sub>1</sub>d<sub>2</sub>...d<sub>p-1</sub> × 2<sup>e</sup>, where *p* is the precision (24 for float, 53 for double). The spacing between two consecutive numbers is 2<sup>1-p+e</sup>, which can be safely approximated by ε|x|, where ε is the *machine epsilon* (2<sup>1-p</sup>).

IEEE 浮点数是基于二进制科学记数法的固定精度数：1.d<sub>1</sub>d<sub>2</sub>...d<sub>p-1</sub> × 2<sup>e</sup>, 其中 *p* 是精度（浮点数为 24，双数为 53）。两个连续数字之间的间距为2<sup>1-p+e</sup>,可以安全地用 ε|x| 近似，其中 ε 是 * 机器ε*(2<sup>1-p</sup>)。

Knowing the spacing in the neighborhood of a floating-point number can help you avoid classic numerical blunders. For example, if you're performing an iterative calculation, such as searching for the root of an equation, there's no sense in asking for greater precision than the number system can give in the neighborhood of the answer. Make sure that the tolerance you request is no smaller than the spacing there; otherwise you'll loop forever.

了解浮点数邻域的间距可以帮助您避免经典的数字错误。例如，如果您正在执行迭代计算，如寻找方程的根，那么在答案附近要求比数字系统所能提供的更高精度是毫无意义的。确保你要求的公差不小于这里的间距，否则你将永远循环下去。

Since floating-point numbers are approximations of real numbers, there is inevitably a little error present. This error, called *roundoff*, can lead to surprising results. When you subtract nearly equal numbers, for example, the most significant digits cancel each other out, so what was the least significant digit (where the roundoff error resides) gets promoted to the most significant position in the floating-point result, essentially contaminating any further related computations (a phenomenon known as *smearing*). You need to look closely at your algorithms to prevent such *catastrophic cancellation*. To illustrate, consider solving the equation *x<sup>2</sup> - 100000x + 1 = 0* with the quadratic formula. Since the operands in the expression *-b + sqrt(b<sup>2</sup> - 4)* are nearly equal in magnitude, you can instead compute the root *r<sub>1</sub> = -b + sqrt(b<sup>2</sup> - 4)*, and then obtain *r<sub>2</sub> = 1/r<sub>1</sub>*, since for any quadratic equation, ax2 + bx + c = 0, the roots satisfy *r<sub>1</sub>r<sub>2</sub> = c/a*.

Smearing can occur in even more subtle ways. Suppose a library naively computes *e<sup>x</sup>* by the formula *1 + x + x<sup>2</sup>/2 + x<sup>3</sup>/3! + ...*. This works fine for positive *x*, but consider what happens when *x* is a large negative number. The even-powered terms result in large positive numbers, and subtracting the odd-powered magnitudes will not even affect the result. The problem here is that the roundoff in the large, positive terms is in a digit position of much greater significance than the true answer. The answer diverges toward positive infinity! The solution here is also simple: for negative *x*, compute *e<sup>x</sup> = 1/e<sup>|x|</sup>*.

涂抹可能以更微妙的方式发生。假设一个程序库天真地计算*e<sup>x</sup>* 根据公式*1 + x + x<sup>2</sup>/2 + x<sup>3</sup>/3! + ...*. 这对正数 *x* 很有效，但考虑一下当 *x* 是一个很大的负数时会发生什么。偶数项的结果是大正数，减去奇数项的大小甚至不会影响结果。这里的问题是，大正数项的舍入位置比真实答案的数字位置重要得多。答案向正无穷发散！这里的解决方法也很简单：对于负 *x*，计算*e<sup>x</sup> = 1/e<sup>|x|</sup>*.

It should go without saying that you shouldn't use floating-point numbers for financial applications — that's what decimal classes in languages like Python and C# are for. Floating-point numbers are intended for efficient scientific computation. But efficiency is worthless without accuracy, so remember the source of rounding errors and code accordingly!

不言而喻，您不应该在金融应用中使用浮点数--那是 Python 和 C# 等语言中的小数类的用途。浮点数用于高效的科学计算。但是，如果没有准确性，效率就毫无价值，所以请记住四舍五入错误的来源，并据此编写代码！

By [Chuck Allison](http://programmer.97things.oreilly.com/wiki/index.php/Chuck_Allison)