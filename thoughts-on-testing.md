# My thoughts on Software Testing

## Executable Documentation

> This article aims to explain in detail how behavioral scenarios are connected with the implementation of tests.

[BDD](https://github.com/pavelozerov/articles/blob/master/semantics-of-ubiquitous-language.md) is the great collaborative process that keeps things up-to-date as a Living Documentation. One of the most significant ambitions of the BDD discipline is to introduce an intelligent and clear **Testing Process** by making the Living Documentation **executable**.

So, important things first. A sequence of actions in the test must be **1:1 mapped with the steps** in the scenario! Such a connection gives a lot of benefits: if some part of the chain doesn't work or is broken, then it will be immediately noted **because of the incorrect behavior**. Also, if there are some required behavior changes, they should be made in every related part (requirement→scenario→code→test). It gives confidence by making the situation impossible when documentation differs from actual system behavior.

The ".feature" files and test code related to the scenarios in these files must be in the same Git repo! It's essentially important in terms of project consistency because it makes Git the main source of truth both for business logic and its implementation. Having behavioral scenarios in the same place as code and rendering them in some collaborative space (e.g., Confluence) using additional plugins allows us to avoid situations where requirements can be occasionally changed without the development team being notified. In this case, every change of the requirements will first trigger a change of the related scenario(s), which carries with it either a **signing of a new "contract" or updating an existing one**. So, in the end, **scenarios are distributed (rendered) "inside out"** from the ".feature" file in Git to the knowledge source (Confluence).

As an additional benefit, making changes through Git requires creating a Pull Request (PR). In its turn, it requires that the **PR must be reviewed before going further**, which can only be done by **all** (!) the involved parties.

<img src="https://github.com/pavelozerov/images/blob/master/thoughts-on-testing/figure1.PNG?raw=true" border="1" width="300"/>

**Inside-out rendering of scenarios**

## General-to-Specific vs Specific-to-General

Now, let's discuss the essence of testing. Below are two examples that provide a different understanding of **unit**. The first example (Figure 2) illustrates the "classical" approach - **unit is a function**, whereas another one (Figure 3) realizes unit as a **set of behaviors** that in total make **the system**.

> And there is a crucial difference between these two regarding Software Development.

Figure 2 illustrates a **Specific-to-General** approach with **the smallest level as the cornerstone**.

<img src="https://github.com/pavelozerov/images/blob/master/thoughts-on-testing/figure2.PNG?raw=true" border="1" width="500"/>

**Figure 2**

Almost everyone in the industry is familiar with it, and de facto, it's already a standard. But what's wrong with that, you can ask? Firstly, concerning the BDD discipline, such an approach requires low-level scenarios to cover the unit (function) level. In the worst (and in the most common) case, there are no such scenarios at all (since the unit level is a responsibility of the dev team, they don't usually want to waste time creating such scenarios). This leads to the biggest and most common problem when nobody can exactly say what and how it is tested. Secondly, the "full picture" of how things work is lost due to disbalance, where low-level (technical details) prevails at a high level (product understanding). As a result, it becomes a root cause of poor domain knowledge (or even worse - it can give an illusion that you have this knowledge because you might have tons of unit tests with or without scenarios, but they are useless without the understanding of what behavior they cover; the thing is that system behavior is not the only function, but rather a set of them).

Another concept (Figure 3), in turn, suggests "promoting" the unit for the sake of one of the BDD gems called ubiquitous language.

<img src="https://github.com/pavelozerov/images/blob/master/thoughts-on-testing/figure3.PNG?raw=true" border="1" width="500"/>

**Figure 3**

> "Business" never thinks in the context of methods.

Hence, if developers really want to understand business requirements (Wishlist), they must start thinking like a business does - from **General-to-Specific**. But what does it mean? Let me give you an analogy. Imagine that you're reading a book. The book is translated from the original language it's written into to your native language. So, besides different levels of understanding, the chain of obstacles is much longer:

<img src="https://github.com/pavelozerov/images/blob/master/thoughts-on-testing/figure4.PNG?raw=true"/>

**Figure 4**

But if you’d read the same book on the original language, then you, at least, could cut the chain by half:

<img src="https://github.com/pavelozerov/images/blob/master/thoughts-on-testing/figure5.PNG?raw=true" border="1" width="400"/>

**Figure 5**

So, the General-to-Specific way of communicating with the business side is like reading a book in the language it was originally written. By doing this, both sides reduce the possible obstacles between what the business wants to get and how developers understand and deliver it. Sounds promising, right?

Since the General-to-Specific approach requires a higher level of unit definition, figuratively speaking, development teams have to "stand on tiptoe" to rethink the unit. It means that **unit is not a method anymore**, but on a higher level, **it's a microservice** with **set of behaviors**, which make a **capability** (or the **system**). And from that perspective, integration testing is done between systems, not behaviors!

> The General-to-Specific approach extends the boundaries and removes the "fence" between dev and business. There is no separate "business" anymore, and the dev team **becomes a capability**.

## End-to-End Testing

End-to-end (E2E) testing is worth discussing because it stands apart from other testing types. The first and most important note about E2E testing is that it's not the sum of scenarios used for development; hence, it **must be based on separate ones prepared by stakeholders**.

> Scenario 1 + Scenario 2 + Scenario 3 + Scenario 4 + Scenario 5 != E2E Scenario

## Keynote

> - Definition of done and acceptance criteria must be presented for every feature (story) that must consist of one or more scenarios that must be tested on different levels (have to be adapted with the needed level of details)
> - Every test on each level is an ACCEPTANCE test because it's related to some scenario that, in turn, is associated with some business requirement that has acceptance criteria
