# Semantics of Ubiquitous Language (SOUL)

## Abstract

Each IT organization intends to develop strong competence in analysis, where all features go through a process that includes various levels of research and testing, such as business, functional, technical, etc. Companies put a lot of effort into reaching this. The common thing of all these strives is a wish to make a product with **value**. Development always starts from the idea with the business requirements behind it. But how do we make business requirements clear and consistent? How do we define them to reflect the original intent without distortion? How do we make sure they have value? The key is a **Behavior Driven Development** concept.

## Specification vs Living Documentation

What does the specification process look like in a "classic" way? In this structure (Figure 1), the analyst becomes a bottleneck because this is the only person who commits to the source of information (usually, this is some collaboration software, e.g., Confluence).

<img src="https://github.com/pavelozerov/images/blob/master/semantics-of-ubiquitous-language/figure1.png?raw=true" border="1" width="200"/>

**Figure 1**

This means that the analyst must make any changes in the future, and the rest of the team does not control these changes anyhow. Worse, they may not even know about them. So, this is an insidious process. The main disadvantage is the speed of change because different things are always stuck in the queue. The situation is also complicated because teams work at their own pace, so analysts will only receive feedback on what is done after some time. It might happen even if the new feature description process already started. Analysts become a "gateway" and, in this state, can only hold a limited number of things in their heads. Now, there are two queues between which analysts have to switch: one with TO-DO things that can be handled step by step only and another one with things-to-be-changed based on late feedback from the team. But as you know, one falls to the ground between two stools.

Why is BDD a problem solver? Because of a **Living Documentation**. Instead of having the analyst role as a "bottleneck," it transforms into the supporting role (Figure 2).

<img src="https://github.com/pavelozerov/images/blob/master/semantics-of-ubiquitous-language/figure2.png?raw=true" border="1" width="300"/>

**Figure 2**

In this structure, the analyst still works closely with different teams, but with one crucial difference. Instead of making changes by oneself, an analyst collects all the needed information, structures it, and creates a shared place where all involved people work together. This shared page has different chapters (specifically for developers, QA, product owners, etc.) that responsible team members must fill. With this approach, an analyst is no longer the bottleneck since **now everybody is responsible for the documentation and knowledge sharing**.

> - If something is **not structured**, it's probably **not documented**, which means that it **does not exist**!
> - ~~When everyone is responsible, no one is responsible~~ → when everyone is responsible, then **structure** is responsible!

## Tower of Babel

What is Behavior Driven Development (BDD) for? Someone can say that this is something to structure the documentation and knowledge source, to bring clarity to the team, or to have a specific process of analysis, implementation, testing, or anything else. But all this doesn't matter. Of course, all these answers are correct in their way, but none of them says anything about the root cause. **And the root cause is Legacy in the way we specify things**. Let me guess: many specifications have been written over the past few years, but most of the information has no clear structure. Business descriptions are often mixed up with some technical pages, which are partially outdated. Congratulations, your company is one of many that have got things out of control. This led us to a situation where it's pretty hard to find consistent information since all the related pieces are split within different places, and some are not documented. It means that needed information about how things work must be collected from other people within a team, and there is a high probability that this information is obsolete. In sum, the problem is that such collective knowledge is usually not structured. **And if something is not structured, it's probably not documented, meaning it does not exist**.

Okay, but if Legacy is the root cause of a documentation lack, what is the root cause of Legacy then? Well, the answer is quite simple - the **communication lack**. To make an example more memorable, we can refer to the Tower of Babel myth (Figure 3).

<img src="https://github.com/pavelozerov/images/blob/master/semantics-of-ubiquitous-language/figure3.png?raw=true" border="1" width="400"/>

**Figure 3**

