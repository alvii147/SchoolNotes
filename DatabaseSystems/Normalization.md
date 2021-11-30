# Normalization

## Atomicity

An attribute is **atomic**, if and only if,

- Either, its **major** uses within a database and associated applications are such that it need not be divided further
- Or, a type exists for that attribute within the database engine such that component parts of the attribute can be treated as distinct and indivisible attributes.

### Examples

The attribute `courseID`, with values like `ECE208`, `ECE250`, `ECE356`, is not atomic in the context of a university database, since there are other departmental prefixes, such as `SE`, `CS` and `MATH`. However, in the context of a departmental database, where the only departmental prefix is `ECE`, the attribute `courseID` is atomic, since the division into course prefixes and course codes does not serve a major purpose given the context of the database.

Additionally, a `datetime` object in the MySQL database engine can be described as atomic. While it is divisible into second, minute, hour, day, month and year, this object type is defined in the MySQL database and is made up of distinct, indivisible attributes. Hence it can be considered atomic.

## Simple Functions

A function is a **simple function** if and only if it is computable without the use of explicit mapping.

### Examples

$\large f(x) = x^2$ is a simple function.

$\large f(x)$ as defined by the table

$\Large f(x)$ | $\Large x$
--- | ---
0 | 0
1 | 1
2 | 4
3 | 9

is not a simple function.

## Non-Redundancy

An attribute is **non-redundant** if and only if it is neither an input to, nor the result of, a simple function.

In contrast, an attribute is **redundant** if and only if it is either an input to, or the result of, a simple function.

### Examples

Consider a `section` relation defined with attributes as follows:

```
section(course_id, sec_id, semester, year, building, room_number)
```

The attribute `semester` is a term code combined with the last two digits of the year. For eg. `W21` represents "winter 2021".

Hence, there exists a simple function that can extract the year out of the semester.

This means neither of the attributes `semester` or `year` are non-redundant.

## Lossless Decomposition

A decomposition of relation $\large r$ into relations $\large r_1$ and $\large r_2$ is **lossless** if and only if
$$
\Large r = r_1 \bowtie r_2
$$
In other words, it is a lossless decomposition if and only if joining relations $\large r_1$ and $\large r_2$ using all the attributes that are common in both results in the relation $\large r$.

More specifically, if relation $\large r(R)$ is has attributes $\large A_i$ for $\large i = 1, 2, 3, ..., 10$:
$$
\Large R = (A_1, A_2, A_3, ..., A_n)
$$
then, relations $\large r_1(R_1)$ and $\large r_2(R_2)$ derived from the lossless decomposition of relation $\large r(R)$ are defined as:
$$
\Large R_1 = (A_i, A_j, ..., A_k, A_l) \\
\Large R_2 = (A_i, A_j, ..., A_p, A_q)
$$
where some attributes are in both $\large R_1$ and $\large R_2$ (i.e. $\large A_i, A_j$) and some attributes are in only $\large R_1$ (i.e. $\large A_k, A_l$) or in only $\large R_2$ (i.e. $\large A_p, A_q$). Note that there are no attributes that are not in either of $\large R_1$ and $\large R_2$.

## Functional Dependencies

Given attributes in a relation, a **functional dependency** is a function that uniquely maps the values of a set of attributes to the values of another set of attributes. The notation for functional dependencies is as follows:
$$
\Large a_1, a_2, ..., a_n \to b_1, b_2, ..., b_m
$$

### Formal Definition

Consider a relation schema $\large R$, and $\large \alpha$, $\large \beta$ as subsets of attributes of $\large R$:
$$
\Large \alpha \sube R, \: \beta \sube R
$$
Then, the functional dependency,
$$
\Large \alpha \to \beta
$$
holds if and only if, for any relation $\large r(R)$, whenever any two tuples $\large t_1$ and $\large t_2$ agree on attributes $\large \alpha$, they also agree on attributes $\large \beta$. That is,
$$
\Large t_1[\alpha] = t_2[\alpha] \implies t_1[\beta] = t_2[\beta]
$$

### Examples

Because everyone in Canada has a Social Insurance Number (SIN), there exists a functional dependency such that `SIN` $\large \to$ `Name`. This is because a person's social insurance number functionally determines their name. In other words, if we know the SIN, we know their name.

### Properties

#### Identity

- $\Large \alpha \to \alpha$

#### Reflexivity

- $\Large \beta \sube \alpha \implies \alpha \to \beta$

#### Augmentation

- $\Large \alpha \to \beta \implies \gamma\alpha \to \beta$

#### Transitivity

- $\Large \alpha \to \beta, \beta \to \gamma \implies \alpha \to \gamma$

## Closures

Given a set of functional dependencies $\large F$, the **closure** of $\large F$, denoted as $\large F^+$ is defined as the set of all possible functional dependencies logically implied by $\large F$ using the properties of functional dependencies. This also implies $\large F \sube F^+$

