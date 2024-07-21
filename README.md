# System design 999

## Context

- This document is my take on concepts around system design
- This is in no ways a doucment only meant for interview purposes
- Aim is to educate budding engineers and wannabe architects on concepts around system design
- Concepts are generally post 2020. Any references to previous architectures is jsut for comparison purposes



# Abstract concepts

# Polyglot persistence

A misconception is that we should ideally use only one persistence (database) technique for our information system
Different use cases (user stories) may ask for different types of database solutions within the same workflow
For example
1. Finanical transactions may require a Relational database with strong ACID properties (eg Oracle)
2. While user profiles may be ok with a No SQL databse with BASE properties (eg Mongo DB)

Modern engineers and budding Architects should be open to use different databse for different use cases within the same solution

**A** few key features are

1. Fit for purpose usage of database technologies as per us case
2. Mainly **Breaking** of the previous notion that there is only one database solution pre workflow
3. Cloud technologies and managed services make provisioning of these databases very easy




# Distributed systems

Contrary to the previous concept of having all components on a single machine and probably in a monolith
Distributed systems by default will have their components on seperate instances.
Components like UI, Compute and persistence will be on seperate logical instances

**A** few key features are

- In modern achitectures (Post 2020) by default your system will be distributed
- Communication betwweh these components will be mainly using HTTP(s) though  other protocols may apply
- This surely increase the complexity of the system overall
- This reduces the total points of failure and mitigates against a single point of failure (SPF)
- Having components on different logical isntances ensures that there is optimum usage of resources
- Addition or removal of resources can be managed by concepts such as Auto scaling 
  


# UI / UX


# Back end and compute


# Persistence

# Agile 

# DevOps









