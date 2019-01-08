# Policy Based Compliance Approach to Container Security

## Introduction

At Anchore, we take a preventative, *policy-based compliance* approach, specific to organizational needs. Our philosophy of scanning and evaluating Docker images against user-defined policies as early as possible in the development lifecycle, greatly reduces vulnerable, non-compliant images from making their way into trusted container registries and production environments. 

But what do we mean by 'policy based compliance'? And what are some of the best practices organizations can adopt to help achieve their own compliance needs? In this post we will first define compliance, and then cover a few steps development teams can take to help to bolster their container security.

## An example of compliance

Before we define *'policy-based compliance'*, it helps to gain a solid understanding of what compliance means in the world of software development. Generally speaking, compliance is a set of standards for recommended security controls laid out by a particular agency or industry that an application must adhere to. An example of such agency is the [National Institute of Standards and Technology or NIST](https://www.nist.gov/). NIST is a non-regulatory government agency that develops technology, metrics, and standards to drive innovation and economic competitiveness at U.S. based organizations in the science and technology industry. Companies that are providing products and services to the federal government oftentimes are required to meet the security mandates set by NIST. An example of one of these documents is NIST SP 800-190, which addresses the security concerns that are associated with application container technologies. 

## What do we mean by *'policy-based'*?

Now that we have a definition and example, we can begin to discuss the aspect role play in achieving compliance. In short, *policy based compliance* means adhering to a set compliance requirements via customizable rules defined by a user.  In some cases, security software tools will contain a policy engine that allows for development teams to create rules that correspond to a particular security concern addressed in a compliance publication.


## How can organizations achieve compliance in containerizaed environments?

Here at Anchore, our focus is helping organizations secure their container environments by scanning and analyzing container images. Oftentimes, our customers come to us to help them achieve certain compliance requirements they have, and we can often point them to our policy engine. Anchore polcies are user-defined checks that are evaluated against an analyzed image.  

## Conclusion