### Attribute-Set Closures

Given a relation $\large r$, a set of functional dependencies $\large F$ and a set of attributes $\large \alpha$, the **attribute-set closure** $\large \alpha^+$ is defined as the set of all attributes that can be logically determined using the attributes in $\large \alpha$.

## Extraneous Attributes

Given a set of functional dependencies $\large F$, functional dependency $\large (\alpha \to \beta) \in F$, an attribute $\large A \in \alpha$ is **extraneous** in $\large \alpha \to \beta$ if and only if,
$$
\Large F \iff (F - \{\alpha \to \beta\}) \: \cup \: \{(\alpha - A) \to \beta\}
$$
In other words, $\large A$ is not a necessary attribute in the functional dependency $\large \alpha \to \beta$.

### Examples

Consider a set of functional dependencies $\large F$:
$$
\Large F = \{A \to C, AB \to C\}
$$
Here, $\large B$ is an extraneous attribute in $\large AB \to C$, since we already know that $\large A \to C$. Hence $\large B$ is not needed in that functional dependency.

## Canonical Covers

Given a set of functional dependencies $\large F$, the canonical cover of $\large F$, is a minimal set of functional dependencies $\large F_c$ such that

- there exists no functional dependency $\large f \in F_c$ such that $\large f$ is implied by the set of functional dependencies $\large F_c - f$
- there exists functional dependency with extraneous attributes.

### Examples

Consider a set of functional dependencies $\large F$:
$$
\Large F = \{A \to B, B \to C, A \to C\}
$$
We know that,
$$
\Large A \to B, B \to C \implies A \to C
$$
Hence, $\large A \to C$ is a redundant functional dependency, which means $\large F$ is not a canonical cover. However, $\large F_c$ defined as,
$$
\Large F_c = \{A \to B, B \to C\}
$$
is a canonical cover.

## Keys

### Super Keys

Consider the set of all attributes $\large R$ in relation $\large r$, and set of attributes $\large \alpha \sube R$. Then, $\large \alpha$ is a **super key** of $\large r$ if and only if $\large \alpha^+ \supe R$.

In other words, in order for $\large \alpha$ to be a super key, all the attributes in $\large r$ must be logically determinable by the attributes in $\large \alpha$.

### Candidate Keys

If $\large \alpha$ is a super key of $\large r$, and there exists no $\large \beta \sub \alpha$ that is also a super key, then $\large \alpha$ is a **candidate key** of $\large r$.

In other words, $\large \alpha$ is a candidate key if and only if removing any attribute from $\large \alpha$ will result in it losing its super key status.

## Determining Candidate Key Attributes

Consider the set of all attributes $\large R$ in relation $\large r$ and a canonical cover $\large F_c$. We can make the following statements about candidate keys for $\large r$.

### Required Attributes

Any attribute that does not appear on the right-hand side of any functional dependency $\large f \in F_c$ **must be present** in every candidate key of $\large r$.

### Required Absent 1

Any attribute that does not appear on the left-hand side of any functional dependency $\large f \in F_c$ but appears on the right-hand side of at least one functional dependency $\large f \in F_c$ **must be absent** in every candidate key of $\large r$.

### Required Absent 2

 Any attribute that appears on the right-hand side of any functional dependency $\large f \in F_c$ where all the attributes on the left-hand side are required, **must be absent** in every candidate key of $\large r$.

### Maybe Present

Any attribute that appears on the left-hand side of some functional dependency $\large f \in F_c$ and the right hand-side of some other functional dependency $\large f \in F_c$ **must be absent in at least one** candidate key of $\large r$.

## First Normal Form

Given a relation $\large r$ with the set of all attributes $\large R$, $\large r$ is in **first normal form** if and only if every attribute in $\large R$ is atomic. In other words, if any of the attributes can be divided into multiple attributes for major uses within the context of the database and is not a type that is supported as multiple values in the database engine, the relation $\large r$ is not in first normal form.

## Third Normal Form

Given a relation $\large r$ with the set of all attributes $\large R$ and a set of functional dependencies $\large F$, $\large r$ is in **third normal form** if and only if, for every functional dependency $\large \alpha \to \beta$ in $\large F$, at least one of the following is true:

- $\Large \beta \sube \alpha$
- $\Large \alpha$ is a superkey for $\large R$
- $\Large \forall_{B \in \beta - \alpha} \:\: B \in CK$ where $\Large CK$ is the set of candidate keys of $\Large r$.

## Boyce-Codd Normal Form

Given a relation $\large r$ with the set of all attributes $\large R$ and a set of functional dependencies $\large F$, $\large r$ is in **third normal form** if and only if, for every functional dependency $\large \alpha \to \beta$ in $\large F$, at least one of the following is true:

- $\Large \beta \sube \alpha$
- $\Large \alpha$ is a superkey for $\large R$
