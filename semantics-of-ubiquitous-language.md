# Semantics of Ubiquitous Language (SOUL)

## Abstract

Each IT organization has an intention to make a strong competence of analysis, where all features go through a certain process that includes various levels of research and testing, such as business, functional, technical, etc. Companies put a lot of effort in order to reach this. The common thing of all these strives is a wish to make a product that has **value**. Development always starts from the idea with the business requirements behind. But how to make business requirements clear and consistent? How to define them in a way to reflect the original intent without distortion? How to make sure they have value? The key is a **Behavior Driven Development** concept.

## Specification vs Living Documentation

What does the specification process look like in a "classic" way? In this structure (Figure 1), the analyst becomes a bottleneck, because this is the only person, who commits to source of information (usually this is some collaboration software, e.g., Confluence).

<img src="https://github.com/pavelozerov/images/blob/master/semantics-of-ubiquitous-language/figure1.png?raw=true" border="1" width="200"/>

**Figure 1**

This means that any change in future must be done by the analyst and rest of the team does not control these changes anyhow. Worse, they may not even know about them. So, this is insidious process, the main disadvantage of which is the speed of changes, because different things are always stuck in the queue. Situation is also complicated by the fact, that teams work at own pace, which means that analyst will never receive the feedback on what is done immediately. It might happen even new feature description process already started. Analyst becomes a "gateway" and in this state can only hold limited amount of things in the head. Now there are two queues between which analyst have to switch: one with TO-DO things, that can be handled step by step only, and another one with things-to-be-changed based on a late feedback from team. But as you know, between two stools one falls to the ground.

Why BDD is a problem solver? Because of a **Living Documentation**. Instead of having the analyst role as a "bottleneck", it transforms it into supporting role (Figure 2).

<img src="https://github.com/pavelozerov/images/blob/master/semantics-of-ubiquitous-language/figure2.png?raw=true" border="1" width="300"/>

**Figure 2**

In this structure the analyst still works closely with different teams, but with one important difference. Instead of making changes by oneself, analyst just collects all the needed information, structures it and creates a shared place, where all involved people work together. This shared page have different chapters (specifically for developers, QA, product owners, etc.) that must be filled by responsible team members. With this approach analyst is not the bottleneck anymore, since **now everybody is responsible for the documentation and knowledge sharing**.

> - If something is **not structured**, it's probably **not documented**, which means that it **does not exist**!
> - ~~When everyone is responsible, no one is responsible~~ → when everyone is responsible, then **structure** is responsible!

## Tower of Babel

What is Behavior Driven Development (BDD) for? Someone can say that this is something to structure the documentation and knowledge source or to bring the clearness to the team, or to have a certain process of analysis, implementation and testing, or anything else. But all this really doesn't matter. Of course, all these answers are correct in their own way, but none of them says anything about the root cause. **And the root cause is Legacy in the way we specify things**. Let me guess, many specifications have been written during over the past few years, but most of the information have no clear structure? Business descriptions are often mixed up with some technical pages, which are partially outdated? Congratulations, your company is one of many that have got things out of control.
This led us to a situation, when it's quite hard to find the consistent information, since all the related pieces are split within different places and some are not documented at all. It means that needed information about how do things work has to be collected from different people within a team, and there is a very high probability that this information is obsolete. In sum, the problem is that such collective knowledge is usually not structured. **And if something is not structured it's probably not documented, which means that it does not exist**.

Okay, but if Legacy is the root cause of a documentation lack, what is the root cause of Legacy then? Well, the answer is quite simple - the **communication lack**. In order to make an example more memorable, we can refer to the Tower of Babel myth (Figure 3).

<img src="https://github.com/pavelozerov/images/blob/master/semantics-of-ubiquitous-language/figure3.png?raw=true" border="1" width="400"/>

**Figure 3**

