## Cheatsheet

### 符号说明

| 概率             | 集合                    | 程序设计 | 英文表达                   | 中文表达                     |
| ---------------- | ----------------------- | -------- | -------------------------- | ---------------------------- |
| $\land$、P(A, B) | $\cap$                  | &        | join \| and \| conjunction | 交 \| 与 \| 且 \| 联合(概率) |
| $\lor$           | $\cup$                  | \|       | union \| or                | 并 \| 或                     |
| $\lnot$          | $\lnot$ 、 - 、~、$S^c$ | !        | not                        | 补 \| 非                     |



### 概率计算3公理

* $$\tag{1.1} \mathit{0 \le P(A) \le1}$$

* $$\tag{1.2}\mathit{P(确定命题)  = 1} $$
* $$\tag{1.3}\mathit{P(A\ or\ B) = P(A) + P(B) } \quad A与B互斥$$

公理3表明任何事件集合的信念等于其非相交部分信念之和。因为对任意事件A，都可以写成 $(A \land B)$ 与 $(A \land \lnot B)$ 之和，将他们组合起来就是

$$\tag{1.4}\mathit{P(A) = P(A, B) + P(A, \lnot B)}$$ 

<div class="alert alert-success" role="alert">
  <h4 class="alert-heading">(1.4)证明:</h4>
    <p>因为$B$ 与 $\lnot B$ 互斥，所以 $(A \land B)$ 与 $(A \land \lnot B)$ 也是互斥的。根据公理3，$\mathit{P((A \land B) \lor (A \land \lnot B)) = P(A \land B) + P(A \land \lnot B)}$，这里稍微用一下集合的分配律$(A \land B) \lor (A \land C) \iff A \land (B \lor C)$，即可得到</p>
    <p>$\mathit{P(A \land (B \lor \lnot B)) = P(A, B) + P(A, \lnot B)}$</p>
	<p>因为 $B \lor \lnot B \iff 1$ (排中律)，$A \land 1 \iff A$(同一律)，所以 $\mathit{P(A) = P(A, B) + P(A, \lnot B)} \quad \blacksquare$</p>
</div>


### 全概率定律

上面是$B$和$\lnot B$两种情况。更一般地，我们可以将事件分割成任意多个不重不漏的部分，即$B_i, i=1, 2, \dots, n$，那么$P(A)$可以通过计算$P(A, B_i)$之和求出。

$$\tag{1.5}\mathit{P(A) = \sum_i P(A, B_i)}$$

### 公式1.7

$$\tag{1.7}\mathit{P(A) + P(\lnot A) = 1}$$

<div class="alert alert-success" role="alert">
  <h4 class="alert-heading">(1.7)证明:</h4>
    <p>$\because A$ 与 $\lnot A$ 互斥，根据公理3</p>
    <p>$\therefore \mathit{P(A) + P(\lnot A) = P(A \lor \lnot A)}$</p>
    <p>$\because \mathit{A \lor \lnot A = \Omega}$</p>
	<p>$\therefore \mathit{P(A) + P(\lnot A) = P(A \lor \lnot A) = P(\Omega) = 1}\quad \blacksquare$</p>
</div>
