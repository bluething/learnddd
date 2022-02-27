# Analyzing Business Domains

To design and build an effective solution, we have to understand the problem. To understand the problem, we have to understand the organization's business strategy, and what value it seeks to gain by building the software.

### What is a business domain?

A company's main area of activity. A company can operate in multiple business domains and the domain can change.

### What is a subdomain?

A subdomain is a fine-grained area of business activity. All of a company's subdomains form its business domain.  
Doing complexity assessment can help us to differentiate subdomain type.  
When looking for subdomains, it's important to identify business functions that are not related to software, acknowledge them as such, and focus on aspects of the business that are relevant to the software system you are working on.

#### Core subdomains

- A core subdomain is what a company does differently from its competitors (competitive advantage).
- Usually complex.  
- Can change often.  
- Must implement in-house.
- Core subdomains are not necessarily technical.  
- Also called core domains.
- Affect software design.  
- Require implementation of the most advanced engineering techniques.

#### Generic subdomains

- Generic subdomains are business activities that all companies are performing in the same way.
- Usually complex and hard to implement.
- Don't provide any competitive edge for the company. So, we don't need innovation or optimization.  
- Solved problem.
- "known unknowns", we can search and implement best practice.

#### Supporting subdomains

- Supporting subdomains do not provide any competitive advantage.  
- Usually simple.

### Identifying Subdomain Boundaries

Subdomains resemble sets of interrelated, _coherent_ use cases. Usually involve the same actor, the business entities, and they all manipulate a closely related set of data.  
So, start from the use cases.