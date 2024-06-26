# Theoretical Background

An abstract boundary value problem is formulated as to find a function $U$ which fulfills the equations:

\begin{equation}
AU = h \text{ inside the domain } \Omega
\end{equation}

\begin{equation}
LU = g \text{ at the domain boundary } \Gamma
\end{equation}

Where $A$ and $L$ are differential operators.

Some boundary value problems can be equally formulated in a variational form such as to find a function $U$ which provides a functional $F(U)$ at minimum value, where the functional $F(U)$ is usually an energy functional.

In 1908 W. Ritz proposed a method of finding an approximate solution of a boundary value problem by approximating it with a linear combination of some basis-functions.

\begin{equation}
U_h = \sum_{i}^n a_i p_i
\end{equation}

Where $a_i$ are unknown factors, and $p_i$ are basis approximation functions.

The factors $a_i$ are found by minimizing the energy functional

\begin{equation}
F(\sum_{i}^n a_i p_i) = \min
\end{equation}

If the boundary value problem is linear, then the minimization problem (Equation 4) can be reduced to a linear algebraic equation system with respect to the factors $a_i$

\begin{equation}
Kd = f
\end{equation}

Where K is a symmetric matrix, d is the vector of unknown factors, and f is a right-hand side of the system.

In FEM the matrix K is called a stiffness matrix, the vector f is called a load vector, and factors $a_i$ are called degrees of freedom.

In 1915 Galerkin proposed another approximate method of solving the boundary value problem (Equation 1)-(Equation 2). According to the Galerkin method the unknown solution U is approximated as

\begin{equation}
U_n = U_0 + \sum_{i}^n a_i p_i
\end{equation}

Where $U_0$ is some function which fulfills non-homogeneous boundary conditions (Equation 2), $p_i$ are analytical approximation functions which fulfill homogeneous boundary conditions, $a_i$ are unknown factors.

Substitution of (Equation 6) into (Equation 1) results in the residual.

\begin{equation}
R = AU_0 + \sum_{i}^n a_i Ap_i - h
\end{equation}

The unknown factors $a_i$ are found from the equation system.

\begin{equation}
\int_\Omega R p_i d\Omega = 0
\end{equation}

If a boundary value problem is linear, then system (Equation 8) is a system of linear algebraic equations.

The Galerkin method does not use a variational formulation of the boundary value problem. Therefore, its applicability is much wider.

Ritz and Galerkin methods proved to be effective means of solving problems in engineering and science. At the same time mathematical justification of the methods faced significant difficulties which were solved with the introduction of functional analysis as a mathematical discipline.

Modern theory of the Ritz-Galerkin method is based on the concept of the weak formulation of the boundary value problem. The weak formulation of a boundary value problem consists of finding a function from $u \in V$ a corresponding Sobolev space which fulfills an abstract variational equation

\begin{equation}
a(u,v) = f(v) \text{ for any function } v \in V
\end{equation}

Where $V$ is some subspace of a Sobolev space, $a(u,v)$ is generally an unsymmetrical bilinear form which is continuous on the space product $V \times V$, $f(v)$ is some linear form in $V$.

In structural analysis, the Sobolev space is a space of functions with finite strain energy.

In the Ritz-Galerkin method the space $V$ is approximated with some finite-dimensional space $X_h$, and the approximate solution is found in form (Equation 3) where the functions $p_i$ belong to the space $X_h$. Therefore, the discretized formulation of a boundary value problem is:

Find a function $U_h \in X_h$ which fulfills the equation.

\begin{equation}
a(U_h,V_h) = f(V_h) \text{ for any function } V_h \in X_h
\end{equation}

Substitution of (Equation 3) into (Equation 10) results in a linear algebraic equation system from which unknown factors $a_i$ are found.

In the classic Ritz-Galerkin method $X_h$ is a space of analytical functions defined on the whole domain $\Omega$, the factors $a_i$ have no physical meaning. In conventional Finite Element Method $X_h$ is a space of piecewise polynomials and factors $a_i$ are values of the function $U_h$ in the nodes of finite elements. In structural analysis they are displacements of the nodes.

Many modifications of Ritz-Galerkin methods have been invented. They differ by the variational equations (Equation 9) and by the classes of basis-functions (Equation 3) used to approximate the solution. The same boundary value problem can have several equivalent formulations (Equation 9) which differ by the spaces $V$.
