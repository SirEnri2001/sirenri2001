# Discrete Differential Geometry: An Applied Introduction

<a>http://www.cs.cmu.edu/~kmcrane/Projects/DDG/paper.pdf</a>

By Keenan Crane

Reading notes by Henry Han

## Chapter 1

Mostly related with Discrete Exterior Calculus **DEC**

**Tangent space at any point:**

In smooth geometric settings:

$\sum_{i}\theta_i=2\pi$

In differential settings:

$\sum_{i}\theta_i\lt2\pi$

Therefore we can use $\tilde{\theta_i}$ as augmented or "discrete" angles

$\tilde{\theta_i}:=s\theta_i$

$s:=\frac{2\pi}{\sum_{i}{\theta_i}}$

where $\theta_i$ denotes the usual Euclidean angles and

## Chapter 2: Combinatorial Surfaces

how surfaces are connected up, not where they are in space

the same as topological surface in smooth settings

**Manifold**

basic simplifying assumption of differential geometry

Topological disk

**Simplicial complex**

encoded by incidence matrices

halfedge mesh

**Abstract Simplicial Complex**

To describe connectivity:

**simplicial complex**

vertices $V={0,1,2,...,n}$

**Face**

any (nonempty) subset of a simplex, a strict subset is called a proper face

**Pure k-simplicial complex**

every simplex $\sigma'\in K$ is contained in some simplex of degree k

Star $\text{St}(i)$ is the collection of all simplices $\sigma\in K$ such that $i\in\sigma$

Closure $\text{Cl}(i)$ the smallest subcomplex

Link $\text{Lk}(i)=\text{Cl}(\text{St}(i))\backslash\text{St}(\text{Cl}(i))$ where $A\backslash B$ denotes the set difference

Boundary $\text{bd}(K')$ is the closure of the set of all simplices $\sigma$ that are proper faces of exactly one simplex of $K'$

Interior $\text{int}(K')=K'\backslash \text{bd}(K')$

**Oriented Simplicial Complex**

orientation of a simplex is really an **equivalence class** (permutations) of ordered tuples

$ijk:=\{(i,j,k),(j,k,i),(k,i,j)\}$

$ikj:=\{(i,k,j),(j,i,k),(k,j,i)\}$

**Even / Odd permutations**

are different orientations, except 0-simplex

**Relative Orientation**

same orientations:

(i,j) -> (j,k)

(i,j,k) -> (k,j,l)

**Simplicial Surfaces**

abstract simplicial surface

is a pure simplicial 2-complex where the link of every vertex so a single loop of edges

a "disk-like" neighborhood captures the bassic idea of a topological surface, manifold

**Oriented Simplicial Surface**

❌Mobius band

Higher dim:

A simplicial n-sphere: $\mathbb{S}^n:=\{x\in\mathbb{R}^{n+1}:|x|=1\}$

i.e., the set of all points unit distance from the origin in n-dimensional space

**Adjacency Matrices**

closely linked to the discrete differential forms

mostly sparse, so we use sparse matrix data structure

**Halfedge Mesh**

two key functions:

twin(symmetric) $\eta(ij)=ji$

next $\rho(ij)=jk, \forall ijk\in K$

faces are orbits of $\rho$

edges are orbits of $\eta$

vertices are orbits of $\rho \circ \eta$

Csaszar polyhedron: describe a torus using a simplicial complex we need at least 7 verts, 21 edgees, and 14 triangles
