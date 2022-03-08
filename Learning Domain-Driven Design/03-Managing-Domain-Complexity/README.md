# Managing Domain Complexity

Successful project need a ubiquitous language that used for communication by all stakeholder. The language should reflect the domain experts’ mental models.  
The language must:  
- Clear and consistent. 
- Free of ambiguity. 
- Implicit assumptions. 
- Extraneous details.

The problem is the domain experts mental models can be inconsistent.

When same term have different meaning in different domain:  
1. Bring the model into the other model, causing new complexity where it's not needed.
2. Simplified the model according other model, causing the model can't fulfil the domain needs.

The solution?  
1. Create a single model. 
This model will be suitable for everything but eventually are effective for nothing.  
We have below problems:  
    1. The complexity to filtering out domain details.  
    2. The complexity of finding what we do need.  
    3. The complexity of keeping the data in a consistent state.
2. Use domain as a prefix.  
The disadvantages:  
    - When should each model be used?  
    - The implementation of the model won’t be aligned with the ubiquitous language.

Then, what we must do? _Create the context_.

## Bounded Context

To solve inconsistent domain expert mental model we must divide the ubiquitous language into multiple smaller languages, then assign each one to the explicit context in which it can be applied, its _bounded context_.    
A ubiquitous language in one bounded context can be completely irrelevant to the scope of another bounded context.

Please remember, a ubiquitous language is not universal. The meaning of ubiquitous only in the boundaries of its bounded context.

The consistency of the ubiquitous language only helps to identify the widest boundary of that language.

### How big the boundary?

It depends on the specific problem domain. It can be wide (following the business domain's inherent contexts) or narrow (divided into smaller problem domain). It's a strategic design decision.  
If the boundary wide it is hard to keep it consistent, but if it's small we will have more integration overhead the design induces.  

Therefore, size is not a deciding factor. Just:  
1. Keep our models useful.  
2. Align the bounded contexts sizes with our business needs and organizational constraints.

### What the relation with subdomains?

Subdomains are result of analyzing business domain to identify interrelated use cases (discovered). Bounded context are result of strategic design decision (designed).

Theoretically, though impractically, a single model (bounded context) could span the entire business domain (for small system).  
When there was a conflict in the model we can split the model following domain expert mental model. Then, decompose the model again if the model hard to maintain.

In some cases, it may be reasonable to use different models of the same subdomain to solve different problems.

The bounded context pattern is the domain-driven design tool for defining physical and ownership boundaries.

### Physical Boundaries

Each bounded context should be implemented as an individual service/project.  
If bounded context contains multiple subdomains, then each subdomain act as logical boundary (different namespaces, modules, or packages).

### Ownership Boundaries

A bounded context should be implemented, evolved, and maintained by one team only. But a single team can own multiple bounded contexts.