# 선형대수학

Linear Algebra - Hoffman and Kunze  
영어 단어들 정리하고 교재 theorem들 한국어로 증명한거 쓰려고 함  


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

