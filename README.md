# 선형대수학

Linear Algebra - Hoffman and Kunze  
영어 단어들 정리하고 헷갈릴 수 있는 교재 theorem들 한국어로 증명한거 쓰려고 함  

중간중간 그냥 내 머리로 생각해서 적은 풀이도 있어서 틀릴 가능성 있음  


## Chapter1
- equivalent system : 같은 변수, 같은 해집합 시스템  
- row-equivalent : 행 동치(기본행연산으로 만들 수 있는 것)  
- row-reduced : 각 행에서 첫 번째 수는 1, 그 첫 수가 있는 열은 그 수 제외 모두 0  
- row-reduced echelon matrix : row reduced이고, 모두 0인 행은 맨 아래에 있고, 아래로 갈수록 0 아닌 원소 나오는 위치 뒤로 가는 형태(row reduced에서 행 정렬까지 한 행렬)  
- homogeneous system : Ax=0 꼴의 우변 0인 시스템으로 자명한 해 x=0 존재
- elementary matrix : identity matrix에서 기본행연산 1번으로 얻을 수 있는 행렬

<br>

모든 행렬은 row-equivalent인 row-reduced, row-reduced echelon matrix 존재한다. 
> 과정을 잘 설명만 하면 된다. 영어가 좀 어렵긴 하네.

<br>

열 방향이 더 긴 행렬 A가 있으면 Ax=0 homogeneous system에서 non-trivial solution이 존재한다. 
> row-reduced echelon matrix로 바꿀 수 있고 이것은 equivalent system이다.  
> 이때 1이 최초로 등장하는 열 번호를 제외한 나머지를 아무거나 하고 1이 나오는 열의 값만 맞추면 그것이 non-trivial solution이다. 

<br>

정사각행렬이 identity metrix와 row-equivalent인 것과 Ax=0이 trivial solution만 가지는 것은 동치이다. 
> identity metrix면 당연히 Ix=x=0 trivial solution  
> trivial solution만 가진다고 하면 Ax=0을 row-reduced echelon matrix로 바꿔서 Rx=0으로 만들 수 있을 것이다.  
> 그런데 Rx=0이 x=0만 가능하기 때문에 모두 0인 행이 존재한다고 하면 그 항을 제외하고 나머지로만 식을 만들 수 있고, 그렇게 되면 열 방향이 더 긴 행렬이 되어 non-trivial solution이 존재하여 모두 0인 행은 존재할 수 없다.  
> 모두 0인 행이 없으려면 1이 대각선으로 쭉 있어야 하고 row-reduced의 정의에 의해 1이 있는 열 나머지는 다 0이 되어 identity metrix가 된다. 

<br>

대충 행렬곱 결합법칙 정도는 알고 있겠지?

<br>

기본행연산 e에 대해 e(A)=e(I)A
> e(AB)=e(A)B임을 증명해도 된다.  
> 간단하게 설명하면 A의 변화한 행이랑 B가 곱해지는 것이고 그 결과의 행에만 영향을 준다.  
> 제대로 하려면 연산 하나하나 따로 증명하는 것밖에 없나?  

같은 원리로 기본열연산 e에 대해 e(AB)=Ae(B)

<br>

n*n 행렬 A에 대해 아래 3개는 동치이다.  
- A는 가역행렬이다. 
- A는 identity matrix와 row-equivalent이다. 
- A는 elementary matrices의 곱이다.
> A의 row-reduced echelon matrix를 R이라고 하면 기본행연산 $E_i$에 대해 $R=E_1E_2...E_nA$이다.  
> elementary matrix는 가역이기 때문에 $A=E^{-1}_nE^{-1}_{n-1}...E^{-1}_1R$  
> A가 가역이면 R은 가역행렬의 곱이 되어 가역이다.  
> R은 n*n 행렬이고 row-reduced echelon matrix이다. 그리고 가역이기 때문에 0인 행이 존재하지 않아서 R은 identity matrix이다.  
> 그러면 A는 identity matrix와 row-equivalent가 된다.  
> elementary matrix의 역행렬도 elementary matrix이기 때문에 A는 elementary matrices의 곱이다. 
> 가역행렬의 곱은 가역이다. 따라서 A가 가역인 것으로 돌아와 동치가 된다. 

<br>

n*n 행렬 A에 대해 아래 3개는 동치이다.  
- A는 가역행렬이다. 
- Ax=0은 trivial solution x=0만을 가진다. 
- Ax=y는 y 1개당 1개의 solution을 가진다. 
> A가 가역이면 Ax=y에서 $x=A^{-1}y$ 1개의 solution을 가진다.  
> Ax=y가 1개의 solution을 가지면 Ax=0에서도 x=0 1개만 가지게 된다.  
> Ax=0에서 x=0만 가능하다는 것은 A가 identity matrix와 row-equivalent라는 것이다.  
> 그러면 $A=E_1E_2...E_nI$꼴로 나타낼 수 있고 A는 가역행렬의 곱이 되어 가역으로 돌아와 동치가 된다. 


