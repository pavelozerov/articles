# The Concept of Testing

## Executable Documentation

> The aim of this article is to explain in detail the idea of how the behavioral scenarios are connected with implementation of tests.

[BDD](https://github.com/pavelozerov/articles/blob/master/concept-of-analysis.md) is a great collaborative process that keeps things up-to-date as a Living Documentation. One of the biggest ambitions of BDD discipline is to introduce an intelligent and clear **Testing Process** by making the Living Documentation **executable**.

So, important things first. Sequence of actions in the test must be **1:1 mapped with the steps** in the scenario! Such a connection gives a lot of benefits: if some part of the chain doesn't work or broken, then it will be immediately noted, **because of the incorrect behavior**. Also, if there are some required behavior changes, they should be made in every related part (requirement→scenario→code→test). It gives a confidence by making impossible the situation, when documentation differs from the real system behavior.

The “.feature” files and test code related to the scenarios in these files must be in the same Git repo! It’s essentially important in terms of the project consistency, because it makes Git as the main source of truth both for business logic and its implementation. Having behavioral scenarios in the same place as code, and rendering them in some collaborative space (e.g., Confluence) using additional plugins, allows to avoid the situation when requirements can be occasionally changed without development team to be notified. In this case every change of the requirements will first trigger a change of the related scenario(s), which carries with it either a **signing of a new “contract” or updating of an existing one**. So, in the end **scenarios are distributed (rendered) “inside out”**: from the ".feature" file in Git to knowledge source (Confluence).

As additional benefit, making changes through the Git, requires a Pull Request (PR) to be created. In its turn, it requires that the **PR must be reviewed before going further**, which can only be done by **all** (!) the involved parties.

<img src="https://github.com/pavelozerov/images/blob/master/concept-of-testing/figure1.PNG?raw=true" border="1" width="300"/>

**Inside out rendering of scenarios**

## General-to-Specific vs Specific-to-General

Now let’s discuss the essence of testing. Below are two examples that provide different understanding of **unit**. First example (Figure 2) illustrates the “classical” approach - **unit is a function**, whereas another one (Figure 3) realizing unit as a **set of behaviors** that in total make **the system**.

> And there is a crucial difference between these two in terms of Software Development.

Basically, Figure 2 illustrates a **Specific-to-General** approach with **the smallest level as cornerstone**.

<img src="https://github.com/pavelozerov/images/blob/master/concept-of-testing/figure2.PNG?raw=true"/>

**Figure 2**

Almost everyone in the industry is familiar with it and, de facto, it’s already a standard. But what’s wrong with that you can ask? Firstly, in relation with BDD discipline such approach requires to have low level scenarios to cover the unit (function) level. In the worst (and in the most common) case there are no such scenarios at all (since unit level is a responsibility of the dev team, they don’t usually want to waste time to create such scenarios). This leads to the biggest, and again, very common problem, when nobody can exactly say what and how is tested. Secondly, the “full picture” of how things work is lost due to disbalance, where low level (technical details) prevails at a high level (product understanding). As a result it becomes a root cause of a poor domain knowledge (or even worse - it can give an illusion that you have this knowledge, because you might have tons of unit tests with or without scenarios, but they are useless without the understanding of what behavior they cover; the thing is that system behavior is not the only function, but rather a set of them).

Another concept (Figure 3), in turn, suggests to “promote” unit for the sake of one of the BDD gems called ubiquitous language.

<img src="https://github.com/pavelozerov/images/blob/master/concept-of-testing/figure3.PNG?raw=true"/>

**Figure 3**

> "Business" never thinks in a context of methods.

Hence, if developers really want to understand business requirements (Wishlist), they must start thinking in the way as business does - from **General-to-Specific**. But what does it mean? Let me give you an analogy. Imagine that you’re reading a book. And the book is translated from the original language it’s written on to your native language. So, besides different level of understanding, the chain of obstacles is much longer:

<img src="https://github.com/pavelozerov/images/blob/master/concept-of-testing/figure4.PNG?raw=true"/>

**Figure 4**

But if you’d read the same book on the original language, then you, at least, could cut the chain by half:

<img src="https://github.com/pavelozerov/images/blob/master/concept-of-testing/figure5.PNG?raw=true"/>

**Figure 5**

So, General-to-Specific way of communicating to business side it’s like reading a book on the language it was originally written on. By doing this both sides reduce the amount of possible obstacles between what business essentially wants to get and how developers understand and deliver it. Sounds promising, right?

Since General-to-Specific approach requires a higher level of unit definition, figuratively speaking, development teams have to “stand on tiptoe” in order to rethink unit. It means that **unit is not a method anymore**, but on a higher level **it’s a microservice** with **set of behaviors**, which make a **capability** (or the **system**). And from that perspective an integration testing is done between systems, not behaviors!

>  General-to-Specific approach extends the boundaries and removes the “fence” between dev and business. There is no separate “business” anymore and dev team **really becomes a capability**.

## End-to-End Testing

An end-to-end (E2E) testing is worth discussing, because it stands apart from other testing types. First and the most important note about E2E testing is that it’s not the sum of scenarios used for development, and hence it **must be based on separate ones prepared by stakeholders**.

<img src="https://github.com/pavelozerov/images/blob/master/concept-of-testing/figure6.PNG?raw=true"/>

**Figure 6**

# Glossary of Testing

> - Definition of done and acceptance criteria must be presented for every feature
> - Feature (story) must consist of one or more scenarios
> - Scenarios must be tested on different levels (have to be adapted with needed level of details)
> - Every test on each level is an ACCEPTANCE test, because it's related to some scenario that in its turn related to some business requirement that has acceptance criteria

## Functional Testing Levels

| Levels | Preconditions | Definition |
| ------ | ------------- | ---------- |
| Unit Testing | Description of unit behavior (low level BDD scenario that describes the function under test) | A test level that focuses on how functions behave. Unit test is a fast in- memory test that depends on a code in the assembly under test and nothing else. Unit tests use mocks of services and data and should be part of the project repository. |
| Integration Testing | Connection to DB (or any other deployed internal related components). Mocked external components (if there is a need). Description of integrated systems' behavior (low level BDD scenario that describes integration at least of two systems). Only part of the service/component can be deployed (for instance, just 1 endpoint) | A test level that focuses on integration between systems (how multiple units are behaving with each other). As soon as a database connection is made or any other behavior with the database is made this is no longer unit test, but an integration test. Unlike unit test, it should use real implementations for internal components/services instead of mocking them (mocks are allowed only for external components/services, which are not a part of SUT - System Under Test). Integration test level is responsible for contract testing (API contracts and behavior) and behavior between services which depend on each other. |
| System Testing | Service(s) deploy. Definition of done (high level BDD scenarios that describes system behavior) | A test level that focuses on a deployed product. The test environment should ideally correspond to the final target or production environment, which requires the entire application to be up and running and focus on replicating user behaviors. Might use different API and GUI interfaces in order to test different acceptance criteria. |
| End-to-End Testing | Full product deployment. High level BDD scenarios considering involved 3rd party services/systems | A test level that focuses on overall, end-to-end behavior of the system(s) as a whole. These tests provide final verification of business requirements considering not only our product, but maybe some other ones (3rd parties) as well. |

## Testing types

| Types | Category | Definition |
| ----- | -------- | ---------- |
| Smoke testing | Functional | A test suite that covers the main functionality of a component or SUT to determine whether it works properly before planned testing process begins. |
| Regression testing | Functional | Previously developed product works as expected (change-related testing). No new defects were introduced for existing functionality after a new development. |
| Security testing | Non- Functional | Testing to determine the security of the product (covered by a separate team). |
| Performance testing | Non- Functional | Testing to determine the performance efficiency of a component or SUT (load, stress, scalability, volume, spike). |
| Exploratory testing | Functional | Focuses on discovery and relies on the guidance of the individual tester to uncover defects that are not easily covered in the scope of other tests. |