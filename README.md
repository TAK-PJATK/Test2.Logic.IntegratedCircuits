# Test2.Logic.IntegratedCircuits

# Logic

This lecture will cover logic, an essential topic for two main reasons. First, understanding logic is crucial for computer scientists; it is necessary to handle logical expressions correctly, as they frequently appear in conditional statements while programming. The second reason is more directly related to this course: logic expressions are the foundation on which all arithmetic computations in computer processors are based (a topic that will be covered in more detail in later lectures).

## Predicate Calculus

Logic deals with the truth value (true or false) of predicates. Predicates are essentially sentences, though not ones like "Polish mountains are the most beautiful," but rather "5 is larger than 6" or "3 is an odd number." While other areas of mathematics let us assert that "3 is odd" is true and "5 is larger than 6" is false, it is logic that determines the truth value of these sentences combined with the word "or."

## Logical Operators

Let's start by discussing the four basic logical operators:

- **AND (conjunction)**
- **OR (disjunction)**
- **XOR (exclusive disjunction; aka. exclusive or; meaning: "either this or that (but not both)")**
- **NOT (negation)**

1. **AND (Conjunction)**:
   - A predicate \(a \land b\) is true if and only if both \(a\) and \(b\) are true. (Note that it is irrelevant what \(a\) and \(b\) actually say).

2. **OR (Disjunction)**:
   - A predicate \(a \lor b\) is true if and only if at least one of \(a\) or \(b\) is true. That is, they may both be true, or just one of them may be true. In other words, \(a \lor b\) is false if and only if both these predicates are false. For example, the sentence "tomorrow it will rain or tomorrow it will not rain" is always true.

3. **XOR (Exclusive Disjunction)**:
   - A predicate \(a \oplus b\) is true if and only if exactly one of \(a\) or \(b\) is true. That is, they cannot both be true—exactly one of them has to be. For example, the sentence "I am now in Warsaw XOR I am now in the capital of Poland" is always false (regardless of whether the speaker is actually now in Warsaw or not).

4. **NOT (Negation)**:
   - A predicate \(\neg a\) means the negation of \(a\), so it is true if and only if \(a\) is false. For example, the sentence "Warsaw is not the capital of Spain" is true. (To make the casual syntax closer to the formal syntax of this predicate, we could rephrase it as: "It is not true that Warsaw is the capital of Spain").
  
### True and False Symbols

Describing logic with words can be cumbersome and lengthy. Therefore, a more concise notation is helpful. In logic, it's customary to denote "true" by 1 and "false" by 0. Using this notation, the AND operator can be expressed more directly as follows:

\[ 
0 \cdot 0 = 0 \\
1 \cdot 0 = 0 \\
0 \cdot 1 = 0 \\
1 \cdot 1 = 1 
\]

### Truth Tables

The above form of presentation can be further enhanced with truth tables. Rows correspond to the possible logical values of predicate \(a\), and columns to the values of predicate \(b\). Each cell contains the value of \(a \cdot b\).

#### AND Truth Table
\[
\begin{array}{c|cc}
\cdot & 0 & 1 \\
\hline
0 & 0 & 0 \\
1 & 0 & 1 \\
\end{array}
\]

Below are analogous tables for the other operators discussed before:

#### OR Truth Table
\[
\begin{array}{c|cc}
+ & 0 & 1 \\
\hline
0 & 0 & 1 \\
1 & 1 & 1 \\
\end{array}
\]

#### XOR Truth Table
\[
\begin{array}{c|cc}
\oplus & 0 & 1 \\
\hline
0 & 0 & 1 \\
1 & 1 & 0 \\
\end{array}
\]

#### NOT Truth Table
\[
\begin{array}{c|c}
\neg &  \\
\hline
0 & 1 \\
1 & 0 \\
\end{array}
\]

The truth table for the NOT operator has a different shape, as this operator takes only one argument.

Using truth tables, one can define more logical operators. For example, the following tables define two more commonly used connectives, NAND (not-and) and NOR (not-or):

#### NAND Truth Table
\[
\begin{array}{c|cc}
\operatorname{NAND} & 0 & 1 \\
\hline
0 & 1 & 1 \\
1 & 1 & 0 \\
\end{array}
\]