Let's make a parallel with the IT industry. At the beginning of the project, people discuss the idea, and all seems to be clear - people speak the same language. But as the project moves further and more people get involved, at the end of the day, there is always a lack of communication as a result. When it happens, the stage might vary, but it definitely happens. And since the moment people start to speak different languages, development is doomed to become a typical IT project, where you need to go through 9 circles of Dante's hell before it is finished (Figure 4).

<img src="https://github.com/pavelozerov/images/blob/master/semantics-of-ubiquitous-language/figure4.png?raw=true" border="1" width="400"/>

**Figure 4**

The same happened to people in the Tower of Babel myth - they failed with their initiative to build a tower tall enough to reach heaven because the team cannot be successful if people can no longer understand each other in the same way. BDD seeks to help avoid this scenario, as it teaches people how to collaborate and speak the same language.

## Root causes

Before we discover the implementation of the BDD approach in more detail, let's have a quick look back first. The sole purpose of mentioning the Tower of Babel myth was to show the importance of communication. This is the only condition that makes teams successful because it creates collaboration. It may not be obvious, but it is the only cure for Legacy because it is exactly its root cause (Figure 5).

<img src="https://github.com/pavelozerov/images/blob/master/semantics-of-ubiquitous-language/figure5.png?raw=true" border="1" />

**Figure 5**

Let's now go deeper into details. What is the root cause of communication lack? All people think differently. This is a known fact, and essentially, this is awesome because different thinking allows people to see things from different angles; thus, we make discoveries and progress. However, such uniqueness, the result of which is a different way of thinking, is the reason that **people understand things differently**. And exactly different understanding is the root cause of communication lack. For example, if you ask some group of people to describe the same thing, most probably as a result, you will get as many answers as there are respondents. So, just communication is not enough. Even well-coordinated communication is not enough. There should be **no room for different interpretations**, which means that communication should always provide **clearness
and collaboration**. Based on that, we can extend the previous drawing with a new dependency (Figure 6).

<img src="https://github.com/pavelozerov/images/blob/master/semantics-of-ubiquitous-language/figure6.png?raw=true" border="1" width="550"/>

**Figure 6**

The next logical question is: how can we fix this? To answer this question, let's take a look at Figure 6. According to it, the **main dependency is a different understanding**. Let's dwell upon this in more detail. What exactly is this difference? Why does it actually appear?

The first possible reason that appears in mind is the remoteness of a team. It's common in IT when several "virtual teams" work on the same product or a feature. But you might have also noticed that this issue often occurs within one team, meaning that remoteness is not a reason. Well, the real reason is also clear and related to the level of detail people work on. Different groups of people need different levels of detail. Stakeholders, product managers, and product owners work on the highest level and are not involved in technical details or the implementation process (sadly). Usually, they only need to have an overview. Architects and analysts work on a bit lower - technical - level. They transform business requirements into technical specifications and behavioral scenarios based on high-level requests. Developers and QA engineers work on the lowest - implementation level. And this is exactly the place where "different understanding" is born.

Let's figure out how we can fix this. Does BDD is designed for that? Of course!

In essence, BDD is nothing but a **collaborative** practice that aims/helps deliver higher-value software more effectively by balancing the level of detail that the business and development teams need. It involves a lot of parties, and they must be satisfied with the requirements, described scenarios, and implementation details. That's why analysts, architects, developers, and QA have to move to the same level of detail, and work can only be started when all the related sides agree on scenarios (Figure 7).

<img src="https://github.com/pavelozerov/images/blob/master/semantics-of-ubiquitous-language/figure7.png?raw=true" border="1" width="350"/>

**Figure 7**

Such an agreement between all the related parties is very similar to **a contract**. Like with a real contract, people put their own signatures, which means that they agree on conditions (requirements) that should be met. Otherwise, the deal (feature/product) will fail. However, it's also important to remember that during the implementation, there might be a situation when the contract (specification) might be changed based on some research or limitations. This is a typical situation since BDD is a collaborative process that allows keeping information constantly up-to-date as a **Living Documentation**. It means that specifications can be changed, but only on one mandatory condition: **a new contract should be made, where all the changes are reflected, and all people are agreed on**. So, there are plenty of things that can be improved using BDD, such as consistency, clearness, confidence, automation, and time-to-delivery; by this, we can highlight such benefits as the clear and common definition of done and acceptance criteria, the shorter period from business requirements to production and implementation that matches requirements.

