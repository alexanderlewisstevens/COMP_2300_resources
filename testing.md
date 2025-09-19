
## The Foundations: Logic and Proofs

### Topics Covered
- **Propositional Logic**
- Applications of Propositional Logic
- Propositional Equivalences
- Predicates and Quantifiers
- Nested Quantifiers
- Rules of Inference
- Introduction to Proofs
- Proof Methods and Strategy

---

The rules of logic specify the meaning of mathematical statements. For instance, these rules help us understand and reason with statements such as "There exists an integer that is not the sum of two squares" and "For every positive integer $n$, the sum of the positive integers not exceeding $n$ is $n(n+1)/2$." Logic is the basis of all mathematical reasoning and of all automated reasoning. It has practical applications to the design of computing machines, to the specification of systems, to artificial intelligence, to computer programming, to programming languages, and to other areas of computer science, as well as to many other fields of study.

To understand mathematics, we must understand what makes up a correct mathematical argument, that is, a proof. Once we prove a mathematical statement is true, we call it a theorem. A collection of theorems on a topic organizes what we know about this topic. To learn a mathematical topic, a person needs to actively construct mathematical arguments on this topic, and not just read exposition. Moreover, knowing the proof of a theorem often makes it possible to modify the result to fit new situations.

> Everyone knows that proofs are important throughout mathematics, but many people find it surprising how important proofs are in computer science. In fact, proofs are used to verify that computer programs produce the correct output for all possible input values, to show that algorithms always produce the correct result, to establish the security of a system, and to create artificial intelligence. Furthermore, automated reasoning systems have been created to allow computers to construct their own proofs.

In this chapter, we will explain what makes up a correct mathematical argument and introduce tools to construct these arguments. We will develop an arsenal of different proof methods that will enable us to prove many different types of results. After introducing many different methods of proof, we will introduce several strategies for constructing proofs. We will introduce the notion of a conjecture and explain the process of developing mathematics by studying conjectures.

### 1.1 Propositional Logic

#### Introduction

The rules of logic give precise meaning to mathematical statements. These rules are used to distinguish between valid and invalid mathematical arguments. Because a major goal of this book is to teach the reader how to understand and how to construct correct mathematical arguments, we begin our study of discrete mathematics with an introduction to logic.

Besides the importance of logic in understanding mathematical reasoning, logic has numerous applications to computer science. These rules are used in the design of computer circuits, the construction of computer programs, the verification of the correctness of programs, and in many other ways. Furthermore, software systems have been developed for constructing some, but not all, types of proofs automatically. We will discuss these applications of logic in this and later chapters.

## The Foundations: Logic and Proofs

### Propositions

Our discussion begins with an introduction to the basic building blocks of logic—**propositions**. A proposition is a declarative sentence (that is, a sentence that declares a fact) that is either true or false, but not both.

**Example 1**: All the following declarative sentences are propositions.

1. Washington, D.C., is the capital of the United States of America.
2. Toronto is the capital of Canada.
3. $1+1=2$.
4. $2+2=3$.

Propositions 1 and 3 are true, whereas 2 and 4 are false.

Some sentences that are not propositions are given in Example 2.

**Example 2**: Consider the following sentences.

1. What time is it?
2. Read this carefully.
3. $x+1=2$.
4. $x+y=z$.

Sentences 1 and 2 are not propositions because they are not declarative sentences. Sentences 3 and 4 are not propositions because they are neither true nor false. Note that each of sentences 3 and 4 can be turned into a proposition if we assign values to the variables. We will also discuss other ways to turn sentences such as these into propositions in Section 1.4.


We use letters to denote propositional variables (or statement variables), that is, variables that represent propositions, just as letters are used to denote numerical variables.

---

## Propositional Logic

Conventional letters used for propositional variables are $p, q, r, s, \ldots$. The **truth value** of a proposition is **true**, denoted by $T$, if it is a true proposition, and the truth value of a proposition is **false**, denoted by $F$, if it is a false proposition.

The area of logic that deals with propositions is called the **propositional calculus** or **propositional logic**. It was first developed systematically by the Greek philosopher Aristotle more than 2300 years ago.

We now turn our attention to methods for producing new propositions from those that we already have. These methods were discussed by the English mathematician George Boole in 1854 in his book *The Laws of Thought*. Many mathematical statements are constructed by combining one or more propositions. New propositions, called **compound propositions**, are formed from existing propositions using logical operators.

### Definition

**Definition 1**: Let $p$ be a proposition. The **negation** of $p$, denoted by $\neg p$ (also denoted by $\sim p$), is the statement "It is not the case that $p$." The proposition $\neg p$ is read "not $p$." The truth value of the negation of $p$, $\neg p$, is the opposite of the truth value of $p$.

### Examples

**Example 3**: Find the negation of the proposition "Michael’s PC runs Linux" and express this in simple English.

**Solution**: The negation is "It is not the case that Michael’s PC runs Linux." This negation can be more simply expressed as "Michael’s PC does not run Linux."

---

**Example 4**: Find the negation of the proposition "Vandana’s smartphone has at least 32GB of memory" and express this in simple English.