#### NOR Truth Table
\[
\begin{array}{c|cc}
\operatorname{NOR} & 0 & 1 \\
\hline
0 & 1 & 0 \\
1 & 0 & 0 \\
\end{array}
\]

### Complex Expressions

There may be many operators used in one predicate. For example: \((a \oplus b) \cdot (a \cdot \neg b)\). For such a complex expression, we can also build a truth table. In this case, it would look as follows:

#### Truth Table for \((a \oplus b) \cdot (a \cdot \neg b)\)
\[
\begin{array}{c|cc}
(a \oplus b) \cdot (a \cdot \neg b) & b = 0 & b = 1 \\
\hline
a = 0 & 0 & 0 \\
a = 1 & 1 & 0 \\
\end{array}
\]

Swapping the roles of \(a\) and \(b\) would impact the value of the final expression. Therefore, for full clarity, it is indicated that rows correspond to the values of \(a\) and columns to the values of \(b\).

More than two variables can be used in a predicate. For example: \((a \oplus b) \cdot (a \cdot \neg c)\). The truth table must then include all possible combinations of values of the input variables:

#### Truth Table for \((a \oplus b) \cdot (a \cdot \neg c)\)
\[
\begin{array}{ccc|c}
a & b & c & (a \oplus b) \cdot (a \cdot \neg c) \\
\hline
0 & 0 & 0 & 0 \\
0 & 0 & 1 & 0 \\
0 & 1 & 0 & 0 \\
0 & 1 & 1 & 0 \\
1 & 0 & 0 & 1 \\
1 & 0 & 1 & 0 \\
1 & 1 & 0 & 0 \\
1 & 1 & 1 & 0 \\
\end{array}
\]

### Other Notations

In logic, there are various notational conventions. Instead of NOT \(a\), we can write:
\[ \neg a = \sim a = \overline{a} = -a \]

For other operators, there are also multiple notations:
\[ a \cdot b = a \land b = a \& b \]
\[ a + b = a \lor b = a \| b \]
\[ a \oplus b = a \text{ XOR } b = a \odot b \]

### Properties of Logical Operators

So far, we've covered the definitions of logical operators and their notations. An interesting question is what relationships hold between them. The basic properties are listed below:

#### Basic Properties of Logical Operators

| Property Name   | For AND              | For OR             |
|-----------------|----------------------|--------------------|
| Neutral elements| \( p \cdot 1 = p \)  | \( p + 0 = p \) |
| Extreme elements| \( p \cdot 0 = 0 \)  | \( p + 1 = 1 \) |
| Idempotence     | \( p \cdot p = p \)  | \( p + p = p \) |
| Complement      | \( p \cdot \neg p = 0 \) | \( p + \neg p = 1 \) |
| Commutativity   | \( p \cdot q = q \cdot p \) | \( p + q = q + p \) |
| Associativity   | \( (p \cdot q) \cdot r = p \cdot (q \cdot r) \) | \( (p + q) + r = p + (q + r) \) |
| Distributivity  | \( p \cdot (q + r) = (p \cdot q) + (p \cdot r) \) | \( p + (q \cdot r) = (p + q) \cdot (p + r) \) |
| Absorption      | \( (p \cdot q) + p = p \) | \( (p + q) \cdot p = p \) |
| De Morgan's laws| \( \neg(p \cdot q) = \neg p + \neg q \) | \( \neg(p + q) = \neg p \cdot \neg q \) |

These equalities can be validated by analyzing the truth tables for both sides and confirming that both sides have equal values, regardless of the input values of \(p\), \(q\), and \(r\).

The above table contains many well-known properties of standard multiplication and addition (e.g., commutativity, associativity, the first of the distributivity properties, etc.). This is why the convention of denoting AND, OR, true, and false respectively by \(\cdot\), \(+\), 1, and 0 is so intuitive. However, we must exercise caution, as not all rules of arithmetic hold for these symbols interpreted in the world of logic. For example, in logic, \(1 + 1 = 1\), which violates the standard arithmetic property that \(a + b = a\) necessarily implies \(b = 0\). On the other hand, compared to standard arithmetic, the operations \(+\) and \(\cdot\) gain some new elegant properties in the world of logic, such as the second distributivity property and absorption.
  
