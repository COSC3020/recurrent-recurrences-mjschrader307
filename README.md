# Recurrent Recurrences

Give big $\Theta$ bounds for the following recurrence relations.

1.
$$ T(n) =
    \begin{cases}
        1 & n \leq 1\\
        T\left(\frac{n}{13}\right) + 5 & n > 1
    \end{cases}
$$

2.
$$ T(n) =
    \begin{cases}
        1 & n \leq 1\\
        13 T\left(\frac{n}{13}\right) + 5 & n > 1
    \end{cases}
$$

3.
$$ T(n) =
    \begin{cases}
        1 & n \leq 1\\
        13 T\left(\frac{n}{13}\right) + 2n & n > 1
    \end{cases}
$$

---

Answers:

1.

$$
T(n) = T(\frac{n}{13}) + 5\\
= T(\frac{n}{169}) + 5 + 5 \\
= T(\frac{n}{169}) + 10 \\
... \\
= T(n \cdot 13^{-i}) + 5i
$$

Let $i = \log_{13}(n)$:

$$
T(n \cdot 13^{-\log_{13}(n)}) + 5\log_{13}(n) \\
= T(n \cdot \frac{1}{n}) + 5\log_{13}(n) \\
= 5 \log_{13}(n) + T(1) \\
= 5 \log_{13}(n) + 1
$$

$5\log_{13}(n) \in \Theta(\log(n))$

2.

$$
T(n) = 13T(\frac{n}{13}) + 5 \\
= 13(13T(\frac{n}{169}) + \frac{5}{13}) + 5 \\
= 13T(\frac{n}{169}) + 10 \\
... \\
= 13^iT(n \cdot 13^{-i}) + 5i
$$

Let $i = \log_{13}(n)$:

$$
13^{\log_{13}(n)}T(n \cdot 13^{-\log_{13}(n)}) + 5\log_{13}(n) \\
= n \cdot T(n \cdot \frac{1}{n}) + 5\log_{13}(n) \\
= 5 \log_{13}(n) + nT(1) \\
= 5 \log_{13}(n) + n
$$

$5\log_{13}(n) + n \in \Theta(n)$

because the linear term is the dominant one.

3.

$$
T(n) = 13T(\frac{n}{13}) + 2n \\
= 13(13T(\frac{n}{169}) + \frac{2}{13}n) + 2n \\
= 169T(\frac{n}{169}) + 4n \\
... \\
= 13^iT(n \cdot 13^{-i}) + 2in
$$

Let $i = \log_{13}(n)$:

$$
13^{\log_{13}(n)}T(n \cdot 13^{-\log_{13}(n)}) + 2n\log_{13}(n) \\
= nT(n \cdot \frac{1}{n}) + 2n\log_{13}(n) \\
= nT(1) + 2n\log_{13}(n) \\
= 2n\log{13}(n) + n
$$

$2n\log_{13}(n) + n \in \Theta(n\log(n))$

because the linearithmic term is the dominant one.

---

**I certify that I have listed all sources used to complete this exercise, including the use
of any Large Language Models. All of the work is my own, except where stated
otherwise. I am aware that plagiarism carries severe penalties and that if plagiarism is
suspected, charges may be filed against me without prior notice.**