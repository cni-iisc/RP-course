---
title: "Probability Function"
author: "Parimal Parag"
format:
  html:
    mathjax: 
      fonts: STIX-Web
    toc: true
    number-sections: false
    toc-depth: 2
---

{{< video https://www.youtube.com/watch?v=dQw4w9WgXcQ >}}

# Indicator Functions

::: defn
**Definition 1** (Indicator functions). Consider a random experiment
over an outcome space $\Omega$ and an event space $\mathcal{F}$. The
indicator of an event $B \in \mathcal{F}$ is denoted by
$$\Bbb{1}_{B}(\omega) = 
\begin{cases}
1, & \omega \in B,\\
0, & \omega \notin B.
\end{cases}$$
:::

::::: shaded
::: exmp
**Example 2**. Consider a roll of dice that has an outcome space
$\Omega = [6]$ and event space $\mathcal{F}= \mathcal{P}(\Omega)$. For
an event $O \triangleq \left\{1,3,5\right\}$ that represents odd
outcomes for dice roll, we observe that $\Bbb{1}_{O}(1) = 1$ and
$\Bbb{1}_{O}(2) = 0$.
:::

::: exmp
**Example 3**. Consider $N$ trials of a random experiment over outcome
space $\Omega$ and the event space $\mathcal{F}$. Let
$\omega_n \in \Omega$ denote the outcome of the experiment of the $n$th
trial. For each event $B \in \mathcal{F}$, we define an indicator
function $$\Bbb{1}_{B}(\omega_n) = 
\begin{cases}
1, & \omega_n \in B,\\
0, & \omega_n \notin B.
\end{cases}$$ For any event $B \in \mathcal{F}$, the number of times the
event $B$ occurs in $N$ trials is denoted by
$N(B) = \sum_{n=1}^N\Bbb{1}_{B}(\omega_n)$. We denote the relative frequency
of an event $A$ in $N$ trials by $\frac{N(B)}{N}$.
:::
:::::

::: defn
**Definition 4** (Disjoint events). Let $(\Omega,\mathcal{F})$ be a pair
of sample and event space, and a sequence of events
$A \in \mathcal{F}^\mathbb{N}$. The sequence is **mutually disjoint** if
$A_n\cap A_m = \emptyset$ for any $m\neq n \in \mathbb{N}$. If
$\cup_{n \in \mathbb{N}}A_n = \Omega$, then $A$ is a **partition** of
sample space $\Omega$.
:::

::::: tcolorbox
::: exerc
**Exercise 5**. Consider the sample space
$\Omega = \left\{H,T\right\}^\mathbb{N}$ and event space
$\mathcal{F}= \sigma(A_n: n \in \mathbb{N})$ where
$A_n \triangleq \left\{\omega \in \Omega: \omega_i = H \text{ for some } i \in [n]\right\}$.
Construct a sequence of non-trivial disjoint events.
:::

::: exerc
**Exercise 6**. Let $(\Omega,\mathcal{F})$ be a pair of sample and event
space. For any sequence of events $A \in \mathcal{F}^\mathbb{N}$, show
that

1.  $\Bbb{1}_{\cap_{n\in\mathbb{N}}A_n}(\omega) = \prod_{n \in \mathbb{N}}\Bbb{1}_{A_n}(\omega)$,

2.  $\Bbb{1}_{\cup_{n \in \mathbb{N}}A_n}(\omega) = \sum_{n \in \mathbb{N}}\Bbb{1}_{A_n}(\omega)$
    if the sequence $A$ is mutually disjoint.
:::
:::::

:::: shaded
::: exmp
**Example 7**. We observe the following properties of the relative
frequency.

1.  For all events $B \in \mathcal{F}$, we have
    $0 \leqslant\frac{N(B)}{N} \leqslant 1$. This follows from the fact
    that $0 \leqslant N(B) \leqslant N$ for any event
    $B \in \mathcal{F}$.

2.  Let $A\in\mathcal{F}^\mathbb{N}$ be a sequence of mutually disjoint
    events, then
    $\frac{N(\cup_{i \in \mathbb{N}}A_i)}{N} =  \sum_{i\in \mathbb{N}}\frac{N(A_i)}{N}$.
    This follows from the fact that for mutually disjoint event sequence
    $A$, we have
    $$\Bbb{1}_{\cup_{i \in \mathbb{N}}A_i}(\omega_n) = \sum_{i \in \mathbb{N}}\Bbb{1}_{A_i}(\omega_n).$$

3.  For the certain event $\Omega$, we have $\frac{N(\Omega)}{N} = 1$.
    This follows from the fact that $N(\Omega) = N$.

Since the relative frequency is positive and bounded, it may converge to
a real number as $N$ grows very large, and the limit
$\lim_{N \to \infty}\frac{N(B)}{N}$ may exist.
:::
::::

# Probability axioms

Inspired by the relative frequency, we list the following axioms for a
probability function $P: \mathcal{F}\to [0,1]$.

::: axiom
**Axiom 8** (Axioms of probability). We define a probability measure on
sample space $\Omega$ and event space $\mathcal{F}$ by a function
$P: \mathcal{F}\to [0,1]$ which satisfies the following axioms.

1.  For all events $B \in \mathcal{F}$, we have $P(B) \geqslant 0$.

2.  For an infinite sequence $A \in \mathcal{F}^\mathbb{N}$ of mutually
    disjoint events, we have
    $P(\cup_{i \in \mathbb{N}}A_i) = \sum_{i \in \mathbb{N}}P(A_i)$.

3.  $P(\Omega) = 1$.
:::

::: defn
**Definition 9** (Probability space). A sample space $\Omega$, an event
space $\mathcal{F}\subseteq \mathcal{P}(\Omega)$, and a probability
measure $P: \mathcal{F}\to [0,1]$, together define a probability space
$(\Omega,\mathcal{F},P)$.
:::

# Properties of Probability

::: thm
**Theorem 10**. *For any probability space $(\Omega, \mathcal{F}, P)$,
we have the following properties of probability measure.*

1.  *$P(\emptyset) = 0$.*

2.  *For mutually disjoint events $A\in \mathcal{F}^n$, we have
    $P(\cup_{i=1}^nA_i) = \sum_{i=1}^nP(A_i)$.*

3.  *If events $A, B \in \mathcal{F}$ such that $A \subseteq B$, then
    $P(A) \leqslant P(B)$.*

4.  *For any events $A, B \in \mathcal{F}$, we have
    $P(A \cup B) = P(A) + P(B) - P(A \cap B)$.*

5.  *For a sequence of events $A \in \mathcal{F}^\mathbb{N})$ such that
    $\lim_nA_n$ exists, we have
    $P(\lim_{n \to \infty}A_n) = \lim_{n \to \infty}P(A_n)$.*
:::

::: proof
We consider the probability space $(\Omega, \mathcal{F}, P)$.

1.  We take disjoint events $E\in\mathcal{F}^\mathbb{N}$ where
    $E_1 = \Omega$ and $E_i = \emptyset$ for $i \geqslant 2$. It follows
    that $\cup_{i \in \mathbb{N}}E_i = \Omega$ and $E$ is a collection
    of mutually disjoint events. From the countable additivity axiom of
    probability, it follows that
    $$P(\Omega) = P(\Omega) + \sum_{i \geqslant 2}P(E_i).$$ Since
    $P(E_i) \geqslant 0$, it implies that $P(\emptyset) = 0$.

2.  We see that finite additivity follows from the countable additivity.
    We consider disjoint events $A_1, \dots, A_n$, and take
    $A_{i} = \emptyset$ for all $i > n$. It follows that the sequence of
    sets $A\in\mathcal{F}^\mathbb{N}$ is mutually disjoint, and since
    $P(\emptyset) = 0$, it follows that
    $$P(\cup_{i=1}^nA_i) = P(\cup_{i \in \mathbb{N}}A_i) = \sum_{i=1}^nP(A_i) + \sum_{i > n}P(\emptyset) =  \sum_{i=1}^nP(A_i).$$

3.  For events $A, B \in \mathcal{F}$ such that $A \subseteq B$, we can
    take disjoint events $E_1 = A$ and $E_2 = B\setminus A$. From
    closure under complements and intersection, it follows that
    $E_2 \in \mathcal{F}$. From non-negativity of probability, we have
    $P(E_2) \geqslant 0$. Finally, the result follows from finite
    additivity of disjoint events
    $$P(B) = P(E_1 \cup E_2)= P(E_1) + P(E_2) \geqslant P(A).$$

4.  For any two events $A, B \in \mathcal{F}$, we can write the
    following events as disjoint unions

    $$
    \begin{align*}
        &A = (A \setminus B) \cup (A \cap B), \\
        &B = (B \setminus A) \cup (A \cap B), \\
        &A \cup B = (A \setminus B) \cup (A \cap B) \cup (B \setminus A).
    \end{align*}
    $$

    The result follows from the finite additivity of probability of
    disjoint events.

5.  To show the continuity of probability in events, we first need to
    understand the limits of events. We show the continuity of
    probability in the next section.

 ◻
:::

:::::: shaded
:::: exmp
**Example 11**. Consider a single coin tosse with the sample space
$\Omega = \left\{H,T\right\}$, an event space
$\mathcal{F}= \mathcal{P}(\Omega)$. The probability measure
$P:\mathcal{F}\to[0,1]$ is defined as

$$
\begin{align*}
    &P(\emptyset) = 0, \quad
    &&P(\{H\}) = p, \quad
    &&P(\{T\}) = 1 - p, \quad
    &&P(\{H, T\}) = 1.
\end{align*}
$$

Can you verify that $P$ is a probability function?
::::

::: exmp
**Example 12**. Consider $N$ coin tosses with the sample space
$\Omega = \left\{H,T\right\}^{[N]}$, an event space
$\mathcal{F}= \mathcal{P}(\Omega)$. For each outcome
$\omega \in \Omega$, we define the number of heads as
$N_H(\omega) \triangleq \sum_{n\in[N]}\Bbb{1}_{\left\{H\right\}}(\omega_n)$
and the number of tails as $N_T(\omega) \triangleq N - N_H(\omega)$. The
probability measure $P:\mathcal{F}\to[0,1]$ is defined for each event
$A \in \mathcal{F}$ as
$$P(A) \triangleq \sum_{\omega \in A}p^{N_H(\omega)}(1-p)^{N_T(\omega)}.$$
Can you verify that $P$ is a probability function?
:::
::::::

# Limits of Sets

::: defn
**Definition 13** (Limits of monotonic sets). For a sequence of
non-decreasing sets $(A_n: n \in \mathbb{N})$, we can define the limit
as $$\lim_{n \to \infty}A_n \triangleq \cup_{n \in \mathbb{N}}A_n.$$
Similarly, for a sequence of non-increasing sets
$(A_n: n \in \mathbb{N})$, we can define the limit as
$$\lim_{n \to \infty}A_n \triangleq \cap_{n \in \mathbb{N}}A_n.$$
:::

::::: shaded
:::: exmp
**Example 14** (Monotone sets). Consider a monotonically increasing
sequence $a \in \mathbb{R}^\mathbb{N}$ defined as
$a_n \triangleq -\frac{1}{n}$ for all $n \in \mathbb{N}$, which
converges to the limit $0$. We consider monotone sequence of sets
$A, B \in \mathcal{B}(\mathbb{R})^\mathbb{N}$ define as
$A_n \triangleq [-2, -\frac{1}{n}]$ and
$B_n \triangleq [-2, \frac{1}{n}]$ for all $n \in \mathbb{N}$, which are
monotonically increasing and decreasing respectively. We can verify the
following limits

$$
\begin{align*}
    &\lim_n A_n = \cup_{n \in \mathbb{N}} A_n = [-2, 0), \\
    &\lim_n B_n = \cap_{n \in \mathbb{N}} B_n = [-2, 0].
\end{align*}
$$

::::
:::::

:::: defn
**Definition 15** (Limits of sets). For a sequence of sets
$(A_n: n \in \mathbb{N})$, we can define the limit superior and limit
inferior of this sequence of sets as

$$
\begin{align*}
    &\limsup_{n \to \infty} A_n \triangleq \cap_{n \in \mathbb{N}} \cup_{m \ge n} A_m = \lim_{n \to \infty} \cup_{m \ge n} A_m, \\
    &\liminf_{n \to \infty} A_n \triangleq \cup_{n \in \mathbb{N}} \cap_{m \ge n} A_m = \lim_{n \to \infty} \cap_{m \ge n} A_m.
\end{align*}
$$

::::

::: lem
**Lemma 16**. *For a sequence of sets $(A_n: n \in \mathbb{N})$, we have
$\liminf_{n \to \infty}A_n \subseteq \limsup_{n \to \infty}A_n$.*
:::

::: proof
For each $n \in \mathbb{N}$, we define
$E_n \triangleq \cup_{m \geqslant n}A_m$ and
$F_n \triangleq \cap_{m \geqslant n}A_m$. Consider a fixed $n$, then
$F_1, F_2, \dots, F_n \subseteq A_n$, and $F_m \subseteq A_m$ for all
$m \geqslant n$. Therefore, we can write
$\cup_{n \in \mathbb{N}}F_n \subseteq \cup_{m \geqslant n}A_m$ for each
$n \in \mathbb{N}$, and hence the result follows. ◻
:::

::: defn
**Definition 17**. If the limit superior and limit inferior of any
sequence of sets $(A_n: n \in \mathbb{N})$ are equal, then the sequence
of sets has a limit $A_\infty$, which is defined as
$$A_\infty \triangleq \lim_{n \to \infty}A_n = \limsup_{n \to \infty}A_n = \liminf_{n \to \infty}A_n.$$
:::

::::: shaded
:::: exmp
**Example 18** (Sequence of sets with different limits). We consider
sequence of sets $(A_n = [-2, (-1)^n + \frac{1}{n}]: n \in \mathbb{N})$.
It follows that $F_n = \cap_{m \geqslant n}A_m = [-2, -1]$ and
$$E_n = \cup_{m \geqslant n}A_m = 
\begin{cases}
[-2, 1+ \frac{1}{n+1}], & n \text{ odd},\\
[-2, 1 + \frac{1}{n}], &n \text{ even}.
\end{cases}$$ We can verify the following limits

$$
\begin{align*}
    &\liminf_n A_n = \cup_{n \in \mathbb{N}} F_n = [-2, -1], \\
    &\limsup_n A_n = \cap_{n \in \mathbb{N}} E_n = [-2, 1].
\end{align*}
$$

::::
:::::

## Proof of continuity of probability

**Continuity for increasing sets.** Let
$(A_n \in \mathcal{F}: n \in \mathbb{N})$ be a non-decreasing sequence
of events, then $\lim_{n \to \infty}A_n = \cup_{n\in \mathbb{N}}A_n$.
This implies that $(P(A_n): n \in \mathbb{N})$ is a non-negative
non-decreasing bounded sequence, and hence has a limit. It remains to
show that $\lim_{n \to \infty}P(A_n) = P(\cup_{n \in \mathbb{N}}A_n)$.
To this end, we observe that
$(A_1, A_2\setminus A_1, \dots, A_n\setminus A_{n-1})$ is a partition of
the event $A_n$, and $P(A_i\setminus A_{i-1}) = P(A_i) - P(A_{i-1})$ for
each $i \in \mathbb{N}$. From finite additivity of $P$ for mutually
disjoint events, we can write for each $n \in \mathbb{N}$
$$P(A_n) = P(A_1) + \sum_{i=1}^{n-1}P(A_{i+1}\setminus A_i) = P(A_1) + \sum_{i=1}^{n-1}(P(A_{i+1}) -P(A_i)).$$
From $\sigma$-additivity of $P$ for sequence of mutually disjoint
events, we can write for
$\lim_{n \to \infty}A_n = \cup_{n \in \mathbb{N}}A_n$,
$$P(\cup_{n \in \mathbb{N}}A_n) = P(A_1) + \sum_{i \in \mathbb{N}}(P(A_{i+1}) -P(A_i)) = P(A_1) + \lim_{n \to \infty}\sum_{i=1}^{n-1}(P(A_{i+1}) -P(A_i)) = \lim_{n \to \infty}P(A_n).$$

**Continuity for decreasing sets.** Similarly, for a non-increasing
sequence of sets $(B_n \in \mathcal{F}: n \in \mathbb{N})$, we can find
the non-decreasing sequence of sets
$(B^c_n \in \mathcal{F}: n \in \mathbb{N})$. By the first part, we have
$$P(\lim_{n \to \infty}B_n) = P(\cap_{n \in \mathbb{N}}B_n) = 1 - P(\cup_{n \in \mathbb{N}}B^c_n)  = 1 - P(\lim_{n \to \infty}B_n^c) = 1 - \lim_{n\to \infty}P(B_n^c) = \lim_{n \to \infty}P(B_n).$$

**Continuity for general sequence of sets.** We can similarly prove the
general result for a sequence of sets
$(A_n \in \mathcal{F}: n \in \mathbb{N})$ such that the limits
$\lim_{n}A_n$ exists. We can define non-increasing sequences of sets
$(E_n = \cup_{m \geqslant n}A_m \in \mathcal{F}: n \in \mathbb{N})$ and
non-decreasing sequences of sets
$(F_n = \cap_{m \geqslant n}A_m \in \mathcal{F}: n \in \mathbb{N})$.
From the continuity of probability for the monotonic sets, we have

$$
\begin{align*}
    &P(\limsup_n A_n) = P(\cap_{n \in \mathbb{N}} E_n) = \lim_{n \to \infty} P(E_n), \\
    &P(\liminf_n A_n) = P(\cup_{n \in \mathbb{N}} F_n) = \lim_{n \to \infty} P(F_n).
\end{align*}
$$

From the definition of two sequences of sets, we obtain

$$
\begin{align*}
    &P(E_n) \ge \sup_{m \ge n} P(A_m), \\
    &P(F_n) \le \inf_{m \ge n} P(A_m).
\end{align*}
$$

Therefore taking limsup and liminf, we obtain
$$\lim_{n\to\infty}P(E_n) = \limsup_{n \in \mathbb{N}} P(A_n) \geqslant\inf_{n \in \mathbb{N}}\sup_{m \geqslant n}P(A_m) \geqslant\sup_{n \in \mathbb{N}}\inf_{m \geqslant n}P(A_m) \geqslant\liminf_{n \in \mathbb{N}}P(A_n)
= \lim_{n\to\infty}P(F_n).$$ Since
$P(\lim_n A_n) = \lim_nP(E_n) = \lim_{n}P(F_n)$ exists, the result
follows.