### True and False Symbols

Describing logic with words can be cumbersome and lengthy. Therefore, a more concise notation is helpful. In logic, it's customary to denote "true" by 1 and "false" by 0. Using this notation, the AND operator can be expressed more directly as follows:

\[ 
0 \land 0 = 0 \\
1 \land 0 = 0 \\
0 \land 1 = 0 \\
1 \land 1 = 1 
\]

### Truth Tables

The above form of presentation can be further enhanced with truth tables. Rows correspond to the possible logical values of predicate \(a\), and columns to the values of predicate \(b\). Each cell contains the value of \(a \land b\).

#### AND Truth Table
\[
\begin{array}{c|cc}
\land & 0 & 1 \\
\hline
0 & 0 & 0 \\
1 & 0 & 1 \\
\end{array}
\]

Below are analogous tables for the other operators discussed before:

#### OR Truth Table
\[
\begin{array}{c|cc}
\lor & 0 & 1 \\
\hline
0 & 0 & 1 \\
1 & 1 & 1 \\
\end{array}
\]

#### XOR Truth Table
\[
\begin{array}{c|cc}
\oplus & 0 & 1 \\
\hline
0 & 0 & 1 \\
1 & 1 & 0 \\
\end{array}
\]

#### NOT Truth Table
\[
\begin{array}{c|c}
\neg &  \\
\hline
0 & 1 \\
1 & 0 \\
\end{array}
\]

The truth table for the NOT operator has a different shape, as this operator takes only one argument.

Using truth tables, one can define more logical operators. For example, the following tables define two more commonly used connectives, NAND (not-and) and NOR (not-or):

#### NAND Truth Table
\[
\begin{array}{c|cc}
\operatorname{NAND} & 0 & 1 \\
\hline
0 & 1 & 1 \\
1 & 1 & 0 \\
\end{array}
\]

#### NOR Truth Table
\[
\begin{array}{c|cc}
\operatorname{NOR} & 0 & 1 \\
\hline
0 & 1 & 0 \\
1 & 0 & 0 \\
\end{array}
\]

### Complex Expressions

There may be many operators used in one predicate. For example: \((a \oplus b) \land (a \land \neg b)\). For such a complex expression, we can also build a truth table. In this case, it would look as follows:

#### Truth Table for \((a \oplus b) \land (a \land \neg b)\)
\[
\begin{array}{c|cc}
(a \oplus b) \land (a \land \neg b) & b = 0 & b = 1 \\
\hline
a = 0 & 0 & 0 \\
a = 1 & 1 & 0 \\
\end{array}
\]

Swapping the roles of \(a\) and \(b\) would impact the value of the final expression. Therefore, for full clarity, it is indicated that rows correspond to the values of \(a\) and columns to the values of \(b\).

More than two variables can be used in a predicate. For example: \((a \oplus b) \land (a \land \neg c)\). The truth table must then include all possible combinations of values of the input variables:

#### Truth Table for \((a \oplus b) \land (a \land \neg c)\)
\[
\begin{array}{ccc|c}
a & b & c & (a \oplus b) \land (a \land \neg c) \\
\hline
0 & 0 & 0 & 0 \\
0 & 0 & 1 & 0 \\
0 & 1 & 0 & 0 \\
0 & 1 & 1 & 0 \\
1 & 0 & 0 & 1 \\
1 & 0 & 1 & 0 \\
1 & 1 & 0 & 0 \\
1 & 1 & 1 & 0 \\
\end{array}
\]

### Other Notations

In logic, there are various notational conventions. Instead of NOT \(a\), we can write:
\[ \neg a = \sim a = \overline{a} = -a \]

For other operators, there are also multiple notations:
\[ a \land b = a \cdot b = a \& b \]
\[ a \lor b = a + b = a \| b \]
\[ a \oplus b = a \text{ XOR } b = a \odot b \]

### Properties of Logical Operators

So far, we've covered the definitions of logical operators and their notations. An interesting question is what relationships hold between them. The basic properties are listed below:

#### Basic Properties of Logical Operators

