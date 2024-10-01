Definitions, Examples, and Theorems

**Definition 1.2.1** (Sample space and event). The _sample space_ $S$ of an experiment is the set of all possible outcomes of the experiment. An _event_ $A$ is a subset of the sample space $S$, and we say that $A$ _occured_ if the actual outcome is in $A$. 

**Example 1.2.2** (Coin flips). A coin is flipped 10 times. Writing Heads as $H$ and Tails as $T$, a possible outcome of (pebble) is $HHHTHHTTHT$, and the sample space is the set of all possible strings of length 10 of $H$'s and $T$'s. We can (and will) encode $H$ as 1 and $T$ as 0, so that an outcome is a sequence $(s_1,...,s_{10})$ with $s_j \in \lbrace 0,1 \rbrace,$ and the sample space is the set of all such sequences. Now let's look at some events:

1. Let $A_1$ be the event that the first flip is Heads. As a set,

    $A_1 = \lbrace(1,s_2,...,s_{10}) : s_j \in {0,1} for 2 \leq j \leq 10\rbrace.$
   
   This is a subset of the sample space, so it is indeed an event; saying that $A_1$ occurs is the same thing as saying that the first flip is Heads. Similarly, let $A_j$ be the event that the $`j`$th flip is Heads for $`j =`$2,3,...,10.

2. Let $B$ be the event that at least one flip was Heads. As a set,

    $B = \bigcup_{j=1}^{10} A_j.$

3. Let $C$ be the event that all the flips were Heads. As a set,

    $C = \bigcap_{j=1}^{10} A_j.$

4. Let $D$ be the event that there were at least two consecutive Heads. As a set,

    $D = \bigcup_{j=1}^{9} (A_j \cap A_{j+1}).$

**Example 1.2.3** (Pick a card, any card). Pick a card from a standard deck of 52 cards. The sample space $S$ is the set of all 52 cards (so there are 52 pebbles, one for each card). Consider the following four events:

$A:$ card is an ace.

$B:$ card has a black suit.

$D:$ card is a diamond.

$H:$ card is a heart.

As a set, $H$ consists of 13 cards:

  $`\lbrace`$Ace of Hearts, Two of Hearts,$`...`$,King of Hearts$`\rbrace.`$

  We can create various other events in terms of the events A, B, D, and H. Unions, intersections, and complements are especiallyl useful for this. For example: 

$A \cap H$ is the event that the card is the Ace of Hearts.

$A \cap B$ is the event $\lbrace Ace of Spades, Ace of Clubs \rbrace.$

$A \cup D cup H$ is the event that the card is red or an ace.

$(A \cup B)^c = A^c \cap B^c$ is the event that the card is a red non-ace. 

Also, note that , so $B$ can be expressed in terms of $D$ and $H$. On the other hand, the event that the card is a spade can't be written in terms of $A,B,D,H$ since none of them are fine-grained enough to be able to distinguish between spades and clubs.

There are _many_ other events that could be defined using this sample space. In fact, the counting methods introduced later in this chapter show that there are $2^{52} \approx 4.5 \times 10^{15}$ events in this problem, even though there are only 52 pebbles.

What if the card drawn were a joker? That would indicate that we had the wrong sample space; we are assuming that the outcome of the experiment is guaranteed to be an selement of $S$.

As the preceding examples demonstrate, events can be described in English or in set notation. Sometimes the English description is easier to interpret while the set notation is easier to manipulate. Let $S$ be a sample space and $s_actual$ be the actual outcome of the experiment (the pebble that ends up getting chosen when the experiment is performed). A mini-dictionary for converting between English and sets is given on the next page.

$$
\begin{array}{ll}
\text{English} & \text{Sets} \\
\text{Events and occurrences} & \\
\text{sample space} & S \\
s \text{ is a possible outcome} & s \in S \\
A \text{ is an event} & A \subseteq S \\
A \text{ occurred} & s_{\text{actual}} \in A \\
\text{something must happen} & s_{\text{actual}} \in S \\
\text{New events from old events} & \\
A \text{ or } B \text{ (inclusive)} & A \cup B \\
A \text{ and } B & A \cap B \\
\text{not } A & A^c \\
A \text{ or } B, \text{ but not both} & (A \cap B^c) \cup (A^c \cap B) \\
\text{at least one of } A_1, \ldots, A_n & A_1 \cup \cdots \cup A_n \\
\text{all of } A_1, \ldots, A_n & A_1 \cap \cdots \cap A_n \\
\text{Relationships between events} & \\
A \text{ implies } B & A \subseteq B \\
A \text{ and } B \text{ are mutually exclusive} & A \cap B = \emptyset \\
A_1, \ldots, A_n are a partition of S & A_1 \cup \cdots \cup A_n = S, A_i \cap A_j = \emptyset, for i \neq j
\end{array}
$$

