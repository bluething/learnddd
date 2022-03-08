# Discovering Domain Knowledge

## Business Problem

The software systems we are building are solutions to business problems. This problem appears both at the business domain and subdomain levels.  
Subdomains are finer-grained problem domains whose goal is to provide solutions for specific business capabilities.

## The key for knowledge discovery is communication

To design an effective software solution, we have to grasp at least the basic knowledge (from domain expert) of the business domain.  
The software has to mimic the domain experts way of thinking about the problem, their mental models.

![knowledge dicovery](https://github.com/bluething/learnddd/blob/main/images/knowledgedicovery.png?raw=true)  
Remember, don't translate business requirement into source code. _Learn and understand the requirements!_  
If we only translate domain expert mental model then we will lose information in each layer of communication.

Almost all software projects require the collaboration of stakeholders in different roles.

A software project's success depends on the effectiveness of knowledge sharing between domain experts and software engineers.

## Ubiquitous Language

To communicate effectively all stakeholders need to speak in the same language.  
DDD calls for cultivating a single language for describing the business domain: the ubiquitous language.  
The aim is to frame the domain experts understanding and mental models of the business domain in terms that are easy to understand.

The language must have _consistency_ to eliminate the need for assumptions and should make the business domain’s logic _explicit_.  
Ubiquitous language demands a single meaning for each term. There are _no place for synonym_, use each term explicitly in its specific context.

## Model of the Business Domain

A model is not a copy of the real world but a human construct that helps us make sense of real world systems. All models have a purpose, and an effective model contains only the details needed to fulfill its purpose.  
For example map, there are many type of maps with different purpose.

In its essence, a model is an _abstraction_.

The business domain is supposed to capture the domain experts mental models.  
The model has to reflect the involved business entities and their behavior, cause and effect relationships, and invariants.

The only reliable way to verify a business domain understanding is to converse with domain experts and do it in the language they understand, the language of the business.

The ubiquitous language is supposed to address the specific problem the software is intended to solve.  
The language should be continuously reinforced throughout the project: requirements, tests, documentation, and even the source code itself should use this language.

We can use Wiki as a glossary to capture and document the ubiquitous language.  
When a ubiquitous language is changed, all team members should be encouraged to go ahead and update the glossary.

The limitation is glossaries work best for 'nouns': names of entities, processes, roles, and so on. How about actual business logic, the behavior?  
We need other tools to capture this, like use cases or Gherkin tests.

Automated tests written in the Gherkin language are not only great tools for capturing the ubiquitous language but also act as an additional tool for bridging the gap between domain experts and software engineers.

Remember, use the tools to support the management of the ubiquitous language, but don't expect the documentation to replace the actual usage.

## The challenge when cultivating ubiquitous language

Quite often, the most important knowledge is unspoken. It's not documented or codified but resides only in the minds of domain experts.  
The only way to access it is to ask questions.

The process involves not merely discovering knowledge that is already there, but rather co-creating the model in tandem with domain experts.  
For example, defining only the "happy path" scenarios but not considering edge cases that challenge the accepted assumptions.

Sometimes there are already a formed language for describing the business domain, and that the stakeholders use it. If that language don't drive by DDD, don't use it.  
We need to change the language first, it's a difficult process.  
We need to make sure the language used where it's easy to control it: in the documentation and source code.