| Property Name   | For AND              | For OR             |
|-----------------|----------------------|--------------------|
| Neutral elements| \( p \land 1 = p \)  | \( p \lor 0 = p \) |
| Extreme elements| \( p \land 0 = 0 \)  | \( p \lor 1 = 1 \) |
| Idempotence     | \( p \land p = p \)  | \( p \lor p = p \) |
| Complement      | \( p \land \neg p = 0 \) | \( p \lor \neg p = 1 \) |
| Commutativity   | \( p \land q = q \land p \) | \( p \lor q = q \lor p \) |
| Associativity   | \( (p \land q) \land r = p \land (q \land r) \) | \( (p \lor q) \lor r = p \lor (q \lor r) \) |
| Distributivity  | \( p \land (q \lor r) = (p \land q) \lor (p \land r) \) | \( p \lor (q \land r) = (p \lor q) \land (p \lor r) \) |
| Absorption      | \( (p \land q) \lor p = p \) | \( (p \lor q) \land p = p \) |
| De Morgan's laws| \( \neg(p \land q) = \neg p \lor \neg q \) | \( \neg(p \lor q) = \neg p \land \neg q \) |

These equalities can be validated by analyzing the truth tables for both sides and confirming that both sides have equal values, regardless of the input values of \(p\), \(q\), and \(r\).

The above table contains many well-known properties of standard multiplication and addition (e.g., commutativity, associativity, the first of the distributivity properties, etc.). This is why the convention of denoting AND, OR, true, and false respectively by ·, +, 1, and 0 is so intuitive. However, we must exercise caution, as not all rules of arithmetic hold for these symbols interpreted in the world of logic. For example, in logic, \(1 + 1 = 1\), which violates the standard arithmetic property that \(a + b = a\) necessarily implies \(b = 0\). On the other hand, compared to standard arithmetic, the operations + and · gain some new elegant properties in the world of logic, such as the second distributivity property and absorption.

### Boolean Functions

A Boolean function is a function from the set of possible valuations of Boolean variables to the set \(\{0, 1\}\). A Boolean variable is a variable that can take the value 0 or 1, and a valuation of a set of variables means a particular assignment of values (0 or 1) to each of them. Thus, equivalently, a Boolean function is just a truth table.

Notably, as typically in mathematics, a function is simply the assignment of return values to every choice of argument values, not the formula (or any other method) used to describe that assignment. For example, the two formulas below describe the same function:
\[ 
f(p, q) = \neg (( \neg p) \cdot q) \\
f(p, q) = ( \neg \neg \neg q) + p 
\]
because, for every choice of values \( p, q \in \{0, 1\} \), both formulas produce the same result.

### Describing Boolean Functions with Formulas

An interesting question is how to represent a given Boolean function with a particular formula. To do this, we can start by finding all the input variable valuations for which the function result is 1. For example, for the following truth table:

\[
\begin{array}{ccc|c}
a & b & c & f(a, b, c) \\
\hline
0 & 0 & 0 & 0 \\
0 & 0 & 1 & 1 \\
0 & 1 & 0 & 0 \\
0 & 1 & 1 & 0 \\
1 & 0 & 0 & 0 \\
1 & 0 & 1 & 1 \\
1 & 1 & 0 & 1 \\
1 & 1 & 1 & 0 \\
\end{array}
\]

There are exactly three valuations leading to result 1: (0, 0, 1), (1, 0, 1), and (1, 1, 0). For each of these valuations, we can easily produce a formula for the function that returns 1 only for that valuation:

For \((0, 0, 1)\):
\[ \neg a \cdot \neg b \cdot c = \overline{a} \cdot \overline{b} \cdot c \]

For \((1, 0, 1)\):
\[ a \cdot \neg b \cdot c = a \cdot \overline{b} \cdot c \]

For \((1, 1, 0)\):
\[ a \cdot b \cdot \neg c = a \cdot b \cdot \overline{c} \]

Using the OR operator (denoted here by \(+\)), we can build a formula representing our original truth table:
\[ 
f(a, b, c) = (\overline{a} \cdot \overline{b} \cdot c) + (a \cdot \overline{b} \cdot c) + (a \cdot b \cdot \overline{c}) 
\]