**Definition 1.3.1** (Naive definition of probability). Let $A$ be an event for an experiment with a finite sample space $S$. The naive probability of $A$ is

  $`P_{naive}(A) = \frac{|A|}{|S|} = \frac{\text{number of outcomes favorable to } A}{\text{total number of outcomes in } S}.`$

(We use |A| to denote the size of $A$; see Section A.1.5 of the math appendix.)

In terms of Pebble World, the naive definition just says that the probability of $A$ is the fraction of pebbles that are in $A$. For example, in Figure 1.1 it says

  $`P_{\text{naive}}(A) = \frac{5}{9}, P_{\text{naive}}(B) = \frac{4}{9}, P_{\text{naive}}(A \cup B) = \frac{8}{9}, P_{\text{naive}}(A \cap B) = \frac{1}{9}.`$

For the complements of the events just considered,

  $`P_{\text{naive}}(A) = \frac{5}{9}, P_{\text{naive}}(B) = \frac{4}{9}, P_{\text{naive}}(A \cup B) = \frac{8}{9}, P_{\text{naive}}(A \cap B) = \frac{1}{9}.`$

In general,

  $`P_{\text{naive}}(A^c) = \frac{|A^c|}{|S|} = \frac{|S| - |A|}{|S|} = 1 - \frac{|A|}{|S|} = 1 - P_{\text{naive}}(A).`$

**Theorem 1.4.1** (Multiplication rule). Consider a compound experiment consisting of two sub-experiments, Experiment A and Experiment B. Suppose that Experiment A has $a$ possible outcomes, and for each of those outcomes Experiment B has $b$ possible outcomes. Then the compound experiment has $ab$ possible outcomes.

To see why the multiplication rule is true, imagine a tree diagram as in Figure 1.2. Let the tree branch $a$ ways according to the possibilities of Experiment A, and for each of those branches create $b$ further branches for Experiment B. Overall, there are $$\underbrace{b + b + \cdots + b}_{a} = ab$$ possibilities.

**Example 1.4.3** (Runners). Suppose that 10 people are running a race. Assume that ties are not possible and that all 10 will complete the race, so there will be well-defined first place, second place, and third place winners. How many possibilities are there for the first, second, and third place winners?

_Solution:_ There are 10 possibilities for who gets first place, then once that is fixed there are 9 possibilities for who gets second place, and once these are both fixed there are 8 possibilities for third place. So by the multiplication rule, there are $10 \cdot 9 \cdot 8 = 720$ possibilities.

We did not have to consider the first place winner first. We could just as well have said that there are 10 possibilities for who got third place, then once that is fixed there are 9 possibilities for second place, and once those are both fixed there are 8 possibilities for first place. Or imagine that there are 3 platforms, which the first, second, and third place runners will stand on after the race. The platforms are gold, silver, and bronze, allocated to the first, second, and third place runners, respectively. Again there are $10 \cdot 9 \cdot 8 = 720$ possibilities for how the platforms will be occupied after the race, and there is no reason that the platforms must be considered in the order (gold, silver, bronze).

**Example 1.4.4** (Chessboard). How many squares are there in an $8 x 8$ chessboard, as in Figure 1.3? Even the name "$8 x 8$ chessboard" makes this easy: there are $8 \cdot 8 = 64$ squares on the board. The grid structure makes this clear, but we can also think of this as an example of the multiplication rule: to specify a square, we can specify which row and which column it is in. There are 8 choices of row, for each of which there are 8 choices of column.

Furthermore, we can see without doing any calculations that half the squares are white and half are black. Imagine rotating the chessboard 90 degrees clockwise. Then all the positions that had a white square now contain a black square, and vice versa, so the number of white squares must equal the number of black squares. We can also count the number of white squares using the multiplication rule: in each of the 8 rows there are 4 white squares, giving a total of $8 cdot 4 = 32$ white squares.

In contrast, it would require more effort to count the number of white squares in the crossword puzzle grid shown in Figure 1.3. The multiplication rule does not apply, since different rows sometimes have different numbers of white squares.

**Example 1.4.5** (Ice cream cones). Suppose you are buying an ice cream cone. You can choose whether to have a cake cone or a waffle cone, and whther to have chocolate, vanilla, or strawberry as your flavor. This decision process can be visualized with a tree diagram, as in Figure 1.4.