**Solution**: The negation is "It is not the case that Vandana’s smartphone has at least 32GB of memory." This negation can also be expressed as "Vandana’s smartphone does not have at least 32GB of memory" or even more simply as "Vandana’s smartphone has less than 32GB of memory."

## The Foundations: Logic and Proofs

### Negation of a Proposition

Table 1 displays the truth table for the negation of a proposition $p$. This table has a row for each of the two possible truth values of a proposition $p$. Each row shows the truth value of $\neg p$ corresponding to the truth value of $p$ for this row.

| $p$ | $\neg p$ |
|-----|----------|
| T   | F        |
| F   | T        |

The negation of a proposition can also be considered the result of the operation of the negation operator on a proposition. The negation operator constructs a new proposition from a single existing proposition. We will now introduce the logical operators that are used to form new propositions from two or more existing propositions. These logical operators are also called **connectives**.

### Conjunction

**Definition 2:** Let $p$ and $q$ be propositions. The conjunction of $p$ and $q$, denoted by $p \land q$, is the proposition "p and q." The conjunction $p \land q$ is true when both $p$ and $q$ are true and is false otherwise.

Table 2 displays the truth table of $p \land q$. This table has a row for each of the four possible combinations of truth values of $p$ and $q$. The four rows correspond to the pairs of truth values TT, TF, FT, and FF, where the first truth value in the pair is the truth value of $p$ and the second truth value is the truth value of $q$.

| $p$ | $q$ | $p \land q$ |
|-----|-----|-------------|
| T   | T   | T           |
| T   | F   | F           |
| F   | T   | F           |
| F   | F   | F           |

> Note: In logic, the word "but" sometimes is used instead of "and" in a conjunction. For example, the statement "The sun is shining, but it is raining" is another way of saying "The sun is shining and it is raining." (In natural language, there is a subtle difference in meaning between "and" and "but"; we will not be concerned with this nuance here.)

**Example 5:**  
Find the conjunction of the propositions $p$ and $q$ where $p$ is the proposition "Rebecca’s PC has more than 16 GB free hard disk space" and $q$ is the proposition "The processor in Rebecca’s PC runs faster than 1 GHz."

**Solution:**  
The conjunction of these propositions, $p \land q$, is the proposition "Rebecca’s PC has more than 16 GB free hard disk space, and the processor in Rebecca’s PC runs faster than 1 GHz." This conjunction can be expressed more simply as "Rebecca’s PC has more than 16 GB free hard disk space, and its processor runs faster than 1 GHz." For this conjunction to be true, both conditions given must be true. It is false when one or both of these conditions are false.

---

### Disjunction

**Definition 3:** Let $p$ and $q$ be propositions. The disjunction of $p$ and $q$, denoted by $p \lor q$, is the proposition "p or q." The disjunction $p \lor q$ is false when both $p$ and $q$ are false and is true otherwise.

Table 3 displays the truth table for $p \lor q$.

| $p$ | $q$ | $p \lor q$ |
|-----|-----|------------|
| T   | T   | T          |
| T   | F   | T          |
| F   | T   | T          |
| F   | F   | F          |



The use of the connective 'or' in a disjunction corresponds to one of the two ways the word 'or' is used in English, namely, as an inclusive 'or'. A disjunction is true when at least one of the two propositions is true. 

For instance, the inclusive 'or' is used in the statement:

> "Students who have taken calculus or computer science can take this class."

Here, it means that students who have taken both calculus and computer science can take the class, as well as students who have taken only one of the two subjects.

On the other hand, the exclusive 'or' is used when we say:

> "Students who have taken calculus or computer science, but not both, can enroll in this class."

Here, it means that students who have taken both calculus and computer science cannot take the class. Only those who have taken exactly one of the two courses can take the class.

Similarly, when a menu at a restaurant states, "Soup or salad comes with an entrée," it almost always means that customers can have either soup or salad, but not both. Hence, this is an exclusive, rather than an inclusive, 'or'.

### Example 6

**What is the disjunction of the propositions $p$ and $q$, where $p$ and $q$ are the same propositions as in Example 5?**

**Solution:** The disjunction of $p$ and $q$, $p \lor q$, is the proposition:

> "Rebecca’s PC has at least 16 GB free hard disk space, or the processor in Rebecca’s PC runs faster than 1 GHz."

This proposition is true when Rebecca’s PC has at least 16 GB free hard disk space, when the PC’s processor runs faster than 1 GHz, and when both conditions are true. It is false when both of these conditions are false, that is, when Rebecca’s PC has less than 16 GB free hard disk space and the processor in her PC runs at 1 GHz or slower.

As was previously remarked, the use of the connective 'or' in a disjunction corresponds to one of the two ways the word 'or' is used in English, namely, in an inclusive way. Thus, a disjunction is true when at least one of the two propositions in it is true. Sometimes, we use 'or' in an exclusive sense. When the exclusive 'or' is used to connect the propositions $p$ and $q$, the proposition " $p$ or $q$ (but not both)" is obtained. This proposition is true when $p$ is true and $q$ is false, and when $p$ is false and $q$ is true. It is false when both $p$ and $q$ are false and when both are true.

## The Foundations: Logic and Proofs

