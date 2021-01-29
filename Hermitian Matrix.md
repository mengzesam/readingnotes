## Hermitian Matrix
***
- **Lemma**: $\mathbf{A}$ is Hermitian if and only if $\mathbf{x^*Ax}$ is real for all 
$\mathbf{x}\in \mathbf{C}^n$ 
>**proof.** <br/>
  only if(necessity):
    $\overline{\mathbf{x^*Ax}}=\mathbf{(x^*Ax)^*}=\mathbf{x^*A^*x}$,
    and $\mathbf{A^*=A}$,
    so $\overline{\mathbf{x^*Ax}}=\mathbf{x^*Ax}$,
    that is $\mathbf{x^*Ax}$ equals its complex conjugate and hence is real,
    or $\mathbf{x^*Ax} \in R$.<br/>
  if(sufficiency):$\forall\mathbf{x}\in \mathbf{C^n},\mathbf{x^*Ax}$ is real,
  $\mathbf{(x+y)^*A(x+y)}\in R$,that is $\mathbf{(x+y)^*A(x+y)}=\mathbf{x^*Ax+y^*Ay+x^*Ay+y^*Ax} \in R$,
  so $\forall \mathbf{x \in C^n},\mathbf{x^*Ay+y^*Ax}\in R$.If we choose $\mathbf{x=e_k,y=e_j}$,then $\mathbf{x^*Ay}=\mathit{a_{kj}},\mathbf{y^*Ax}=\mathit{a_{jk}}$ ,so $\mathbf{x^*Ay+y^*Ax}=\mathit{a_{kj}+a_{jk}}$ is real, i.e. $Im(\mathit{a_{kj}})=-Im(\mathit{a_{jk}})$.
  If we choose $\mathbf{x=ie_k,y=e_j}$,then $\mathbf{x^*Ay+y^*Ax}=\mathit{\mathbf{-i}a_{kj}+\mathbf{i}a_{jk}}$ is real,i.e. $Re(\mathit{a_{kj}})=Re(\mathit{a_{jk}})$.<br/>
  To sum up,$\forall k,j \in [1,n], \exists a_{kj}=\overline{a_{jk}}$, hence $\mathbf{A^*=A}$, $\mathbf{A}$ is Hermitian.

- **Lemma**: If $\mathbf{A}$ is Hermitian then the eigenvalues of $\mathbf{A}$ are real. 
>**Proof.** <br/>
> If $\mathbf{Ax=\lambda x}$ and $\mathbf{x^*x=1}$, 
> then $\lambda =\lambda \mathbf{x^*x}=\mathbf{x^*\lambda x}> =\mathbf{x^*Ax}$, so $\lambda$ is real.

- **Lemma**: If $\mathbf{A}$ if normal and has only real eigenvalues, then $\mathbf{A}$ is Hermitian.
> **Proof.** <br/>
> If $\mathbf{A}$ is normal, it is Unitarily diagonalizable, so 
> $\mathbf{A=U \Lambda U^*}$ with $\Lambda=diag(\lambda_1,\lambda_2,...,\lambda_n)$, $\mathbf{A^*=(U \Lambda U^*)^*=U \bar{\Lambda}U^*}$, 
> but if $\Lambda$ is real, we have $\mathbf{A^*=U \Lambda U^*=A}$.

- **Lemma:** Let $\mathbf{A \in M_n}$ be Hermitian, then <br/>
$\forall S \in M_n$, $\mathbf{S^*AS}$ is Hermitian.
> **Proof.** <br/>
> If $\mathbf{A^*=A}$, so $\mathbf{(S^*AS)^*=S^*A^*S=S^*AS}$.

- **Lemma:** If $\mathbf{S^*AS}$ is Hermitian for all $\mathbf{S \in M_n}$, then $\mathbf{A}$ is Hermitian.
> **Proof.** <br/>
> Let $\mathbf{S=I,I \in M_n}$ and is identity, then 
> $\mathbf{S^*AS=I^*AI=A}$ is Hermitian.

- **State:**
> Hermitian is normal: $\mathbf{AA^*=AA=A^*A}$, so all the properties about normal matrices apply to Hermitian matrices. e.g.: <br/>
> 1.  eigenvectors associated with distinct eigenvalues are orthogonal, there is an orthonormal basis of eigenvectors.
> 2. Hermitian matrices are unitarily diagonalizable.

- **Lemma:** $\mathbf{A}$ is Hermitian if and only if there is a unitary $\mathbf{U \in M_n}$ and a real diagonal $\mathbf{\Lambda \in M_n}$ ,so that $\mathbf{A=U \Lambda U^*}$. <br/>
Moreover $\mathbf{A}$ is real sysmmetric if and only if there is a real orthogonal $\mathbf{P \in M_n}$ and a real diagonal $\mathbf{\Lambda \in M_n}$ ,so that $\mathbf{A=P \Lambda P^*}$. 