By the multiplication rule, there are $2 \cdot 3 = 6$ possibilities. This is a very simple example, but is worth thinking through in detail as a foundation for thinking about and visualizing more complicated examples. Soon we will encounter examples where drawing the tree in legible size would take up more space than exists in the known universe, yet where conceptually we can still think in terms of the ice cream example. Some things to note:

1. It doesn't matter whether you choose the type of cone first ("I'd like a waffle cone with chocolate ice cream") or the flavor first ("I'd like chocolate ice cream on a waffle conde"). Either way, there are $2 \cdot 3 = 3 \cdot 2 = 6$ possibilities.

2. It doesn't matter whether the same flavors are available on a cake cone as on a waffle cone. What matters is that there are exactly 3 flavor choices for each cone choice. If for some strange reason it were forbidden to have chocolate ice cream on a waffle cone, with no substitute flavor available (aside from vanilla and strawberry), there would be $3 + 2 = 5$ possibilities and the multiplication rule wouldn't apply. In larger examples, such complications could make counting the number of possbilities vastly more difficult.

Now suppose you buy _two_ ice cream cones on a certain day, one in the afternoon and the other in the evening. Write, for example, (cakeC, waffleV) to mean a cake cone with chocolate in the afternoon, followed by a waffle cone with vanilla in the evening. By the multiplication rule, there are $6^2 = 36$ possbilities in your delicious compound experiment.

But what if you're only interested in what kinds of ice cream cones you had that day, not the order in which you had them, so you don't want to distinguish, for example, between (cakeC, waffleV) and (waffleV, cakeC)? Are there now $36/2 = 18$ possibilities? No, since possibilities like (cakeC, cakeC) were already only listed once each. There are $6 \cdot 5 = 30$ ordered possibilities $(x,y)$ with $x \neq y$, which turn into 15 possibilities if we treat $(x,y)$ as equivalent to $(y,x)$, plus 6 possibilities of the form $(x,x)$, giving a total of 21 possibilities. Note that if the 36 original ordered pairs $(x,y)$ are equally likely, then the 21 possibilities here are _not_ equally likely.

**Example 1.4.6** (Subsets). A set with $n$ elements has $2^n$ subsets, including the empty set $\emptyset$ and the set itself. This follows from the multiplication rule since for each element, we can choose whether to include it or exclude it. For example, the set $\lbrace 1, 2, 3 \rbrace$ has the 8 subsets $\emptyset, \lbrace 1 \rbrace, \lbrace 2 \rbrace, \lbrace 3 \rbrace, \lbrace 1, 2 \rbrace, \lbrace 1, 3 \rbrace, \lbrace 2, 3 \rbrace, \lbrace 1, 2, 3 \rbrace$. This result explains why in Example 1.2.3 there are $2^{52}$ events that can be defined.

We can use the multiplication rule to arrive at formulas for sampling with and without replacement. Many experiments in probability and statistics can be interpreted in one of these two contexts, so it is appealing that both formulas follow directly from the same basic counting principle.

**Theorem 1.4.7** (Sampling with replacement). Consider $n$ objects and making $k$ choices from them, one at a time _with replacement_ (i.e., choosing a certain object does not preclude it from being chosen again). Then there are $n^k$ possible outcomes (where order matters, in the sense that, e.g., choosing object 3 and then object 7 is counted as a different outcome than choosing object 7 and then object 3.)

For example, imagine a jar with $n$ balls, labeled from 1 to $n$. We sample balls one at a time with replacement, meaning that each time a ball is chosen, it is returned to the jar. Each sampled ball is a sub-experiment with $n$ possible outcomes, and there are $k$ sub-experiments. Thus, by the multiplication rule there are $n^k$ ways to obtain a sample size $k$.

**Theorem 1.4.8** (Sampling without replacement). Consider $n$ objects and making $k$ choices from them, one at a time _without replacement_ (i.e., choosing a certain object precludes it from being chosen again). Then there are $n(n-1) \cdots (n-k+1)$ possible outcomes for $1 \leq k \leq n$, and 0 possibilities for $k > n$ (where order matters). By convention, $n(n-1) \cdots (n-k+1) = n$ for $k = 1$.

This result also follows directly from the multiplication rule: each sampled ball is again a sub-experiment, and the number of possible outcomes decreases by 1 each time. Note that for sampling $k$ out of $n$ objects without replacement, we need $k \leq n$, whereas in sampling with replacement the objects are inexhaustible. 