### Exclusive Or

**Definition 4:** Let $p$ and $q$ be propositions. The exclusive or of $p$ and $q$, denoted by $p \oplus q$, is the proposition that is true when exactly one of $p$ and $q$ is true and is false otherwise.

> The truth table for the exclusive or of two propositions is displayed in Table 4.

**Table 4: The Truth Table for the Exclusive Or of Two Propositions**

| $p$ | $q$ | $p \oplus q$ |
|-----|-----|--------------|
| T   | T   | F            |
| T   | F   | T            |
| F   | T   | T            |
| F   | F   | F            |

---

### Conditional Statements

We will discuss several other important ways in which propositions can be combined.

**Definition 5:** Let $p$ and $q$ be propositions. The conditional statement $p \to q$ is the proposition “if $p$, then $q$.” The conditional statement $p \to q$ is false when $p$ is true and $q$ is false, and true otherwise. In the conditional statement $p \to q$, $p$ is called the hypothesis (or antecedent or premise) and $q$ is called the conclusion (or consequence).

> The statement $p \to q$ is called a conditional statement because $p \to q$ asserts that $q$ is true on the condition that $p$ holds. A conditional statement is also called an implication.

**Table 5: The Truth Table for the Conditional Statement $p \to q$**

| $p$ | $q$ | $p \to q$ |
|-----|-----|-----------|
| T   | T   | T         |
| T   | F   | F         |
| F   | T   | T         |
| F   | F   | T         |

> Note that the statement $p \to q$ is true when both $p$ and $q$ are true and when $p$ is false (no matter what truth value $q$ has).

Because conditional statements play such an essential role in mathematical reasoning, a variety of terminology is used to express $p \to q$. You will encounter most if not all of the following ways to express this conditional statement:

- “if $p$, then $q$”
- “$p$ implies $q$”
- “if $p$, $q$”
- “$p$ only if $q$”
- “$p$ is sufficient for $q$”
- “a sufficient condition for $q$ is $p$”
- “$q$ if $p$”
- “$q$ whenever $p$”
- “$q$ when $p$”
- “$q$ is necessary for $p$”
- “a necessary condition for $p$ is $q$”
- “$q$ follows from $p$”
- “$q$ unless $\neg p$”

> A useful way to understand the truth value of a conditional statement is to think of an obligation or a contract. For example, the pledge many politicians make when running for office is “If I am elected, then I will lower taxes.”


If the politician is elected, voters would expect this politician to lower taxes. Furthermore, if the politician is not elected, then voters will not have any expectation that this person will lower taxes, although the person may have sufficient influence to cause those in power to lower taxes. It is only when the politician is elected but does not lower taxes that voters can say that the politician has broken the campaign pledge. This last scenario corresponds to the case when $p$ is true but $q$ is false in $p \to q$.

Similarly, consider a statement that a professor might make:

> "If you get 100% on the final, then you will get an A."

If you manage to get a 100% on the final, then you would expect to receive an A. If you do not get 100%, you may or may not receive an A depending on other factors. However, if you do get 100%, but the professor does not give you an A, you will feel cheated.

Of the various ways to express the conditional statement $p \to q$, the two that seem to cause the most confusion are "p only if q" and "q unless ¬p." Consequently, we will provide some guidance for clearing up this confusion.

- To remember that "p only if q" expresses the same thing as "if p, then q," note that "p only if q" says that $p$ cannot be true when $q$ is not true. That is, the statement is false if $p$ is true, but $q$ is false. When $p$ is false, $q$ may be either true or false, because the statement says nothing about the truth value of $q$. Be careful not to use "q only if p" to express $p \to q$ because this is incorrect. To see this, note that the true values of "q only if p" and $p \to q$ are different when $p$ and $q$ have different truth values.

> You might have trouble understanding how "unless" is used in conditional statements unless you read this paragraph carefully.

- To remember that "q unless ¬p" expresses the same conditional statement as "if p, then q," note that "q unless ¬p" means that if ¬$p$ is false, then $q$ must be true. That is, the statement "q unless ¬p" is false when $p$ is true but $q$ is false, but it is true otherwise. Consequently, "q unless ¬p" and $p \to q$ always have the same truth value.

### Example 7

Let $p$ be the statement "Maria learns discrete mathematics" and $q$ the statement "Maria will find a good job." Express the statement $p \to q$ as a statement in English.

**Solution:** From the definition of conditional statements, we see that when $p$ is the statement "Maria learns discrete mathematics" and $q$ is the statement "Maria will find a good job," $p \to q$ represents the statement

> "If Maria learns discrete mathematics, then she will find a good job."

There are many other ways to express this conditional statement in English. Among the most natural of these are:

- "Maria will find a good job when she learns discrete mathematics."
- "For Maria to get a good job, it is sufficient for her to learn discrete mathematics."
- "Maria will find a good job unless she does not learn discrete mathematics."

---

Note that the way we have defined conditional statements is more general than the meaning attached to such statements in the English language. For instance, the conditional statement in Example 7 and the statement

> "If it is sunny, then we will go to the beach."

