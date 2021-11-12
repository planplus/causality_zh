## 第一章公式推导

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

### 条件独立关系的性质

* 对称性：$\mathit{(X {\perp\!\!\!\perp} Y \mid Z) \implies (X {\perp\!\!\!\perp} Y \mid Z)}$

<div class="alert alert-success" role="alert">
  <h4 class="alert-heading">证明:</h4>
    <p>$$\tag{1}\mathit{(X {\perp\!\!\!\perp} Y \mid Z) \iff P(x \mid y,z)=P(x \mid z)}$$</p>
    <p>$$\tag{2}\mathit{(Y {\perp\!\!\!\perp} X \mid Z) \iff P(y \mid x,z)=P(y \mid z)}$$</p>
	<p>利用乘法公式，1式和2式可以改写为：</p>
    <p>$$\tag{3}\mathit{\frac {P(x,y,z)} {\boxed{P(y,z)}} = \frac {\boxed{P(x,z)}} {P(z)}}$$</p>
    <p>$$\tag{4}\mathit{\frac {P(x,y,z)} {P(x,z)} = \frac {P(y,z)} {P(z)}}$$</p>
    <p>
        3式方框标注部分位置对换一下，就是4式。$\blacksquare$
    </p>
</div>

* 分解性：$\mathit{(X {\perp\!\!\!\perp} YW \mid Z) \implies (X {\perp\!\!\!\perp} Y \mid Z)}$

<div class="alert alert-success" role="alert">
  <h4 class="alert-heading">证明:</h4>
    <p>$$\tag{1}\mathit{(X {\perp\!\!\!\perp} YW \mid Z) \iff P(x \mid y,z,w)=P(x \mid z)}$$</p>
    <p>$$\tag{2}\mathit{(X {\perp\!\!\!\perp} Y \mid Z) \iff P(x \mid y,z)=P(x \mid z)}$$</p>
	<p>利用乘法公式，1式和2式可以改写为：</p>
    <p>$$\tag{3}\mathit{\frac {P(x,y,z,w)} {\boxed{P(y,z,w)}} = \frac {\boxed{P(x,z)}} {P(z)}}$$</p>
    <p>$$\tag{4}\mathit{\frac {P(x,y,z)} {P(y,z)} = \frac {P(x,z)} {P(z)}}$$</p>
    <p>3式方框标注部分位置对换一下，得：
        $$\tag{5}\mathit{\frac {P(x,y,z,w)} {P(x,z)} = \frac {P(y,z,w)} {P(z)}}$$
    </p>
    <p>
        两边对$W$进行边缘化（将集合$W$中的所有值累加起来）
        $$\tag{6}\mathit{\frac {\displaystyle\sum_{W} P(x,y,z,w)} {P(x,z)} = \frac {\displaystyle\sum_{W} P(y,z,w)} {P(z)}}$$
    </p>
    <p>
        根据全概率公式，得：
        $$\tag{7}\mathit{\frac {P(x,y,z)} {\boxed{P(x,z)}} = \frac {\boxed{P(y,z)}} {P(z)}}$$
    </p>
    <p>
        将7式方框部分交换位置，即可得到4式。$\blacksquare$
    </p>
</div>

* 弱连性：$\mathit{(X {\perp\!\!\!\perp} Y W\mid Z) \implies (X {\perp\!\!\!\perp} Y \mid ZW)}$

<div class="alert alert-success" role="alert">
  <h4 class="alert-heading">证明:</h4>
    <p>$$\tag{1}\mathit{(X {\perp\!\!\!\perp} YW \mid Z) \iff P(x \mid y,z,w)=P(x \mid z)}$$</p>
    <p>$$\tag{2}\mathit{(X {\perp\!\!\!\perp} Y \mid ZW) \iff P(x \mid y,z,w)=P(x \mid z,w)}$$</p>
	<p>利用乘法公式，1式和2式可以改写为：</p>
    <p>$$\tag{3}\mathit{\frac {P(x,y,z,w)} {\boxed{P(y,z,w)}} = \frac {\boxed{P(x,z)}} {P(z)}}$$</p>
    <p>$$\tag{4}\mathit{\frac {P(x,y,z,w)} {P(y,z,w)} = \frac {P(x,z,w)} {P(z,w)}}$$</p>
    <p>3式方框标注部分位置对换一下，得：
        $$\tag{5}\mathit{\frac {P(x,y,z,w)} {P(x,z)} = \frac {P(y,z,w)} {P(z)}}$$
    </p>
    <p>
        两边对$Y$进行边缘化（将集合$Y$中的所有值累加起来）
        $$\tag{6}\mathit{\frac {\displaystyle\sum_{Y} P(x,y,z,w)} {P(x,z)} = \frac {\displaystyle\sum_{Y} P(y,z,w)} {P(z)}}$$
    </p>
    <p>
        根据全概率公式，得：
        $$\tag{7}\mathit{\frac {P(x,z,w)} {\boxed{P(x,z)}} = \frac {\boxed{P(z,w)}} {P(z)}}$$
    </p>
    <p>
        将7式方框部分交换位置，并于3式联立，即可得到:
        $$\tag{8}\mathit{\boxed{\frac {P(x,z,w)} {P(z,w)}} = \frac {P(x,z)} {P(z)}} = \boxed{\frac {P(x,y,z,w)} {P(y,z,w)}}$$
        其中方框部分就是4式。$\blacksquare$
    </p>