In this way, we can represent every Boolean function. Unfortunately, this does not have to be the shortest possible representation. To see this, consider a function taking four input variables which always returns 1 (or, to put it simply, is always true). The shortest formula describing such a function would be:
\[ 
f(a, b, c, d) = 1 
\]
Yet, our general method would produce a disjunction of 16 conjunctions:
\[ 
f(a, b, c, d) = (a \cdot b \cdot c \cdot d) + (\overline{a} \cdot b \cdot c \cdot d) + (a \cdot \overline{b} \cdot c \cdot d) + \ldots 
\]

The particular form of representation produced by the above method is called disjunctive normal form (DNF). It's always a disjunction whose arguments are conjunctions, whose arguments are either the input Boolean variables or their negations.

### NAND Alone Suffices

We have described how to represent an arbitrary Boolean function with a formula using three operators: NOT (\(\neg\)), AND (\(\cdot\)), and OR (\(+\)). Now, we'll show that all these operations can be represented just by NAND, of course, applied multiple times. This is the way to do it:

\[ 
\neg a = \neg (a \cdot a) = a \operatorname{NAND} a 
\]

\[ 
a \cdot b = \neg (a \operatorname{NAND} b) = (a \operatorname{NAND} b) \operatorname{NAND} (a \operatorname{NAND} b) 
\]

\[ 
a + b = \neg (\neg a \cdot \neg b) = (\neg a) \operatorname{NAND} (\neg b) = (a \operatorname{NAND} a) \operatorname{NAND} (b \operatorname{NAND} b) 
\]