are statements used in normal language where there is a relationship between the hypothesis and the conclusion. Further, the first of these statements is true unless Maria learns discrete mathematics, but she does not get a good job, and the second is true unless it is indeed sunny, but we do not go to the beach.

## The Foundations: Logic and Proofs

The statement “If Juan has a smartphone, then $2 + 3 = 5$” is true from the definition of a conditional statement, because its conclusion is true. The truth value of the hypothesis does not matter in this case. Conversely, the conditional statement “If Juan has a smartphone, then $2 + 3 = 6$” is true if Juan does not have a smartphone, despite $2 + 3 = 6$ being false. 

> We would not typically use these last two conditional statements in natural language, except perhaps sarcastically, because there is no relationship between the hypothesis and the conclusion in either statement. In mathematical reasoning, we consider conditional statements more generally than in English. The mathematical concept of a conditional statement is independent of any cause-and-effect relationship between hypothesis and conclusion. Our definition specifies its truth values and is not based on English usage.

---

### Converse, Contrapositive, and Inverse

We can form new conditional statements starting with a conditional statement $p \to q$. There are three related conditional statements that occur often and have special names:

- **Converse:** $q \to p$
- **Contrapositive:** $\neg q \to \neg p$
- **Inverse:** $\neg p \to \neg q$

The contrapositive, $\neg q \to \neg p$, always has the same truth value as $p \to q$. The converse and the inverse do not always share the same truth value with $p \to q$. 

- The contrapositive is false only when $\neg p$ is false and $\neg q$ is true, that is, when $p$ is true and $q$ is false.
- Note that when $p$ is true and $q$ is false, the original conditional statement is false, but the converse and the inverse are both true.

Remember, a conditional statement and its contrapositive are equivalent. Equivalent propositions always have the same truth value. While the converse and inverse are equivalent to each other, neither is equivalent to the original conditional statement. A common logical error is assuming the converse or inverse of a conditional statement is equivalent to the original statement.

We further illustrate the use of conditional statements in Example 9.


### Example 9

What are the contrapositive, the converse, and the inverse of the conditional statement, "The home team wins whenever it is raining?"

**Solution:**  
Because "q whenever p" is one of the ways to express the conditional statement $p \to q$, the original statement can be rewritten as:  
"If it is raining, then the home team wins."

- **Contrapositive:**  
  "If the home team does not win, then it is not raining."

- **Converse:**  
  "If the home team wins, then it is raining."

- **Inverse:**  
  "If it is not raining, then the home team does not win."

> Only the contrapositive is equivalent to the original statement.

---

### Biconditionals

We now introduce another way to combine propositions that expresses that two propositions have the same truth value.

#### Definition 6

Let $p$ and $q$ be propositions. The biconditional statement $p \leftrightarrow q$ is the proposition "p if and only if q." The biconditional statement $p \leftrightarrow q$ is true when $p$ and $q$ have the same truth values, and is false otherwise. Biconditional statements are also called **bi-implications**.

The truth table for $p \leftrightarrow q$ is shown in Table 6. Note that the statement $p \leftrightarrow q$ is true when both the conditional statements $p \to q$ and $q \to p$ are true and is false otherwise. That is why we use the words "if and only if" to express this logical connective and why it is symbolically written by combining the symbols $\to$ and $\leftarrow$.

There are some other common ways to express $p \leftrightarrow q$:  
- "p is necessary and sufficient for q"
- "if p then q, and conversely"
- "p iff q."

The last way of expressing the biconditional statement $p \leftrightarrow q$ uses the abbreviation "iff" for "if and only if." Note that $p \leftrightarrow q$ has exactly the same truth value as $(p \to q) \land (q \to p)$.

#### Table 6: The Truth Table for the Biconditional $p \leftrightarrow q$

| $p$ | $q$ | $p \leftrightarrow q$ |
|-----|-----|-----------------------|
| T   | T   | T                     |
| T   | F   | F                     |
| F   | T   | F                     |
| F   | F   | T                     |

## Example 10

Let $p$ be the statement "You can take the flight," and let $q$ be the statement "You buy a ticket." Then $p \leftrightarrow q$ is the statement:
"You can take the flight if and only if you buy a ticket."

This statement is true if $p$ and $q$ are either both true or both false, that is, if you buy a ticket and can take the flight or if you do not buy a ticket and you cannot take the flight. It is false when $p$ and $q$ have opposite truth values, that is, when you do not buy a ticket, but you can take the flight (such as when you get a free trip) and when you buy a ticket but you cannot take the flight (such as when the airline bumps you).

> You should be aware that biconditionals are not always explicit in natural language. In particular, the "if and only if" construction used in biconditionals is rarely used in common language. Instead, biconditionals are often expressed using an "if, then" or an "only if" construction. The other part of the "if and only if" is implicit. That is, the converse is implied but not stated. For example, consider the statement in English "If you finish your meal, then you can have dessert." What is really meant is "You can have dessert if and only if you finish your meal." This last statement is logically equivalent to the two statements "If you finish your meal, then you can have dessert" and "You can have dessert only if you finish your meal." Because of this imprecision in natural language, we need to make an assumption whether a conditional statement in natural language implicitly includes its converse. Because precision is essential in mathematics and in logic, we will always distinguish between the conditional statement $p \rightarrow q$ and the biconditional statement $p \leftrightarrow q$.

