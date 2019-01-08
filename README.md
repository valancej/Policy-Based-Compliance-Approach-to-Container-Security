# Policy Based Compliance Approach to Container Security

## Introduction

At Anchore, we take a preventative, *policy-based compliance* approach, specific to organizational needs. Our philosophy of scanning and evaluating Docker images against user-defined policies as early as possible in the development lifecycle, greatly reduces vulnerable, non-compliant images from making their way into trusted container registries and production environments. 

But what do we mean by 'policy based compliance'? And what are some of the best practices organizations can adopt to help achieve their own compliance needs? In this post we will first define compliance, and then cover a few steps development teams can take to help to bolster their container security.

## An example of compliance

Before we define *'policy-based compliance'*, it helps to gain a solid understanding of what compliance means in the world of software development. Generally speaking, compliance is a set of standards for recommended security controls laid out by a particular agency or industry that an application must adhere to. An example of such agency is the [National Institute of Standards and Technology or NIST](https://www.nist.gov/). NIST is a non-regulatory government agency that develops technology, metrics, and standards to drive innovation and economic competitiveness at U.S. based organizations in the science and technology industry. Companies that are providing products and services to the federal government oftentimes are required to meet the security mandates set by NIST. An example of one of these documents is NIST SP 800-190, which addresses the security concerns that are associated with application container technologies. 

## What do we mean by *'policy-based'*?

Now that we have a definition and example, we can begin to discuss the aspect role play in achieving compliance. In short, *policy based compliance* means adhering to a set compliance requirements via customizable rules defined by a user.  In some cases, security software tools will contain a policy engine that allows for development teams to create rules that correspond to a particular security concern addressed in a compliance publication.


## How can organizations achieve compliance in containerizaed environments?

Here at Anchore, our focus is helping organizations secure their container environments by scanning and analyzing container images. Oftentimes, our customers come to us to help them achieve certain compliance requirements they have, and we can often point them to our policy engine. Anchore policies are user-defined checks that are evaluated against an analyzed image. A best practice for implementing these checks is through a step in CI/CD. By adding an Anchore image scanning step in a CI tool like Jenkins or Gitlab, development teams can create an added layer of governance to their build pipeline. 

### Proactive approach

#### Image scanning

Adding image scanning against a list of CVEs to a build pipeline allows developers to be proactive about security as they will get a near immediate feedback loop on potentially vulnerable images. Anchore image scanning will identify any known vulnerabilities in the container images, enforcing a shift-left paragidm in the development lifecycle. Once vulnerabilities have been identified, reports can be generated listing infomation about the CVEs and vulnerable packages within the images. In addition, Anchore can be configured to send webhooks to specified endpoints if new CVEs are published that impact an image that has been previously scanned. At Anchore, we've seen integrations with Slack or JIRA to alert teams or file tickets automatically when vulnerabilities are discovered.  

#### Adding governance

Following each scanned image, we now have analyzed image data to work with. Based on the previous paragraph, we've also been able to extract any CVEs wihin images as well. It is typically at this stage that security and devops teams want to add a layer of control to the images being scanned in order to make decisions on which images should be promoted into production environments.


## Conclusion