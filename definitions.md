Definitions and Examples

**Definition 1.2.1** (Sample space and event). The _sample space_ $S$ of an experiment is the set of all possible outcomes of the experiment. An _event_ $A$ is a subset of the sample space $S$, and we say that $A$ _occured_ if the actual outcome is in $A$. 

**Example 1.2.2** (Coin flips). A coin is flipped 10 times. Writing Heads as $H$ and Tails as $T$, a possible outcome of (pebble) is $HHHTHHTTHT$, and the sample space is the set of all possible strings of length 10 of $H$'s and $T$'s. We can (and will) encode $H$ as 1 and $T$ as 0, so that an outcome is a sequence $(s_1,...,s_{10})$ with $s_j \in \lbrace 0,1 \rbrace,$ and the sample space is the set of all such sequences. Now let's look at some events:

1. Let $A_1$ be the event that the first flip is Heads. As a set,

    $A_1 = \lbrace(1,s_2,...,s_{10}) : s_j \in {0,1} for 2 \leq j \leq 10\rbrace.$
   
   This is a subset of the sample space, so it is indeed an event; saying that $A_1$ occurs is the same thing as saying that the first flip is Heads. Similarly, let $A_j$ be the event that the $j$th flip is Heads for $j = 2,3,...,10.

3. 