## Truth Tables of Compound Propositions

We have now introduced four important logical connectives—conjunctions, disjunctions, conditional statements, and biconditional statements—as well as negations. We can use these connectives to build up complicated compound propositions involving any number of propositional variables. We can use truth tables to determine the truth values of these compound propositions, as Example 11 illustrates. We use a separate column to find the truth value of each compound expression that occurs in the compound proposition as it is built up. The truth values of the compound proposition for each combination of truth values of the propositional variables in it are found in the final column of the table.

### Example 11

Construct the truth table of the compound proposition $(p \lor \neg q) \rightarrow (p \land q)$.

**Solution:** Because this truth table involves two propositional variables $p$ and $q$, there are four rows in this truth table, one for each of the pairs of truth values TT, TF, FT, and FF. The first two columns are used for the truth values of $p$ and $q$, respectively. In the third column, we find the truth value of $\neg q$, needed to find the truth value of $p \lor \neg q$, found in the fourth column. The fifth column gives the truth value of $p \land q$. Finally, the truth value of $(p \lor \neg q) \rightarrow (p \land q)$ is found in the last column. The resulting truth table is shown in Table 7.

---

**Table 7: The Truth Table of $(p \lor \neg q) \rightarrow (p \land q)$.**

| $p$ | $q$ | $\neg q$ | $p \lor \neg q$ | $p \land q$ | $(p \lor \neg q) \rightarrow (p \land q)$ |
|---------|---------|--------------|---------------------|-----------------|--------------------------------------------|
| T       | T       | F            | T                   | T               | T                                          |
| T       | F       | T            | T                   | F               | F                                          |
| F       | T       | F            | F                   | F               | T                                          |
| F       | F       | T            | T                   | F               | F                                          |

## Precedence of Logical Operators

We can construct compound propositions using the negation operator and other logical operators. Parentheses are typically used to specify the order of operations in a compound proposition. For example, $(p \vee q) \wedge (\neg r)$ is the conjunction of $p \vee q$ and $\neg r$. 

However, to minimize parentheses, the following precedence rules are applied:
- The negation operator (`¬`) is applied before all other logical operators. So, `¬p ∧ q` is equivalent to `(¬p) ∧ q`, not `¬(p ∧ q)`.
- The conjunction operator (`∧`) takes precedence over the disjunction operator (`∨`). Hence, `p ∧ q ∨ r` means `(p ∧ q) ∨ r` rather than `p ∧ (q ∨ r)`.

To ensure clarity, parentheses will still be used for the order of disjunction and conjunction operators.

### Operator Precedence Table

| Operator | Precedence |
|----------|------------|
| ¬        | 1          |
| ∧        | 2          |
| ∨        | 3          |
| →        | 4          |
| ↔        | 5          |

The conditional (`→`) and biconditional (`↔`) operators have lower precedence than conjunction and disjunction operators. Consequently, `p ∨ q → r` is the same as `(p ∨ q) → r`. Parentheses will be used where necessary, as the conditional operator has precedence over the biconditional operator.


## The Foundations: Logic and Proofs

### Bit Operators: OR, AND, and XOR

| x | y | $x \lor y$ | $x \land y$ | $x \oplus y$ |
|---|---|-----------|------------|------------|
| 0 | 0 | 0         | 0          | 0          |
| 0 | 1 | 1         | 0          | 1          |
| 1 | 0 | 1         | 0          | 1          |
| 1 | 1 | 1         | 1          | 0          |

Information is often represented using bit strings, which are lists of zeros and ones. When this is done, operations on the bit strings can be used to manipulate this information.

**Definition 7**: A bit string is a sequence of zero or more bits. The length of this string is the number of bits in the string.

**Example 12**: `101010011` is a bit string of length nine.

We can extend bit operations to bit strings. We define the bitwise OR, bitwise AND, and bitwise XOR of two strings of the same length to be the strings that have as their bits the OR, AND, and XOR of the corresponding bits in the two strings, respectively. We use the symbols $\lor$, $\land$, and $\oplus$ to represent the bitwise OR, bitwise AND, and bitwise XOR operations, respectively.

**Example 13**: Find the bitwise OR, bitwise AND, and bitwise XOR of the bit strings `0110110110` and `1100011101`. 

Solution: The bitwise OR, bitwise AND, and bitwise XOR of these strings are obtained by taking the OR, AND, and XOR of the corresponding bits, respectively. This gives us:

```
0110110110
1100011101
-----------
1110111111 bitwise OR
0100010100 bitwise AND
1010101011 bitwise XOR
```

### Exercises

#### 1. Which of these sentences are propositions? What are the truth values of those that are propositions?
   - a) Boston is the capital of Massachusetts.
   - b) Miami is the capital of Florida.
   - c) $2 + 3 = 5$.
   - d) $5 + 7 = 10$.
   - e) $x + 2 = 11$.
   - f) Answer this question.

#### 2. Which of these are propositions? What are the truth values of those that are propositions?
   - a) Do not pass go.
   - b) What time is it?
   - c) There are no black flies in Maine.
   - d) $4 + x = 5$.
   - e) The moon is made of green cheese.
   - f) $2^n \ge 100$.