## Chapter 2
- commutative : 교환법칙 성립
- associative : 결합법칙 성립
- subspace-spanned : 어떤 벡터들을 포함하고 있는 벡터공간의 모든 부분공간의 교집합을 벡터의 subspace-spanned라고 한다.

<br>

W가 V의 subspace인 것과 V에서 정의한 연산 그대로 W에 적용하여 W에 포함된 a, b, 스칼라 c에 대해 ac+b가 W에 포함되는 것은 동치이다. 
> 분배, 결합 등은 V 벡터공간으로 증명됨  
> (-1)p+p=0으로 덧셈 항등원 포함, (-1)p+0=-p로 덧셈 역원 포함  
> ca+0=ca로 스칼라곱 닫힘, 1a+b=a+b로 덧셈 닫힘  

<br>

V의 subspace의 intersection은 subspace이다. 
> $W_1$, $W_2$라고 하고 intersection을 W라고 하자.  
> $W_1$, $W_2$는 부분공간이므로 W에 포함되는 a, b에 대해 ca+b는 $W_1$, $W_2$에 둘다 포함되게 된다. 
> 이것이 W와 같고 W도 부분공간이 된다. 

<br>

subspace-spanned인 subspace는 벡터들의 선형결합으로 이루어진 집합이다. 
> 일단 벡터공간이니 당연히 선형결합은 존재한다.  
> 선형결합이 아닌 것이 있으면 당연히 그것을 포함하지 않는 것이 존재하여 교집합 안에 포함되지 않음. 

<br>

$a_1, a_2, ..., a_m$ 벡터의 생성공간에서 어떤 선형독립 집합도 m개보다 많은 원소를 가질 수 없다. 
> m보다 많은 선형독립 벡터 집합 $S=\{b_1, b_2, ..., b_n\}$ $(n>m)$ 존재하면  
> b들은 a의 선형결합이므로 행렬 A가 존재하여 아래의 식이 성립한다. 
> $$
\begin{bmatrix} b_1 & b_2 & ... & b_n \end{bmatrix} = \begin{bmatrix} a_1 & a_2 & ... & a_m \end{bmatrix}A
$$
> 이때 $bx=aAx=0$ 이므로 $Ax=0$ 인 x가 0 말고 존재한다면 S는 선형독립이 아니게 된다.  
> 한쪽이 더 긴 행렬은 non-trivial 해가 존재한다는 것을 위에 간단하게 증명해두었다.  

<br>

Lenma : 어떤 집합의 생성공간에 포함되지 않는 벡터는 그 집합과 선형독립이다.  
증명은 선형독립이 아니라고 하면 그냥 그 생성공간에 포함이 된다. 

W가 유한 차원 벡터공간 V의 부분공간이면 W의 모든 선형독립 부분집합은 유한하고 기저의 일부가 될 수 있다. 
> V가 유한 차원이기 때문에 W도 부분집합이라 유한 차원이다. 따라서 W의 유한한 차원보다 많은 선형독립 집합은 존재하지 않는다.  
> 어떤 선형독립 집합을 S라고 하고 span(S)!=W이면 W-span(S)의 임의의 원소 b를 하나 가져오면 S와 선형독립이다.  
> S.add(b) 하면서 span(S)==W 될 때까지 반복

<br>

유한차원 벡터공간에서 $dim(W_1)+dim(W_2)=dim(W_1∪W_2)+dim(W_1∩W_2)$
> $W_1∩W_2$의 기저를 위의 Theorem을 이용해서 확장하면 된다.

<br>

