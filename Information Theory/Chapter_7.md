### 7.8 Mutual information based on f-divergence

**(p107)** In the third section, the book tries to prove under the condition that $A,B$ are independent conditioning on $X$, then:
$$
I_{skl}(X;A,B)=I_{skl}(X;A)+I_{skl}(X;B)
$$
The book proved the formula under the discrete case, here is some annotation that explain some of the tricky steps of the proof.

1. from 7.46 to 7.45 we need a conclusion:
$$
D(P_{A,B|X=x}\Vert P_{A,B|X=x'})=D(P_{A|X=x}\Vert P_{A|X=x'})+D(P_{B|X=x}\Vert P_{B|X=x'})
$$

which is refered to as *the additivity of KL-Divergence*. This only rings true under the condition that $A,B$ are independent conditioning on $X$. This properity of KL-Divergence can be found on p30, and is known as *Tensorization*. Here I provide a detailed proof down below:

Using the chain rule of KL-Divergence
$$
D(P_{A,B|X=x}\Vert P_{A,B|X=x'})=D(P_{A|B,X=x}\Vert P_{A|B,X=x'}\vert P_{B,X=x})+D(P_{B|X=x}\Vert P_{B|X=x'})
$$
since $A,B$ are independent conditioning on $X$, we have $P_{A|B,X=x} = P_{A|X=x}$ and $P_{A|B,X=x'} = P_{A|X=x'}$, then we get the result:
$$
\begin{aligned}
D(P_{A,B|X=x}\Vert P_{A,B|X=x'})&=D(P_{A|X=x}\Vert P_{A|X=x'}\vert P_{B,X=x})+D(P_{B|X=x}\Vert P_{B|X=x'})\\
&=D(P_{A|X=x}\Vert P_{A|X=x'})+D(P_{B|X=x}\Vert P_{B|X=x'})
\end{aligned}
$$
And we complete the proof.

2. In the book, it says *Since the marginals of $P_{X,Y}$ and $P_XP_Y$ coincide, we can replace $\log \frac{P_{X,Y}(x,y)}{P_X(x)P_Y(y)}$ by any $\log \frac{P_{Y|X}(y|x)} {f(y)}$ for any $f$. We choose $f(y) = P_{Y|X}(y|x′)$* and deduce that:
$$
\begin{aligned}
I_{skl}(X;Y)&=\sum_{x,y}[P_{X,Y}(x,y)-P_X(x)P_Y(y)]\log \frac{P_{X,Y}(x,y)}{P_{X}(x)P_Y(y)}\\
&=\sum_{x,y}[P_{X,Y}(x,y)-P_X(x)P_Y(y)]\log \frac{P_{Y|X}(y|x)}{P_{Y|X}(y|x')}
\end{aligned}
$$

To explain why this deduction works, I will add some more details:
$$
\begin{aligned}
I_{skl}(X;Y)&=\sum_{x,y}[P_{X,Y}(x,y)-P_X(x)P_Y(y)]\log \frac{P_{X,Y}(x,y)}{P_{X}(x)P_Y(y)}\\
&=\sum_{x,y}[P_{X,Y}(x,y)-P_X(x)P_Y(y)]\left[\log \frac{P_{Y|X}(y|x)}{P_{Y|X}(y|x')}+\log \frac{P_{Y|X}(y|x')}{P_{Y}(y)}\right]\\
&=\sum_{x,y}[P_{X,Y}(x,y)-P_X(x)P_Y(y)]\log \frac{P_{Y|X}(y|x)}{P_{Y|X}(y|x')}+\sum_{y}\left[\sum_{x}[P_{X,Y}(x,y)-P_X(x)P_Y(y)]\right]\log \frac{P_{Y|X}(y|x')}{P_{Y}(y)}\\
&=\sum_{x,y}[P_{X,Y}(x,y)-P_X(x)P_Y(y)]\log \frac{P_{Y|X}(y|x)}{P_{Y|X}(y|x')}
\end{aligned}
$$
The final step shows how *the marginals of $P_{X,Y}$ and $P_XP_Y$ coincide* work.

> Here I try to prove the general case using the chain rule:
$$
\begin{aligned}
&D(P_{X,A,B}\Vert P_XP_{A,B})=D(P_{X,A}\Vert P_XP_{A})+D(P_{B|X,A}\Vert P_{B|A}\vert P_{X,A})\\
&D(P_XP_{A,B}\Vert P_{X,A,B})=D(P_XP_{A}\Vert P_{X,A})+D(P_{B|A}\Vert P_{B|X,A}\vert P_{X}P_{A})
\end{aligned}
$$
adding the two formula above, we have:
$$
I_{skl}(X;A,B)=I_{skl}(X;A)+D(P_{B|X,A}\Vert P_{B|A}\vert P_{X,A})+D(P_{B|A}\Vert P_{B|X,A}\vert P_{X}P_{A})
$$
so the key here is to prove that when $A\bot B|X$:
$$
I_{skl}(X;B) = D(P_{B|X,A}\Vert P_{B|A}\vert P_{X,A})+D(P_{B|A}\Vert P_{B|X,A}\vert P_{X}P_{A})
$$