#### 3. What is the negation of each of these propositions?
   - a) Mei has an MP3 player.
   - b) There is no pollution in New Jersey.
   - c) $2 + 1 = 3$.
   - d) The summer in Maine is hot and sunny.

#### 4. What is the negation of each of these propositions?
- a) Jennifer and Teja are friends.
   - b) There are 13 items in a baker’s dozen.
   - c) Abby sent more than 100 text messages every day.
   - d) 121 is a perfect square.


#### 5. Negation of Propositions

What is the negation of each of these propositions?

- a) Steve has more than 100 GB free disk space on his laptop.
- b) Zach blocks e-mails and texts from Jennifer.
- c) $7 \cdot 11 \cdot 13 = 999$.
- d) Diane rode her bicycle 100 miles on Sunday.

#### 6. Determining Truth Values for Smartphone Specifications

Suppose:

- Smartphone A: 256 MB RAM, 32 GB ROM, 8 MP camera
- Smartphone B: 288 MB RAM, 64 GB ROM, 4 MP camera
- Smartphone C: 128 MB RAM, 32 GB ROM, 5 MP camera

Determine the truth value of each proposition:

- a) Smartphone B has the most RAM of these three smartphones.
- b) Smartphone C has more ROM or a higher resolution camera than Smartphone B.
- c) Smartphone B has more RAM, more ROM, and a higher resolution camera than Smartphone A.
- d) If Smartphone B has more RAM and more ROM than Smartphone C, then it also has a higher resolution camera.
- e) Smartphone A has more RAM than Smartphone B if and only if Smartphone B has more RAM than Smartphone A.

#### 7. Company Financial Analysis

Suppose for the most recent fiscal year:

- Acme Computer: Annual revenue of 138 billion dollars, net profit of 8 billion dollars
- Nadir Software: Annual revenue of 87 billion dollars, net profit of 5 billion dollars
- Quixote Media: Annual revenue of 111 billion dollars, net profit of 13 billion dollars

Determine the truth value of each proposition:

- a) Quixote Media had the largest annual revenue.
- b) Nadir Software had the lowest net profit and Acme Computer had the largest annual revenue.
- c) Acme Computer had the largest net profit or Quixote Media had the largest net profit.
- d) If Quixote Media had the smallest net profit, then Acme Computer had the largest annual revenue.
- e) Nadir Software had the smallest net profit if and only if Acme Computer had the largest annual revenue.

#### 8. Lottery Propositions

Let $p$ and $q$ be the propositions:

- $p$: I bought a lottery ticket this week.
- $q$: I won the million dollar jackpot.

Express each proposition as an English sentence:

- a) $\neg p$
- b) $p \lor q$
- c) $p \to q$
- d) $p \land q$
- e) $p \leftrightarrow q$
- f) $\neg p \to \neg q$
- g) $\neg p \land \neg q$
- h) $\neg p \lor (p \land q)$

#### 9. Swimming and Sharks Propositions

Let $p$ and $q$ be the propositions:

- $p$: Swimming at the New Jersey shore is allowed.
- $q$: Sharks have been spotted near the shore.

Express each compound proposition as an English sentence:

- a) $\neg q$
- b) $p \land q$
- c) $\neg p \lor q$
- d) $p \to \neg q$
- e) $\neg q \to p$
- f) $\neg p \to \neg q$
- g) $p \leftrightarrow \neg q$
- h) $\neg p \land (p \lor \neg q)$

#### 10. Election Propositions

Let $p$ and $q$ be the propositions:

- $p$: The election is decided.
- $q$: The votes have been counted.

Express each compound proposition as an English sentence:

- a) $\neg p$
- b) $p \lor q$
- c) $\neg p \land q$
- d) $q \to p$
- e) $\neg q \to \neg p$
- f) $\neg p \to \neg q$
- g) $p \leftrightarrow q$
- h) $\neg q \lor (\neg p \land q)$

#### 11. Weather Propositions

Let $p$ and $q$ be the propositions:

- $p$: It is below freezing.
- $q$: It is snowing.

Write these propositions using $p$, $q$, and logical connectives:

- a) It is below freezing and snowing.
- b) It is below freezing but not snowing.
- c) It is not below freezing and it is not snowing.
- d) It is either snowing or below freezing (or both).
- e) If it is below freezing, it is also snowing.
- f) Either it is below freezing or it is snowing, but it is not snowing if it is below freezing.
- g) That it is below freezing is necessary and sufficient for it to be snowing.

#### 12. Flu, Exams, and Passing Propositions

Let $p$, $q$, and $r$ be the propositions:

- $p$: You have the flu.
- $q$: You miss the final examination.
- $r$: You pass the course.

Express each proposition as an English sentence:

- a) $p \to q$
- b) $\neg q \leftrightarrow r$
- c) $q \to \neg r$
- d) $p \lor q \lor r$
- e) $(p \to \neg r) \lor (q \to \neg r)$
- f) $(p \land q) \lor (\neg q \land r)$

#### 13. Driving and Speeding Propositions