Let’s make a parallel with an IT industry. In the beginning of the project people discuss the idea and all seems to be clear - people speak on the same language. But during the project moves further, and more people get involved, in the end of the day there is always the lack of communication as a result. The stage, when it happens might vary, but it definitely happens. And since the moment when people start to speak different languages, development is doomed to become a typical IT project, where you need to go through 9 circles of Dante's hell before it will be finished (Figure 4).

<img src="https://github.com/pavelozerov/images/blob/master/semantics-of-ubiquitous-language/figure4.png?raw=true" border="1" width="400"/>

**Figure 4**

Exactly the same happened to people in Tower of Babel myth - they were failed with own initiative to build a tower tall enough to reach heaven. Because team cannot be successful if people can no longer understand each other in the same way. BDD seeks to help to avoid this scenario, as it teaches people how to collaborate and speak the same language.

## Root causes

Before we will go further in order to discover the implementation of BDD approach, let's have a quick look back first. The sole purpose of mentioning Tower of Babel myth was to show the importance of the communication. This is the only condition, which makes teams successful, because it creates the collaboration. It may not be obvious, but it is the only cure for Legacy, because it is exactly its root cause (Figure 5).

<img src="https://github.com/pavelozerov/images/blob/master/semantics-of-ubiquitous-language/figure5.png?raw=true" border="1" />

**Figure 5**

Let's now go deeper into details. What is the root cause of communication lack? All people think differently. This is known fact and essentially this is awesome, because different thinking allows people to see things from different angles; thus we make discoveries and progress. However, such the uniqueness, the result of which is a different way of thinking, is the reason that **people understand things differently**. And exactly different understanding is the root cause of communication lack. For example, if you will ask some group of people to describe the same thing, most probably as a result you will get as many answers as there are respondents. So, just communication is not enough. Even well-coordinated communication is not enough. There should be **no room for different interpretations**, which means that communication should always provide **clearness
and collaboration**. Based on that we can extend previous drawing with a new dependency (Figure 6).

<img src="https://github.com/pavelozerov/images/blob/master/semantics-of-ubiquitous-language/figure6.png?raw=true" border="1" width="550"/>

**Figure 6**

And the next logical question is: how can we fix this? However, in order to answer this question, let's take a look on a Figure 6. According to it, the **main dependency is a different understanding**. Let's dwell upon this in a more detail. What exactly is this difference? Why does it actually appear?

First possible reason that appears in mind is a remoteness of a team. It's quite common thing in IT, when several “virtual teams” work on the same product or a feature. But you might have also noticed that this issue often occurs within one team, which means that remoteness is not really a reason. Well, the real reason is also clear, and is related to the level of details people work on. There are different groups of people that need different level of details. Stakeholders, product managers and product owners work on the highest level and not really involved into technical details or implementation process (sadly). Usually they only need to have an overview. Architects and analysts work on a bit lower - technical - level. Based on high-level requests they transform business requirements into technical specifications and behavioral scenarios. Developers and QA engineers work on the lowest - implementation level. And this is exactly the place, where "different understanding" is born.

Let's try to figure out how we can fix this. Does BDD is designed for that? Of course!

In the essence, BDD is nothing but a **collaborative** practice that aims/helps to deliver higher value software more effectively by making a balance between level of details that business and development team need. It involves a lot of parties, and it's essentially important that they would be satisfied with the requirements, described scenarios and implementation details. That's why analysts, architects, developers and QA have to move to the same level of details and work can only be started, when all the related sides are agreed on scenarios (Figure 7).

<img src="https://github.com/pavelozerov/images/blob/master/semantics-of-ubiquitous-language/figure7.png?raw=true" border="1" width="350"/>

**Figure 7**

Such an agreement between all the related parties is very similar to **a contract**. Like with a real contract people put own signatures, which means that they agree on conditions (requirements) that should be met. Otherwise, deal (feature/product) will be
failed. Anyway, it's also important to remember that during the implementation there might be such a situation, when contract (specification) might be changed based on some research or limitations. This is normal situation, since BDD is a collaborative process which allows keeping information constantly up-to-date as a **Living Documentation**. It means that specification can be changed, but only on one mandatory condition: **a new contract should be made, where all the changes are reflected, and all people are agreed on**. So, there are plenty of things that can be improved using BDD, such as consistency, clearness, confidence, automation and time-to-delivery; by this we can highlight such benefits as clear and common definition of done, and acceptance criteria, shorter period from business requirements to production and implementation that matches requirements.

