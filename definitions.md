Definitions and Examples

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