Let $p$ and $q$ be the propositions:

- $p$: You drive over 65 miles per hour.
- $q$: You get a speeding ticket.

Write these propositions using $p$, $q$, and logical connectives:

- a) You do not drive over 65 miles per hour.
- b) You drive over 65 miles per hour, but you do not get a speeding ticket.
- c) You will get a speeding ticket if you drive over 65 miles per hour.
- d) If you do not drive over 65 miles per hour, then you will not get a speeding ticket.
- e) Driving over 65 miles per hour is sufficient for getting a speeding ticket.
- f) You get a speeding ticket, but you do not drive over 65 miles per hour.
- g) Whenever you get a speeding ticket, you are driving over 65 miles per hour.

#### 14. Academic Achievement Propositions

Let $p$, $q$, and $r$ be the propositions:

- $p$: You get an A on the final exam.
- $q$: You do every exercise in this book.
- $r$: You get an A in this class.

Write these propositions using $p$, $q$, $r$, and logical connectives.

- You get an A in this class, but you do not do every exercise in this book.
- You get an A on the final, you do every exercise in this book, and you get an A in this class.
- To get an A in this class, it is necessary for you to get an A on the final.
- You get an A on the final, but you don’t do every exercise in this book; nevertheless, you get an A in this class.
- Getting an A on the final and doing every exercise in this book is sufficient for getting an A in this class.
- You will get an A in this class if and only if you either do every exercise in this book or you get an A on the final.

---

#### Exercise 15: Propositions with Logical Connectives

Let $p$, $q$, and $r$ be the propositions:
- $p$: Grizzly bears have been seen in the area.
- $q$: Hiking is safe on the trail.
- $r$: Berries are ripe along the trail.

Translate the following statements:

- Berries are ripe along the trail, but grizzly bears have not been seen in the area.
- Grizzly bears have not been seen in the area and hiking on the trail is safe, but berries are ripe along the trail.
- If berries are ripe along the trail, hiking is safe if and only if grizzly bears have not been seen in the area.
- It is not safe to hike on the trail, but grizzly bears have not been seen in the area and the berries along the trail are ripe.
- For hiking on the trail to be safe, it is necessary but not sufficient that berries not be ripe along the trail and for grizzly bears not to have been seen in the area.
- Hiking is not safe on the trail whenever grizzly bears have been seen in the area and berries are ripe along the trail.

---

#### Exercise 16: Truth of Biconditionals

Determine whether these biconditionals are true or false:

1. $2+2=4$ if and only if $1+1=2$.
2. $1+1=2$ if and only if $2+3=4$.
3. $1+1=3$ if and only if monkeys can fly.
4. $0>1$ if and only if $2>1$.

---

#### Exercise 17: Truth of Conditional Statements

Determine whether each of these conditional statements is true or false:

1. If $1+1=2$, then $2+2=5$.
2. If $1+1=3$, then $2+2=4$.
3. If $1+1=3$, then $2+2=5$.
4. If monkeys can fly, then $1+1=3$.

---

#### Exercise 18: Truth of Conditional Statements

Determine whether each of these conditional statements is true or false:

1. If $1+1=3$, then unicorns exist.
2. If $1+1=3$, then dogs can fly.
3. If $1+1=2$, then dogs can fly.
4. If $2+2=4$, then $1+2=3$.

---

#### Exercise 19: Inclusive or Exclusive Or

Determine whether an inclusive or exclusive or is intended. Explain your answer:

1. Coffee or tea comes with dinner.
2. A password must have at least three digits or be at least eight characters long.
3. The prerequisite for the course is a course in number theory or a course in cryptography.
4. You can pay using U.S. dollars or euros.

---

#### Exercise 20: Inclusive or Exclusive Or

Determine whether an inclusive or exclusive or is intended. Explain your answer:

1. Experience with C++ or Java is required.
2. Lunch includes soup or salad.
3. To enter the country you need a passport or a voter registration card.
4. Publish or perish.

---

#### Exercise 21: Meaning of Or

For each sentence, state the meaning if the logical connective or is inclusive versus exclusive:

1. To take discrete mathematics, you must have taken calculus or a course in computer science.
2. When you buy a new car from Acme Motor Company, you get $2000 back in cash or a 2% car loan.
3. Dinner for two includes two items from column A or three items from column B.
4. School is closed if more than 2 feet of snow falls or if the wind chill is below $-100$.

---

#### Exercise 22: Conditional Statements in English

Write in the form "if $p$, then $q$":

1. It is necessary to wash the boss’s car to get promoted.
2. Winds from the south imply a spring thaw.
3. A sufficient condition for the warranty to be good is that you bought the computer less than a year ago.
4. Willy gets caught whenever he cheats.
5. You can access the website only if you pay a subscription fee.
6. Getting elected follows from knowing the right people.
7. Carol gets seasick whenever she is on a boat.

---

#### Exercise 23: Conditional Statements in English

Write in the form "if $p$, then $q$":