The most important thing to remember is that BDD is all about working together, where teams provide results that are valuable and really matter (Figure 8).

<img src="https://github.com/pavelozerov/images/blob/master/semantics-of-ubiquitous-language/figure8.png?raw=true" border="1" width="400"/>

**Figure 8**

## Implementation of BDD

Development always starts from the idea. Usually, all the ideas without analysis go to the specific **product backlog (inbox)**. Once the TO-DO list is prioritized by the Product Owner (or another responsible person), it goes to a **product roadmap**. Such tickets are usually called Epics because they describe the idea in general. Epics are some kind of containers for features they consist of. The next step is feature mapping: this is a collaborative process involving different teams that aims to discuss details of feature requirements, architecture, implementation, etc.

When the analysis is ready, developers can start to work on **feature implementation** using tickets from **development backlog**. When development is finished, there is a QA phase when engineers prepare **automated tests** that are 1:1 implementation of the behavioral scenarios created during the feature mapping process. When functional testing is done, the feature moves to **acceptance testing**, where the analyst and business have to ensure that the current implementation does exactly the same as the business requirements (Figure 9).

<img src="https://github.com/pavelozerov/images/blob/master/semantics-of-ubiquitous-language/figure9.png?raw=true" border="1" width="550"/>

**Figure 9**

# Feature essentials

## Feature mapping