The most important thing to remember is that BDD is all about working together where teams provide result that is valuable and really matters (Figure 8).

<img src="https://github.com/pavelozerov/images/blob/master/semantics-of-ubiquitous-language/figure8.png?raw=true" border="1" width="400"/>

**Figure 8**

## Implementation of BDD

Development always starts from the idea. Usually all the ideas-without-analysis go to the specific **product backlog (inbox)**. Once TO-DO list is prioritized by Product Owner (or another responsible person), it goes to a **product roadmap**. Such tickets are usually called Epics, because they describe the idea in general. Epics are some kind of containers for features they consist of. The next step is a feature mapping: this is a collaborative process involving different teams, that aims to discuss details of feature requirements, architecture, implementation, etc.

When analysis is ready developers can start to work on **feature implementation** using tickets from **development backlog**. When development finished, there is a QA phase when engineers prepare **automated tests** that are 1:1 implementation of the behavioral scenarios created during the feature mapping process. When functional testing is done, feature moves to **acceptance testing**, where analyst and business have to make sure that current implementation does exactly the same what is in the business requirements (Figure 9).

<img src="https://github.com/pavelozerov/images/blob/master/semantics-of-ubiquitous-language/figure9.png?raw=true" border="1" width="550"/>

**Figure 9**

# Feature essentials

## Feature Mapping

