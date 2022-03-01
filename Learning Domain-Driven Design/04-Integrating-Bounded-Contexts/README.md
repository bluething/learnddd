# Integrating Bounded Contexts

Bounded context pattern will protect the consistency of ubiquitous language and enables modeling. The boundary specifying the purpose for the model.
Models in different bounded contexts can be evolved and implemented independently.  
The bounded context need to interact with other bounded context to achieve system goals.  
There will always be touchpoints between bounded contexts. These are called contracts.

## Relationships and integrations between bounded contexts

### Cooperation

This pattern can be implemented by the team that have:  
- Well established communication.  
- Dependent goals.

#### Partnership

![partnership](https://github.com/bluething/learnddd/blob/main/images/partnership.png?raw=true)

One team can notify a second team about a change in the API, and the second team will cooperate and adapt no drama or conflicts.  
The teams can work out the differences and choose the most appropriate solution. They cooperate in solving any integration issues that might come up.

This pattern might not be a good fit for geographically distributed teams.

#### Shared Kernel

![shared kernel](https://github.com/bluething/learnddd/blob/main/images/sharedkernel.png?raw=true)

The same model of a subdomain implement in multiple bounded context. The shared model has to be consistent across all the bounded contexts that are using it.  
A change made to the shared model has an immediate effect on all the bounded contexts. Only share that needed by both bounded context.  
If the changes not immediately implemented we will have stale implementations of the shared kernel, leading to data corruption and/or runtime issues.

The shared kernel will consist only of integration contracts and data structures that are intended to be passed across the bounded contexts boundaries.

The decision when to use shared kernel is the cost of duplication versus the cost of coordination.  
The factors that influence it are volatility of the model. The more frequently it changes, the higher the integration costs will be.
Use it when the cost of duplication is higher than the cost of coordination.

The shared kernel will naturally be applied for the subdomains that change the most: the core subdomains.

A common use case for implementing a shared kernel:  
- When communication or collaboration issues prevent implementing the partnership pattern.  
- The gradual modernization of a legacy system.

### Customer–Supplier

![customer supplier](https://github.com/bluething/learnddd/blob/main/images/customersupplier.png?raw=true)

The supplier provides a service for its customers. The service provider is "upstream" and the customer or consumer is "downstream".  
Both teams (upstream and downstream) can succeed independently. Consequently, in most cases we have an imbalance of power: either the upstream or the downstream team can dictate the integration contract.

#### Conformist

![comformist](https://github.com/bluething/learnddd/blob/main/images/conformist.png?raw=true)

The upstream team has no real motivation to support its clients needs. They just provides the integration contract, defined according to its own model.

#### Anticorruption Layer

![anticorruption layer](https://github.com/bluething/learnddd/blob/main/images/anticorruptionlayer.png?raw=true)

The upstream power same with conformist, but now the downstream bounded context is not willing to conform.  
There are translation process from upstream bounded context model into their own model, creating anticorruption layer.

There are scenario when creating anticorruption layer:  
- When the downstream bounded context contains a core subdomain.  
- When the upstream model is inefficient or inconvenient for the consumers needs.  
- When the suppliers contract changes often.

#### Open-Host Service

![open host](https://github.com/bluething/learnddd/blob/main/images/openhostservice.png?raw=true)

This time, the dominant power is in the downstream side.  
To protect the consumers from changes in its implementation model, the upstream supplier decouples the implementation model from the public interface. This interface expose a protocol convenient for the consumers, expressed in an integration-oriented language (published language).

![published language](https://github.com/bluething/learnddd/blob/main/images/publishedlanguage.png?raw=true)

### Separate Ways

This collaboration option is not to collaborate at all.  
The reason why this type arise:  
- There are communication difficulties driven by the organizations size or internal politics.  
- When the subdomain in question is generic, and if the generic solution is easy to integrate, it may be more cost-effective to integrate it locally in each bounded context.  
- Differences in the bounded contexts models that can't be tackle by conformist or anticorruption layer.

## Context Map

![context map](https://github.com/bluething/learnddd/blob/main/images/contextmap.png?raw=true)

The context map is a visual representation of the systems bounded contexts and the integrations between them.  
This gives us valuable strategic insight on multiple levels:  
- High-level design  
  A context map provides an overview of the system’s components and the models they implement.
- Communication patterns  
  A context map depicts the communication patterns among teams.
- Organizational issues  
  A context map can give insight into organizational issues.

A context map should be introduced into a project right from the get-go, and be updated to reflect additions of new bounded contexts and modifications to the existing one.  
Maintenance of context map is a shared effort because each team is responsible for updating its own integrations with other bounded contexts.

![complicated context map](https://github.com/bluething/learnddd/blob/main/images/complicatedcontextmap.png?raw=true)  
But, creating and maintaining context map is a challenging task. This happens when there are multiple integration phase.