1. It snows whenever the wind blows from the northeast.
2. The apple trees will bloom if it stays warm for a week.
3. That the Pistons win the championship implies that they beat the Lakers.
4. It is necessary to walk 8 miles to get to the top of Long’s Peak.
5. To get tenure as a professor, it is sufficient to be world-famous.
6. If you drive more than 400 miles, you will need to buy gasoline.
7. Your guarantee is good only if you bought your CD player less than 90 days ago.
8. Jan will go swimming unless the water is too cold.


#### Exercise 24

Write each of these statements in the form "if $p$, then $q$" in English. 

- I will remember to send you the address only if you send me an e-mail message.
- To be a citizen of this country, it is sufficient that you were born in the United States.
- If you keep your textbook, it will be a useful reference in your future courses.
- The Red Wings will win the Stanley Cup if their goalie plays well.
- That you get the job implies that you had the best credentials.
- The beach erodes whenever there is a storm.
- It is necessary to have a valid password to log on to the server.
- You will reach the summit unless you begin your climb too late.

#### Exercise 25

Write each of these propositions in the form "$p$ if and only if $q$" in English.

- If it is hot outside you buy an ice cream cone, and if you buy an ice cream cone it is hot outside.
- For you to win the contest it is necessary and sufficient that you have the only winning ticket.
- You get promoted only if you have connections, and you have connections only if you get promoted.
- If you watch television your mind will decay, and conversely.
- The trains run late on exactly those days when I take it.

#### Exercise 26

Write each of these propositions in the form "$p$ if and only if $q$" in English.

- For you to get an A in this course, it is necessary and sufficient that you learn how to solve discrete mathematics problems.
- If you read the newspaper every day, you will be informed, and conversely.
- It rains if it is a weekend day, and it is a weekend day if it rains.
- You can see the wizard only if the wizard is not in, and the wizard is not in only if you can see him.

#### Exercise 27

State the converse, contrapositive, and inverse of each of these conditional statements.

- If it snows today, I will ski tomorrow.
- I come to class whenever there is going to be a quiz.
- A positive integer is a prime only if it has no divisors other than 1 and itself.

#### Exercise 28

State the converse, contrapositive, and inverse of each of these conditional statements.

- If it snows tonight, then I will stay at home.
- I go to the beach whenever it is a sunny summer day.
- When I stay up late, it is necessary that I sleep until noon.

#### Exercise 29

How many rows appear in a truth table for each of these compound propositions?

- $p \to \neg p$
- $(p \lor \neg r) \land (q \lor \neg s)$
- $q \lor p \lor \neg s \lor \neg r \lor \neg t \lor u$
- $(p \land r \land t) \leftrightarrow (q \land t)$

#### Exercise 30

How many rows appear in a truth table for each of these compound propositions?

- $(q \to \neg p) \lor (\neg p \to \neg q)$
- $(p \lor \neg t) \land (p \lor \neg s)$
- $(p \to r) \lor (\neg s \to \neg t) \lor (\neg u \to v)$
- $(p \land r \land s) \lor (q \land t) \lor (r \land \neg t)$

#### Exercise 31

Construct a truth table for each of these compound propositions.

- $p \land \neg p$
- $p \lor \neg p$
- $(p \lor \neg q) \to q$
- $(p \lor q) \to (p \land q)$
- $(p \to q) \leftrightarrow (\neg q \to \neg p)$
- $(p \to q) \to (q \to p)$


#### Exercise 35

Construct a truth table for each of these compound propositions.
- $p \to \neg q$
- $\neg p \leftrightarrow q$
- $(p \to q) \lor (\neg p \to q)$
- $(p \to q) \land (\neg p \to q)$
- $(p \leftrightarrow q) \lor (\neg p \leftrightarrow q)$
- $(\neg p \leftrightarrow \neg q) \leftrightarrow (p \leftrightarrow q)$

#### Exercise 36

Construct a truth table for each of these compound propositions.
- $(p \lor q) \lor r$
- $(p \lor q) \land r$
- $(p \land q) \lor r$
- $(p \land q) \land r$
- $(p \lor q) \land \neg r$
- $(p \land q) \lor \neg r$

#### Exercise 37
Construct a truth table for each of these compound propositions.

- $p \to (\neg q \lor r)$
- $\neg p \to (q \to r)$
- $(p \to q) \lor (\neg p \to r)$
- $(p \to q) \land (\neg p \to r)$
- $(p \leftrightarrow q) \lor (\neg q \leftrightarrow r)$
- $(\neg p \leftrightarrow \neg q) \leftrightarrow (q \leftrightarrow r)$

#### Exercise 38
Construct a truth table for $((p \to q) \to r) \to s$.

#### Exercise 39
Construct a truth table for $(p \leftrightarrow q) \leftrightarrow (r \leftrightarrow s)$.

#### Exercise 40:
 Explain why $(p \lor \neg q) \land (q \lor \neg r) \land (r \lor \neg p)$ is true when $p$, $q$, and $r$ have the same truth value and false otherwise.
#### Exercise 41
Explain why $(p \lor q \lor r) \land (\neg p \lor \neg q \lor \neg r)$ is true when at least one of $p$, $q$, and $r$ is true and at least one is false, but false when all three have the same truth value.

#### Exercise 50 
An ancient Sicilian legend states a barber shaves those, and only those, who do not shave themselves. Can there be such a barber?