</div>

* 缩并性：$\mathit{(X {\perp\!\!\!\perp} Y \mid Z) \& (X {\perp\!\!\!\perp} W \mid ZY) \implies (X {\perp\!\!\!\perp} YW \mid Z)}$

<div class="alert alert-success" role="alert">
  <h4 class="alert-heading">证明:</h4>
    <p>
        $$\begin{cases} \mathit{(X {\perp\!\!\!\perp} Y \mid Z) \iff P(x \mid y,z)=P(x \mid z)}  &\text{(1)}\\ \mathit{(X {\perp\!\!\!\perp} W \mid ZY) \iff P(x \mid y,z,w)=P(x \mid y,z)} &\text{(2)} \end{cases}$$
    </p>
    <p>要证明：$$\tag{3}\mathit{(X {\perp\!\!\!\perp} YW \mid Z) \iff P(x \mid y,z,w)=P(x \mid z)}$$</p>
	<p>1式左边和2式右边相同，两式一合并：</p>
    <p>$$\tag{4}\mathit{P(x \mid y,z,w) = P(x \mid z)}$$</p>
    <p>4式就是要证明得3式。$\blacksquare$</p>
</div>

* 相交性：$\mathit{(X {\perp\!\!\!\perp} W \mid ZY) \& (X {\perp\!\!\!\perp} Y \mid ZW) \implies (X {\perp\!\!\!\perp} YW \mid Z)}$

<div class="alert alert-success" role="alert">
  <h4 class="alert-heading">证明:</h4>
    <p>
        $$\begin{cases} \mathit{(X {\perp\!\!\!\perp} W \mid ZY) \iff P(x \mid y,z,w)=P(x \mid y,z)}  &\text{(1)}\\ \mathit{(X {\perp\!\!\!\perp} Y \mid ZW) \iff P(x \mid y,z,w)=P(x \mid z,w)} &\text{(2)} \end{cases}$$
    </p>
    <p>要证明：$$\tag{3}\mathit{(X {\perp\!\!\!\perp} YW \mid Z) \iff P(x \mid y,z,w)=P(x \mid z)}$$</p>
	<p>1式2式左边相同，两式一合并：</p>
    <p>$$\tag{4}\mathit{P(x \mid y,z) = P(x \mid z,w)}$$</p>
    <p>利用乘法公式，4式可写做：$$\tag{5}\mathit{\frac {P(x,y,z)} {\boxed{P(y,z)}} = \frac {\boxed{P(x,z,w)}} {P(z,w)}}$$</p>
    <p>交换5式方框部分，并对$Y$进行边缘化：
        $$\tag{6}\mathit{\frac {\displaystyle\sum_{Y} P(x,y,z)} {P(x,z,w)} = \frac {\displaystyle\sum_{Y} P(y,z)} {P(z,w)}}$$
    </p>
    <p>根据全概率公式，得：
        $$\tag{7}\mathit{\frac {P(x,z)} {\boxed{P(x,z,w)}} = \frac {\boxed{P(z)}} {P(z,w)}}$$
    </p>
    <p>交换方框部分，得
        $$\tag{8}\mathit{\frac {P(x,z)} {P(z)} = \frac {P(x,z,w)} {P(z,w)}}$$
    </p>
    <p>将8式写成条件概率
        $$\tag{9}\mathit{P(x \mid z)=P(x \mid z,w)}$$
    </p>
    <p>9式和2式一合并，即可得：$\mathit{P(x \mid y,z,w)=P(x \mid z)}$，这就是我们要证明的3式。$\blacksquare$</p>
</div>