The most significant advantage of BDD is that it lets people use the same language to understand requirements in the same way. There is a technique called [Feature mapping](https://johnfergusonsmart.com/feature-mapping-a-simpler-path-from-stories-to-executable-acceptance-criteria/) to achieve this. According to its author, [John Ferguson Smart](https://johnfergusonsmart.com/author/), in a nutshell, the process goes something like this:

- Define a feature or story, or pick one from the backlog
- Understand what actors are involved in the story
- Break the feature into tasks to identify the main flows
- Identify examples that illustrate a principle or variant flow. Ask questions like "But what if...", "What else could lead to this outcome," and "What other outcomes might happen," and use the answers to create new examples. Use rules to explain and give context to your examples
- Rinse and repeat for other rules and examples
- Create Executable Specifications: automate the main high-level flows with pending steps

> Feature mapping is a collaborative activity that makes the whole team work together in order to define the **value** of the feature.

<img src="https://github.com/pavelozerov/images/blob/master/semantics-of-ubiquitous-language/figure10.png?raw=true" border="1" width="550"/>

**Figure 10**

## Feature breakdown

Feature mapping starts with a breakdown. What is the feature breakdown? This is a process when a team moves from general to particular and turns the development unit (Epic) into modules. Let's have a quick recap of what the team already has:

- Prepared product backlog
- Architecture Overview of an Epic
- Business requirements described as user story (Figure 11)

<img src="https://github.com/pavelozerov/images/blob/master/semantics-of-ubiquitous-language/figure11.png?raw=true" border="1" width="550"/>

**Figure 11**

What else do we then need? According to the essence of feature mapping, such an activity aims to discover **acceptance criteria** and business requirements. For instance, based on the story from Figure 11, the analyst might note down the following initial **business rules**:

- Amount of items added to stock equals the amount of items the customer returns
- In case of a return, goods must be returned to the merchant's stock
- Customer can get a refund

So, what is the essence of feature mapping and breakdown, then? What modules do we talk about? There are **several of them**:

- Create acceptance criteria based on business requirements
- Create sequence diagrams as a basis for scenarios
- Create scenarios of feature
- Create development tasks
- Produce an acceptance test afterward

# Scenario essentials

## When a picture is worth a thousand words

The feature requires more breakdown than just acceptance criteria to create good scenarios. Sequence diagrams are one of the valuable artifacts of that process. A sequence diagram is a set of **actors** and **actions** that technically describes the workflow. Ideally, each couple of interaction arrows is a separate scenario with a **testable outcome**, but it might also be that the scenario includes several arrows from the diagram (Figure 12).

<img src="https://github.com/pavelozerov/images/blob/master/semantics-of-ubiquitous-language/figure12.png?raw=true" border="1" width="550"/>

**Figure 12**

A sequence diagram is the result of detailing the architecture overview diagram. Basically, you need to "zoom in" some part of the architecture view and describe it in another level of detail. A sequence diagram is extremely useful for the implementation process. Hence, it is related to the implementation level of details, whereas an architecture overview relates to the high level.

## Writing a good scenario

Once acceptance criteria are defined and the feature is described, this is the right time to go further and break down the sequence diagram even more and make scenarios. The scenario is a **representation of a sequence diagram** in the text (Figure 13).

<img src="https://github.com/pavelozerov/images/blob/master/semantics-of-ubiquitous-language/figure13.png?raw=true" border="1" width="550"/>

**Figure 13**

You may wonder why this is necessary if you already have a sequence diagram. Again, due to the variety of levels of detail. Every page related to a new feature is created using a specific template that auto-generates several chapters on the page, such as "Overview," "Architecture overview," "Requirements overview," "Implementation details," etc. Basically, each chapter is a dedicated area where people from different levels can put their information and share it with all involved people. High-level people may not be so interested in implementation details, but rather, they want to understand a feature's general behavior. Then, scenarios will help them get this! They will not check complex diagrams with many technical details but review short and straightforward behavioral representations from scenarios. And vice versa: if someone from a technical or implementation level of details is interested in some nuances of implementation, then diagrams and notes from developers will give such a possibility.

This is the essence of BDD - **to give everybody the needed level of understanding**.

But how good the written scenarios are? How to write scenarios correctly and make sure that they're written in a good way? For such a purpose, there is a set of rules, and following that, you can guarantee that the scenario has all the necessary elements to be successful, clear, and consistent.

First, scenario should be written to be easily readable and understandable. To achieve this, BDD uses neat Gherkin syntax. But just syntax is not enough. All the people working with BDD in your company must agree on **consistent structure and naming convention**.

Here is a cheat sheet that explains the Gherkin notation:

- **Given** - precondition (should be written in the past tense)
- **When** - action (some interaction between actors that triggers the expected result; should be written in present tense)
- **Then** - assert (**testable** outcome caused by the action)
- **And/But** - additional statements that might be used only in case something **must** be considered; it is better to avoid
- **Label (@)** - semantic tag that allows to group scenarios into the **same development unit**

## Actor-Action-Actor

Usually, ideal scenarios have several layers of details to be clear separately and together. The first layer is the title of the scenario. Since each feature and scenario will be transformed into a TO-DO ticket, developers should immediately understand what is required and what should be done. The title has to include an action that describes the original intent or a TO-DO instruction (or at least a result of a behavior). The second level of details is a bunch of given-when-then statements. If the content of the scenario has been opened, then a sequence of given-when-then statements should give an overview of what behavior the business waits for. Another level of detail is a group of scenarios united by the same label that must be implemented as one logical unit.

The **AAA** principle can be used to make the scenario breakdown simpler. Going back to the syntax of BDD, you may have noticed that this is kind of a modern mix of different "classical" techniques that combine "precondition, trigger, post-condition" notation from the use cases, "As a... I want... So that..." notation from the user stories and "Act, Assert, Arrange" notation from the science of unit testing. But in our case, **AAA stands for "Actor- Action-Actor"** (Figure 14).

<img src="https://github.com/pavelozerov/images/blob/master/semantics-of-ubiquitous-language/figure14.png?raw=true" border="1" width="550"/>

**Figure 14**

In your mind's eye, divide the scenario horizontally and vertically. **Each part of scenario should respond to the AAA principle matrix**. It means that every statement within the scenario, such as Given-When-Then, should include two actors and one action between them. This allows scenarios to be modular, and clarity remains on each level of detail.

## Scenario evaluation

Since there are a lot of criteria on how to write good scenarios, there is a scenario evaluation checklist that should be filled in for each scenario (Figure 15).

<img src="https://github.com/pavelozerov/images/blob/master/semantics-of-ubiquitous-language/figure15.png?raw=true" border="1" width="550"/>

**Figure 15**

Scenarios must be kept as short as possible because extra words (usually unneeded) complicate understanding. **Try not to use articles a/an/the/etc**. Although grammatically incorrect, it brings easier interpretation. Gherkin syntax is limited, but it's limited intentionally - such a strict structure forces you to express your thoughts concisely and clearly.

A scenario should not be written considering only one part (tech or business); it has to be clear to all the parties. **If scenario is unclear to someone, then obviously something is wrong with it**. Details in the scenario should be in balance because otherwise, it might have too much or not enough of them, and it will be hard to estimate the needed amount of work.

**Scenario should be testable!** Acceptance criteria related to the testing must be discussed and clarified for everyone. Furthermore, **if the outcome of some scenario cannot be automated**, it's **time to think of its necessity**. Since tests are implementation of business requirements and scenarios are their representation, **first of all, scenarios must have value for business**. Ideally, they must answer "What?" and "How?" questions.

## BDD essentials and benefits

Remember, BDD is **not a framework** or any kind of library (in a technical sense) that can be just taken and included in your project! There is no chance that you will get it to work after reading a couple of articles on the Internet and starting writing Given-When-Then constructions. Rather opposite, you will find out that BDD doesn't work for you. But don't worry, this is expected behavior! Because BDD is **not a form, but meaning**. Hence, using the Given-When-Then syntax itself will never solve your problems within a process. Furthermore, it can make the situation even worse. Let me give you an analogy (Figure 16).

<img src="https://github.com/pavelozerov/images/blob/master/semantics-of-ubiquitous-language/figure16.PNG?raw=true" border="1" width="550"/>

**Figure 16**

If we imagine the process as a square and BDD as a circle, then it's evident that these shapes don't match. But if we transform the process to the shape of a circle (as BDD is), we have two identical shapes that match ideally!

To adopt BDD, first, you must change your processes because its implementation is always about discipline. Once it is done, you will immediately see how BDD works for your team instead of being an annoying thing that requires additional attention.

The essence of making a shape of your internal process similar to the shape of BDD is to create the most significant BDD artifact: **unity-of-everything circle** (Figure 17).

<img src="https://github.com/pavelozerov/images/blob/master/semantics-of-ubiquitous-language/figure17.PNG?raw=true" border="1" width="550"/>

**Figure 17**

An entry point here is the business requirements, which are kind of a Wishlist. Using the feature breakdown process (described above), the wishlist will be represented by some Epic(s). Each consists of some Story(s) called a TO-DO list. This list has some Scenario(s) that will be represented for developers in some Task(s). And since Scenario(s) will become Test(s) in the end, we are **100% sure** that Code works exactly the same way as it was described in business requirements.

Hence, we have **1:1 mapping of everything**. But what does it mean? What is the benefit of it? Well, using this structure, we can easily remove one part of the chain, and... that's alright, nothing will happen because **these are replacement parts**! For example, if the team decides not to make tasks, the behavior is described on a story level; if there are no automated tests ready, scenarios cover that part, and stakeholders can always verify the requirements manually, etc.

The secret treasure of that approach is that **business requirements = TO-DO list = scenario(s) = tests = code**!

Last but not least, the BDD gem is the **ubiquitous language** (Figure 18).

<img src="https://github.com/pavelozerov/images/blob/master/semantics-of-ubiquitous-language/figure18.png?raw=true" border="1" width="550"/>

**Figure 18**

The image shows how we can describe the same case differently. If someone asks you to read some text on a sticker, there are many questions: which sticker do we talk about? What text color do we talk about? What sticker color, etc. But by saying that this is black text on a white sticker, I clearly specify things in a way that there is no chance to interpret them differently. I am sure we **really** understand the **same thing in the same way**. And that's the idea of BDD - to put people on the same level of understanding.

Another hidden treasure of BDD is the thing that can be called **reusable scenarios**. Following all the practices mentioned above (naming convention, Given-When-Then syntax, AAA matrix, etc.), you can map all possible product behaviors by just copying/pasting existing scenarios. Following the naming convention, you define a glossary of actors, and the AAA matrix forces you to clearly describe an interaction (behavior) between them. Hence, every new behavior (scenario) you want to describe, implement, or test will have the **same structure** (actors, syntax) but just **different intent**. So, in the case of BDD, copy/paste is **not a bad practice**, but vice versa - the best way to get a **consistency of a Living Documentation**.

> Adaption of BDD is like the creation of [impossible bottle](https://en.wikipedia.org/wiki/Impossible_bottle).

<img src="https://github.com/pavelozerov/images/blob/master/semantics-of-ubiquitous-language/figure19.jpeg?raw=true" border="1" width="550"/>

**Figure 19**

To assemble the model so that it cannot be removed without violating the integrity of the model or the bottle. The same is true here: **If any part of the process is missed/fails, the whole setup will be broken, and BDD will not work correctly**.

> Despite BDD being a collaborative practice, it cannot work without a clear driver who follows both directly related and side activities.

The sequence of all the actions above has several goals. Of course, collaboration, creating a contract between involved parties, and clearness. **But one of the goals is also to transform scenarios into executable specifications by automated tests**.

> - BDD is not a form, but the meaning behind it!
> - Unity-of-everything circle → business requirements = TO-DO list = scenario(s) = tests = code!

## SOUL highlights (keynote)

**What is BDD?**

BDD is not just the given-when-then syntax, scenarios, user stories, reports, or acceptance criteria; it's about a seamless collaboration when teams provide only what is valuable and matters.

**What is the goal of BDD?**

To teach people from different levels to speak the same language, understand each other, and work in collaboration on living documentation. So, there is no chance to interpret things differently.

**What are BDD essentials in a nutshell?**

- Input – business requirements
- Output – scenarios
- Outcome – a shared understanding of system behavior and its automation

**Why there is no chance to fail using BDD?**

Everything is connected. If you want to change business requirements, an item in the product backlog must be created and prioritized first. Then, it must be analyzed, and new acceptance criteria with sequence diagrams should be clarified. Then, scenarios should be updated. Only after that is it possible to change the code and related tests. This is a power of Living Documentation that is always up-to-date.

Contract. Such an agreement between all involved parties. Like with a real contract, people put their signatures, meaning they agree on conditions (requirements) that should be met. Otherwise, the deal (feature/product) will fail.

The essence of making BDD is like creating a ship in a bottle: assembling the model so that it cannot be removed without violating the integrity of either the model or the bottle. The same is true here: if any part of the process is missed/failed, then the whole setup will be broken, and BDD will not work correctly.

## References

- [Behavior Driven Development](https://en.wikipedia.org/wiki/Behavior-driven_development)
- [Gherkin](https://cucumber.io/docs/gherkin/)
- [Feature Mapping – a simpler path from stories to executable acceptance criteria](https://johnfergusonsmart.com/feature-mapping-a-simpler-path-from-stories-to-executable-acceptance-criteria/)
- [Impossible bottle (source: wikipedia.org, author: Bin im Garten)](https://commons.wikimedia.org/wiki/File:Buddelschiff_2012_PD_06.JPG)
