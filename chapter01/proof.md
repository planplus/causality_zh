## 重要公式证明

### 符号说明

$\mathit{V = \{V_1, V_2, \dots\}}$ 表示变量的有限集合。

$\mathit{X, Y, Z, W}$这种大写字母表示$\mathit{V}$中变量的子集。可以认为$\mathit{X, Y, Z, W \in V}$

$\mathit{x, y, z, w}$这种小写字母表示$\mathit{X, Y, Z, W}$集合中的任一成员。可以认为$\mathit{\forall x \in X}$

### 条件独立关系的性质



#### 对称性：$\mathit{(X {\perp\!\!\!\perp} Y \mid Z) \implies (X {\perp\!\!\!\perp} Y \mid Z)}$

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
<p></p>

#### 分解性：$\mathit{(X {\perp\!\!\!\perp} YW \mid Z) \implies (X {\perp\!\!\!\perp} Y \mid Z)}$

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
<p></p>

<div class="alert alert-success" role="alert">
  <h4 class="alert-heading">证明:</h4>
    <p>$$\tag{1}\mathit{(X {\perp\!\!\!\perp} YW \mid Z) \iff P(x \mid y,z,w)=P(x \mid z)}$$</p>
    <p>$$\tag{2}\mathit{(X {\perp\!\!\!\perp} Y \mid Z) \iff P(x \mid y,z)=P(x \mid z)}$$</p>
	<p>根据公式(1.11)：$\mathit{P(A \mid K)} = \displaystyle\mathit{\sum_{i} P(A \mid B_i, K)P(B_i \mid K)}$</p>
    <p>$$\tag{3}\mathit{P(x \mid y,z) = \sum_{w \in W} P(x \mid y,z,w)P(w \mid y,z)}$$</p>
    <p>根据1式，$\mathit{P(x \mid y,z,w)=P(x \mid z)}$，带入3式得：
        $$\tag{4}\mathit{P(x \mid y,z) = \sum_{w \in W} P(x \mid z)P(w \mid y,z) = P(x \mid z) \sum_{w \in W}P(w \mid y,z)}$$
    </p>
    <p>
        因为对任意$\mathit{\forall w \in W}$的情况都取到了，所以$\displaystyle\mathit{\sum_{w \in W}P(w \mid y,z)}$求和的结果就是1：
        $$\therefore \tag{5}\mathit{P(x \mid y,z) = P(x \mid z)} \quad \blacksquare$$
    </p>
</div>
<p></p>

#### 弱连性：$\mathit{(X {\perp\!\!\!\perp} Y W\mid Z) \implies (X {\perp\!\!\!\perp} Y \mid ZW)}$

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
<p></p>

<div class="alert alert-success" role="alert">
  <h4 class="alert-heading">证明:</h4>
    <p>$$\tag{1}\mathit{(X {\perp\!\!\!\perp} YW \mid Z) \iff P(x \mid y,z,w)=P(x \mid z)}$$</p>
    <p>$$\tag{2}\mathit{(X {\perp\!\!\!\perp} Y \mid ZW) \iff P(x \mid y,z,w)=P(x \mid z,w)}$$</p>
	<p>根据公式(1.11)：</p>
    <p>$$\tag{3}\mathit{P(x \mid z,w) = \sum_{y \in Y} P(x \mid y,z,w)P(y \mid z,w)}$$</p>
    <p>根据1式$\mathit{P(x \mid y,z,w)=P(x \mid z)}$，带入3式得：
        $$\tag{4}\mathit{P(x \mid z,w) = \sum_{y \in Y} P(x \mid z)P(y \mid z,w) = P(x \mid z) \sum_{y \in Y} P(y \mid z,w)}$$
    </p>
    <p>
        因为对任意$\mathit{\forall y \in Y}$的情况都取到了，所以$\displaystyle\mathit{\sum_{y \in Y} {P(y \mid z,w)}} = 1$，
        $$\therefore \mathit{P(x \mid z,w) = P(x \mid z) = P(x \mid y,z,w)} \quad \blacksquare$$
    </p>
</div>
<p></p>

#### 缩并性：$\mathit{(X {\perp\!\!\!\perp} Y \mid Z) \& (X {\perp\!\!\!\perp} W \mid ZY) \implies (X {\perp\!\!\!\perp} YW \mid Z)}$

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
<p></p>

#### 相交性：$\mathit{(X {\perp\!\!\!\perp} W \mid ZY) \& (X {\perp\!\!\!\perp} Y \mid ZW) \implies (X {\perp\!\!\!\perp} YW \mid Z)}$

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