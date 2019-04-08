# DDD for me

## Strategic Design:
* segregate domain models with **Bounded Context**
* develop **Ubiquitous Language** as your domain model whithin a Bounded Context
* engage **Domains Expert**
* deal with unbounded complexity of legacy systems leveraging **Subdomains**
* integrate multiple Bounded Context using **Context Mapping**

### Bounded Context:
>a semantic context boundary
When it refers to a key strategic initiative of the business, it's called **Core
Domain**.
A Core Domain is developed to distinguish your organization competitively from all others. 
So you choose wisely what should be part of your Core Domain and what should not. 
This is the primary value proposition of DDD, and you want to invest appropriately 
by committing your best resources to a Core Domain.
There should also be a separate source code repository for each Bounded Context. 
It is possible that one team could work on multiple Bounded Contexts , but multiple 
teams should not work on a single Bounded Context.

### Subdomains:
>a sub-part of your overall business domain
You can think of a Subdomain as representing a single, logical domain model.
Most business domains are usually too large and complex to reason about as a whole.
Subdomains can be used to logically break up your whole business domain.
There are three main types of *Subdomains*:
* *Core Domains*: this is where you are making a strategic investment in a single, well-defined
domain model, committing significant resources for carefully crafting your Ubiquitous
Language in an explicit Bounded Context.
* *Supporting Subdomains*: this is a modeling situation that calls for custom development,
because an off-the-shelf solution doesn’t exist. However, you will still not make the kind of
investment that you have made for your Core Domain
* *Generic Subdomain*: this kind of solution may be available for purchase off the shelf but may
also be outsourced or even developed in house by a team that doesn’t have the kind of elite
developers that you assign to your Core Domain or even a lesser Supporting Subdomain.

### Context Mapping:
>the mapping between two Bounded Context