The biggest advantage of BDD is that it let people to use the same language to understand requirements in the same way. In order to achieve this, there is such a technique called [Feature Mapping](https://johnfergusonsmart.com/feature-mapping-a-simpler-path-from-stories-to-executable-acceptance-criteria/). According to its author, [John Ferguson Smart](https://johnfergusonsmart.com/author/), in a nutshell the process goes something like this:

- Define a feature or story, or pick one from the backlog
- Understand what actors are involved in the story
- Break the feature into tasks to identify the main flows
- Identify examples that illustrate a principle or variant flow. Ask questions like "But what if...", "what else could lead to this outcome", "what other outcomes might happen", and use the answers to create new examples. Use rules to explain and give context to your examples
- Rinse and repeat for other rules and examples
- Create Executable Specifications: automate the main high-level flows with pending steps

> Feature Mapping is collaborative activity, which makes the whole team work together in order to define **value** of the feature.

<img src="https://github.com/pavelozerov/images/blob/master/semantics-of-ubiquitous-language/figure10.png?raw=true" border="1" width="550"/>

**Figure 10**

## Feature breakdown

Feature Mapping starts with a breakdown. What is the Feature Breakdown? This is a process when a team moves from general to particular, and turns development unit (Epic) into modules. Let's have a quick recap of what team already has:

- Prepared product backlog
- Architecture overview of an Epic
- Business requirements described as user story (Figure 11)

<img src="https://github.com/pavelozerov/images/blob/master/semantics-of-ubiquitous-language/figure11.png?raw=true" border="1" width="550"/>

**Figure 11**

What else we then need? According to the essence of Feature Mapping, the goal of such an activity is to discover **acceptance criteria** and business requirements. For instance, based on the story from Figure 11, the analyst might note down the following initial **business rules**:

- Amount of items added to stock equals to the amount of items customer returns
- In case of return goods must be returned to merchant's stock
- Customer can get refund

So, what is the essence of Feature Mapping and breakdown then? What modules do we talk about? There are **several of them**:

- Create acceptance criteria based on business requirements
- Create sequence diagrams as a basis for scenarios
- Create scenarios of feature
- Create development tasks
- Produce an acceptance testing afterwards

# Scenario essentials

## When a picture is worth a thousand words

In order to create good scenarios, feature requires a bit more breakdown than just acceptance criteria. Sequence diagrams are one of the useful artifacts of that process. Basically sequence diagram is a set of **actors** and **actions** that describes the workflow in a technical way. Ideally each couple of interaction arrows is a separate scenario with a **testable outcome**, but it might also be that scenario includes several arrows from the diagram (Figure 12).

<img src="https://github.com/pavelozerov/images/blob/master/semantics-of-ubiquitous-language/figure12.png?raw=true" border="1" width="550"/>

**Figure 12**

Sequence diagram is the result of detailing the architecture overview diagram. Basically, you just need to "zoom in" some part of architecture view and start to describe it on another level of details. Sequence diagram is extremely useful for implementation process, hence it is related to implementation level of details, whereas architecture overview relates to the high-level.

## Writing a good scenario

Once acceptance criteria are defined and feature is described, then this is the right time to go further and breakdown sequence diagram even more, and make scenarios. Scenario is a **representation of sequence diagram** in text (Figure 13).

<img src="https://github.com/pavelozerov/images/blob/master/semantics-of-ubiquitous-language/figure13.png?raw=true" border="1" width="550"/>

**Figure 13**

You may wonder why this is necessary if you already have a sequence diagram? Again due to the variety of level of detail. Every page related to a new feature is created using a specific template that auto-generates several chapters on the page, such as "Overview", "Architecture overview", "Requirements overview", "Implementation details", etc. Basically, each chapter is a dedicated area, where people from different levels can put own information in order to share it with all involved people. But high-level people maybe not so interested in implementation details, but rather they want to understand the behavior of a feature in general. Then scenarios will help them to get this! They will not check complex diagrams with lots of technical details, but rather will check short and straight forward behavioral representation from scenarios. And vice versa: if someone from a technical or implementation level of details will be interested in some nuances of implementation, then diagrams and notes from developers will give such a possibility.

Basically, this is the essence of BDD - **to give everybody needed level of understanding**.

But how good the written scenarios are? How to actually write scenarios properly and make sure that they're written in a good way? For such a purpose there is a set of rules, following that you can guarantee that scenario has all the necessary elements to be successful, clear and consistent.

First, scenario should be written in a simple way to be easily readable and understandable. To achieve this BDD uses neat Gherkin syntax. But just syntax is not enough. Within your company all the people, who work with BDD should agree on **consistent structure and naming convention**.

Here is a cheat sheet that explains the Gherkin notation:

- **Given** - precondition (should be written in the past tense)
- **When** - action (some interaction between actors that triggers the expected result; should be written in present tense)
- **Then** - assert (**testable** outcome caused by the action)
- **And/But** - additional statements that might be used only is case if something **must** be considered; better to avoid
- **Label (@)** - semantic tag that allows to group scenarios into the **same development unit**

## Actor-Action-Actor

Usually ideal scenarios have several layers of details in order to be clear both separately and together. First layer is a title of the scenario. Since each feature and scenario will be transformed into TO-DO ticket, developers should immediately understand what is required and should be done. Title has to include an action that describes the original intent or a TO-DO instruction (or at least a result of a behavior). Second level of details is a bunch of given- when-then statements. If content of the scenario has been opened, then sequence of given-when-then statements should give an overview of what behavior business waits for. Another level of details is a group of different scenarios united by the same label, that have to be implemented as one logical unit.

In order to make the scenario breakdown simpler, the **AAA** principle can be used. Going back to the syntax of BDD, you may have noticed that this is kind of a modern mix of different "classical" techniques that combine "precondition, trigger, post-condition" notation from the use cases, "As a... I want... So that..." notation from the user stories and "Act, Assert, Arrange" notation from the science of unit testing. But in our case **AAA stands for "Actor- Action-Actor"** (Figure 14).

<img src="https://github.com/pavelozerov/images/blob/master/semantics-of-ubiquitous-language/figure14.png?raw=true" border="1" width="550"/>

**Figure 14**

In your mind's eye divide scenario horizontally and vertically. **Each part of scenario should respond to the AAA principle matrix**. It means, that every single statement within scenario, such as Given- When-Then should include 2 actors and 1 action between them. This allows scenarios to be modular and clearness remains on each level of details.

## Scenario evaluation

Since there is a lot of criteria on how to write good scenarios, there is a scenario evaluation checklist that should be filled in for each scenario (Figure 15).

<img src="https://github.com/pavelozerov/images/blob/master/semantics-of-ubiquitous-language/figure15.png?raw=true" border="1" width="550"/>

**Figure 15**

Scenarios have to be kept as short as possible, because extra words (that are usually unneeded) make understanding more complicated. **Try not to use articles a/an/the/etc**. Despite the fact that grammatically this is incorrect, it brings easier interpretation. Gherkin syntax is limited, but it's limited intentionally. Such a strict structure forces to express your thoughts concisely and clearly.

Scenario should not be written considering one part only (tech or business), but it has to be clear for all the parties. **If scenario is not clear to someone, then obviously there is something wrong with it**. Details in the scenario should be in balance, because otherwise it might have too much or not enough of them, and it will be hard to estimate needed amount of work.

**Scenario should be testable!** Acceptance criteria have to be discussed and clear for all the people related to the testing. Furthermore, **if the outcome of some scenario cannot be automated**, then maybe it's **time to think of its necessity**. Since tests are implementation of business requirements and scenarios are their representation, **first of all scenarios must have value for business**. Ideally they have to answer "What?" and "How?" questions.

## BDD essentials and benefits

Remember, BDD is **not a framework** or any kind of library (in a technical sense), that can be just taken and included to your project! There is no chance that after reading a couple of articles on the Internet and start writing Given-When-Then constructions you will get it to work. Rather the opposite, you will find out that BDD doesn’t work for you. But don’t worry, this is expected behavior! Because BDD is **not a form, but meaning**. Hence, usage of Given-When-Then syntax itself will never solve your problems within a process. Furthermore, it can make the problem even worse. Let me give you an analogy (Figure 16).

<img src="https://github.com/pavelozerov/images/blob/master/semantics-of-ubiquitous-language/figure16.PNG?raw=true" border="1" width="550"/>

**Figure 16**

If we imagine the process as a circle and BDD as a square, then it’s obvious that these shapes don’t match. But if we transform the process to the shape of a circle as well as BDD, then we have 2 identical shapes that match ideally!

This is exactly what I mean - in order to adapt BDD, first you need to change your processes, because implementation of BDD is always about discipline. And once it is done, you will immediately see how BDD works for your team, instead of being an annoying thing that requires additional attention.

The essence of making a shape of your internal process similar to the shape of BDD is to create the greatest BDD artifact: **unity-of-everything circle** (Figure 17).

<img src="https://github.com/pavelozerov/images/blob/master/semantics-of-ubiquitous-language/figure17.PNG?raw=true" border="1" width="550"/>

**Figure 17**

An entry point here is the business requirements, which are kind of a Wishlist. Using the feature breakdown process (described above) Wishlist will be represented by some Epic(s). Each of them consists of some Story(s) that can be called a TO-DO list. This list has some Scenario(s) that will be represented for developers in some Task(s). And since Scenario(s) will become Test(s) in the end, we are **100% sure** that Code works exactly the same way as it was described in business requirements.

Hence, we have **1:1 mapping of everything**. But what does it mean? What is the benefit of it? Well, using this structure we can easily remove one part of the chain and... that’s alright, nothing will happen, because **these are replacement parts**! For example, if team decided not to make tasks, then behavior is anyway described on a story level; if there is no automated tests ready, then scenarios cover that part and stakeholders are always able to verify the requirements manually, etc.

The secret treasure of that approach is that **business requirements = TO-DO list = scenario(s) = tests = code**!

Last, but not least BDD gem is the **ubiquitous language** (Figure 18).

<img src="https://github.com/pavelozerov/images/blob/master/semantics-of-ubiquitous-language/figure18.png?raw=true" border="1" width="550"/>

**Figure 18**

The image shows how we can describe the same case differently. If someone asks you to read some text on a sticker, then immediately there are lots of questions: which sticker do we talk about? What text color do we talk about? What sticker color, etc. But by saying that this is a black text on white sticker, I clearly specify things in the way that there is no chance to interpret them differently. I am sure that we **really** understand the **same thing in the same way**. And that’s idea of BDD - to put people to the same level of understanding.

Another hidden treasure of BDD is the thing that can be called **reusable scenarios**. Following all the practices mentioned above (naming convention, Given-When-Then syntax, AAA matrix, etc.) you’re able to make the map of all possible behaviors of the product by just copy/paste of existing scenarios. By following the naming convention you define glossary of actors and AAA matrix forces you to clearly describe an interaction (behavior) between them. Hence, every new behavior (scenario) you want to describe, implement or test will have the **same structure** (actors, syntax), but just **different intent**. So, in case of BDD copy/paste is **not a bad practice**, but vice versa - the best way to get a **consistency of a Living Documentation**.

> Adaption of BDD is like creation of [impossible bottle](https://en.wikipedia.org/wiki/Impossible_bottle).

<img src="https://github.com/pavelozerov/images/blob/master/semantics-of-ubiquitous-language/figure19.jpeg?raw=true" border="1" width="550"/>

**Figure 19**

To assemble the model so that it cannot be removed without violating the integrity of either the model or the bottle. The same is here: **if any part of the process will be missed/failed, then the whole setup will be broken and BDD will not work properly**.

> Despite BDD is a collaborative practice it cannot work without a clear driver, who follows both directly related and side activities

The sequence of all the actions above has several goals. Of course, collaboration, creation of contract between involved parties and clearness. **But one of goals is also to transform scenarios into executable specification by automated tests**.

> - BDD is not a form, but the meaning behind!
> - Unity-of-everything circle → business requirements = TO-DO list = scenario(s) = tests = code!

## SOUL highlights (keynote)

**What is BDD?**

BDD is not just the given-when-then syntax, scenarios, user stories, reports or acceptance criteria; it’s about a seamless collaboration, when teams provide only what is valuable and really matters.

**What is the goal of BDD?**

To teach people from different levels to speak on the same language, understand each other and to work in collaboration on living documentation. So, there is no chance to interpret things differently.

**What are BDD essentials in a nutshell?**

- Input – business requirements.
- Output – scenarios.
- Outcome – common understanding of a system behavior and its automation.

**Why there is no chance to fail using BDD?**

Everything is connected. If you want to change business requirement, first an item in product backlog must be created and prioritized. Then it must be analyzed and new acceptance criteria with sequence diagrams should be clarified. Then scenarios should be updated. And only after that it's possible to change the code and related tests. This is a power of Living Documentation that is always in up-to-date state.

Contract. Such an agreement between all involved parties. Like with a real contract people put own signatures, which means that they agree on conditions (requirements) that should be met. Otherwise, deal (feature/product) will be failed.

The essence of making BDD is like creation of a ship in a bottle; to assemble the model so that it cannot be removed without violating the integrity of either the model or the bottle. The same is here: if any part of the process will be missed/failed, then the whole setup will be broken and BDD will not work properly.

## References

- [Behavior Driven Development](https://en.wikipedia.org/wiki/Behavior-driven_development)
- [Gherkin](https://cucumber.io/docs/gherkin/)
- [Feature Mapping – a simpler path from stories to executable acceptance criteria](https://johnfergusonsmart.com/feature-mapping-a-simpler-path-from-stories-to-executable-acceptance-criteria/)
- [Impossible bottle (source: wikipedia.org, author: Bin im Garten)](https://commons.wikimedia.org/wiki/File:Buddelschiff_2012_PD_06.JPG)