$[\alpha]_{\beta}$ : 벡터 $\alpha$를 ordered basis $\beta$로 만드는 좌표를 의미함 (coordinate)  
좌표변환 행렬 P : $[\alpha]_{\beta}=P[\alpha]_{\beta^{'}}$  
P는 invertible이고 유일하다. 
$$
α=\begin{bmatrix}β_1 & β_2 & ... & β_n\end{bmatrix}[α]_{β}
$$
$$
=\begin{bmatrix}β_1 & β_2 & ... & β_n\end{bmatrix}P[α]_{β^{'}}
$$
$$
=\begin{bmatrix}β_1^{'} & β_2^{'} & ... & β_n^{'}\end{bmatrix}[α]_{β^{'}}
$$
$$
βP=β^{'}
$$
P의 col vector는 $β^{'}$의 각 기저를 $β$로 나타낸 좌표 벡터이다. 

<br>

row-reduced echelon matrix의 0이 아닌 row vector들은 그것의 row space의 기저이다. 
> row vector의 생성공간이기 때문에 선형독립만 증명하면 된다.  
> 선형독립도 그냥 선형결합으로 0을 만든다고 했을 때 1이 최초로 등장하는 부분에는 나머지가 0이므로 그 0이 곱해져야 그 열이 0이 된다.  

<br>

$F^n$의 부분공간인 W가 존재할 때 row space가 W가 되는 0이 아닌 row-reduced echelon matrix가 유일하게 존재한다. 
> 선형독립인 임의의 기저 하나를 그냥 잡을 수 있다. (기저로 확장 가능하기 때문)   
> 이걸 row-reduced echelon matrix로 바꾸면 최소 하나는 존재하게 된다.  
> row space가 같은 2개의 row-reduced echelon matrix가 존재한다고 하면 이 2개는 row-equivalent이다.
> row-equivalent인 row-reduced echelon matrix 2개는 없다.  
> https://www.youtube.com/watch?v=EcgaeUUYV1U  

근데 이거 뭔가 이상하다. 교과서에서는 row-reduced echelon matrix의 유일성 없이 증명하고 이걸 통해서 유일성을 증명했다. 나중에 확인해보고 바꿔야 할지도

<br>

## Chapter 3
- linear operator : V to V 선형변환
- 선형변환에서 invertible : T가 있을 때 UT=TU=I인 선형변환 U가 존재하면 U=T$^{-1}$이고 T는 invertible이다.
- non-singular : T(x)=0인 x가 0 하나밖에 없으면 T를 non-singular이라고 한다.  



T가 V to W 선형변환일 때 rank(T)+nullity(T)=dim(V)
> T의 nullspace의 기저를 쭉 나타내고 그것을 $b_1, b_2, ..., b_n$이라고 하자.  
> 여기에서 dim(V)=m개까지 기저 확장이 가능하다.  
> 그러면 $b_{n+1}, b_{n+1}, ..., b_m$이 추가로 들어가게 되고 $T(b_{n+1}), ..., T(b_{m})$이 T(V)를 생성함을 보이면 된다. 
> 일단 $b_1, b_2, ..., b_m$은 V의 기저이다. $T(b_1), ..., T(b_m)$은 T(V)를 생성한다.  
> 근데 $b_1, b_2, ..., b_n$은 T 거치면 0이 되니까 당연히 $T(b_{n+1}), ..., T(b_{m})$로도 T(V)를 생성한다.  

<br>

A가 m*n 행렬일 때 row rank(A)=column rank(A)
> n차원 벡터 x T(x)=Ax일때 rank(T)=column rank(A)=n-nullity(T)  
> Ax=0을 만드는 x의 차원을 생각해보면 A를 row-reduced echelon matrix로 바꿔서  
> Rx=0으로 생각할 수 있고 R의 0이 아닌 행의 수를 r이라고 할 때 r은 column rank(A)가 된다.  
> $x_1, x_2, ..., x_n$ 중에서 첫 1이 나오는 자리에 들어가는 x들을 제외하고 모두 자유롭게 결정할 수 있다.  
> 1이 나오는 자리의 수는 r이라서 Rx=0이 되는 x의 차원은 n-r=n-column rank(A)이다.  

<br>

각각 m, n차원 벡터공간 W, V에 대해 L(W, V)는 mn차원 벡터공간이다. (L(W, V)는 W to V 선형변환의 집합을 의미함)
> W의 기저 $a_1, a_2, ..., a_m$  
> V의 기저 $b_1, b_2, ..., b_n$  
> $T_{ij}(a_i)=b_j$ 이것으로 모든 선형변환 T를 유일하게 만들 수 있다는 것을 증명해야 한다.  
> 임의의 T에 대해 $[T(a_1)]_b, [T(a_1)]_b, ..., [T(a_m)]_b$를 얻으면 mn개의 $T_{ij}(a_i)=b_j$와 일대일로 대응된다.  
> $[T(x)]_b=\begin{bmatrix}[T(a_1)]_b && [T(a_1)]_b && ... && [T(a_m)]_b\end{bmatrix}[x]_a$로 모든 x에 대해 T값을 알 수 있다.   
> 따라서 $T_{ij}$가 있으면 모든 x에 대해 T(x)가 정해지게 된다. 모든 선형변환을 만들 수 있음이 증명되었다.  

<br>

모든 V에서 선형독립인 집합이 T를 거쳐서 W에서 선형독립 집합이 되는 것과 T가 non-singular인 것은 동치이다.  
> V의 선형독립 집합인 기저 a={$β_1, β_2, ..., β_n$}이 있을 때 b={$T(β_1), T(β_2), ..., T(β_n)$}가 W에서 선형독립이라면  
> $T(x)=T([β_1\ \ β_2\ \ ...\ \ β_n][x]_a)=[T(β_1)\ \ T(β_2)\ \ ...\ \ T(β_n)][x]_a=0$  
> b가 선형독립 집합이라서 $[x]_a$가 0밖에 없다.  
>   
> 만약 T(x)=x가 0밖에 없으면  
> 어떤 선형독립 집합 a={$β_1, β_2, ..., β_n$}를 V에서 잡아도 
> $c_1T(β_1)+c_2T(β_2)+...+c_nT(β_n)=T(c_1β_1+c_2β_2+...+c_nβ_n)=0$  
> $c_1β_1+c_2β_2+...+c_nβ_n=0$밖에 없는데 a가 선형독립 집합이라서 $c_i=0$밖에 없고 $T(β_i)$들도 선형독립이다.  

<br>

차원이 같은 두 집합 V, W에서 V to W 선형변환 T에 대해 아래 3개는 동치이다.  
T는 invertible이다.  
T는 non-singular이다.  
T는 onto이다. (T(V)=W)
> 아직안함