So, there is a single logical operator which suffices to express all Boolean functions. This fact has practical implications because (as we'll discuss in the lecture on integrated circuits) it allows simplifying the design of integrated circuits.

### Can This Ever Be True?

Often, we face a problem in the opposite direction: given a Boolean function (represented by a formula), find a valuation of its arguments for which that function would return value 1. In other words, determine which input variables should be true and which should be false to make the whole expression true. Of course, that could be solved by computing the whole truth table. However, that requires some reflection on efficiency.

For one input variable, there are two possible valuations (either true or false). For two variables, there are 4 valuations (both true, or just the first one, or just the second one, or neither). For three variables, we have 8 valuations, then we get 16, 32, 64, etc. That is, the time needed for computations (also called the computational complexity of the program) is exponential in terms of the number of input variables.

### Why We Dislike the Exponential Function

An exponential function is a function of the form \( f(n) = A^n \), where \( A \) is some constant. In the above considerations, we're dealing with an exponential function with \( A = 2 \). That function is presented on the graph below (caution: the Y-axis has a drastically different scale than the X-axis):

```

```

#### Takeaway
The number of combinations that must be verified grows very fast. To realize how fast, let's assume that checking one valuation takes 1 ms (one millisecond). Then, for 22 input variables, the whole computation would take over 1 hour; for 39 variables, over 10 years; for 69 variables, more than the age of the universe (since the Big Bang)!

When we notice that we're up to performing an exponential amount of computation, it's always worth considering if we can solve the problem faster. Typically, the goal would be to reduce the necessary number of operations to less than \( B \cdot n^A \), where \( n \) is the number of input data (in our case, the number of input variables), and \( A \) and \( B \) are some constants (of course, the smaller, the better). Such complexity is called polynomial. The difference between the exponential and polynomial growth rates is shown by the following graphs (again, watch out for the scale on the Y-axis):

```

```

The graph on the left shows that (for sufficiently large values of \( n \), starting from just about 15) the value of \( 2^n \) greatly exceeds not only common polynomials like \( n^2 \) or \( n^3 \), but even their multiplicities by constants like 100 or 1,000.

Moreover, the situation does not change significantly even after increasing the power exponent. Even if, looking at the graph on the left, it might seem that \( 2^n \) "loses the race" against \( n^7 \), this turns out just to be a matter of scale, as can be clearly seen on the graph on the right. In general, for every exponent \( A \) and multiplier \( B \), taking a sufficiently large \( n \), we will obtain \( 2^n > B \cdot n^A \). That's why the theory of complexity says that "exponential functions grow faster than all polynomial functions."

### Finding the Truth Is Hard

After this long digression, we can come back to our problem of finding a valuation for which the given Boolean function returns true. Now, we have bad news. It's a problem that has attracted a lot of scientific attention; yet, we still do not know if there exists an algorithm solving that problem in polynomial time. Although these remarks are not constructive, it's good to be aware of them, as it's always better to know upfront what can cause efficiency troubles in programming.

For those interested: Just deciding, given a Boolean function, whether there exists a valuation leading to a true result, known in computer science as the satisfiability problem, belongs to the class of NP-complete problems, for which we know no way of solving in polynomial time.

Certainly! Here's the corrected content in Markdown format suitable for GitHub, along with recreated schematics for the logic gates using LaTeX:

```markdown
# Integrated Circuits

## Theoretical Grounds for Constructing the Computer Processor
In this lecture, we will bridge the gap between theory and practice.

## Basic Building Blocks

### Transistors
Early computers utilized vacuum tubes, which were inefficient in terms of size, reliability, and energy consumption. The technological revolution began in the late 1940s with the invention of the first transistors. While the detailed electronic description of a transistor is beyond the scope of this course, it's important to note that transistors can control an electric signal. This means that by choosing the voltage in one electric circuit, we can influence the voltage in another. Transistors allow us to:

- Choose the nature of signal propagation: depending on the transistor, a higher voltage on the input can cause either a higher or lower voltage on the output.
- Amplify voltage changes: the range of output voltage values is broader than the range of input values. This allows for the combination of transistors into arbitrarily large integrated circuits without losing the original signal.

### Electric Current and Digital Information Storage
A low voltage (approximately 0 V) is interpreted as '0', while a high voltage (approximately 5 V) is interpreted as '1'. Voltage values in between occur briefly and do not influence computations.

### Logic Gates
Transistors effectively open or close electric circuits depending on the values of input signals. Combining a few transistors can create what are known as logic gates. A logic gate manipulates electric signals according to a logic operation. It reacts to the input signals (voltage levels, interpreted as '0' or '1') and ensures that the output pin reflects the appropriate signal, corresponding to the result of the logic function. For example, the AND function is implemented by the AND gate, which takes two input signals (A and B) and generates the output signal (C = A AND B).

Logic gates, particularly AND, OR, NOT, NAND, and NOR, are considered the basic building blocks for constructing more complex integrated circuits. Diagrams of such circuits typically contain symbols denoting various types of logic gates.

#### Schematics for Logic Gates

Here are the schematics for some of the most common logic gates:

- **AND Gate**:
  $$
  \begin{array}{c}
  \text{A} \\
  \text{B} \\
  \hline
  \text{C} \\
  \end{array}
  \quad
  \begin{array}{c}
  \text{AND} \\
  \end{array}
  $$

- **NOT Gate**:
  $$
  \begin{array}{c}
  \text{A} \\
  \hline
  \overline{\text{A}} \\
  \end{array}
  \quad
  \begin{array}{c}
  \text{NOT} \\
  \end{array}
  $$

- **OR Gate**:
  $$
  \begin{array}{c}
  \text{A} \\
  \text{B} \\
  \hline
  \text{A + B} \\
  \end{array}
  \quad
  \begin{array}{c}
  \text{OR} \\
  \end{array}
  $$

- **XOR Gate**:
  $$
  \begin{array}{c}
  \text{A} \\
  \text{B} \\
  \hline
  \text{A} \oplus \text{B} \\
  \end{array}
  \quad
  \begin{array}{c}
  \text{XOR} \\
  \end{array}
  $$

- **NAND Gate**:
  $$
  \begin{array}{c}
  \text{A} \\
  \text{B} \\
  \hline
  \overline{\text{A} \cdot \text{B}} \\
  \end{array}
  \quad
  \begin{array}{c}
  \text{NAND} \\
  \end{array}
  $$

- **NOR Gate**:
  $$
  \begin{array}{c}
  \text{A} \\
  \text{B} \\
  \hline
  \overline{\text{A + B}} \\
  \end{array}
  \quad
  \begin{array}{c}
  \text{NOR} \\
  \end{array}
  $$
```

