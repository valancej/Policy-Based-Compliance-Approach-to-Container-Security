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

### Complete approach to image scanning

#### Vulnerability scanning

Adding image scanning against a list of CVEs to a build pipeline allows developers to be proactive about security as they will get a near immediate feedback loop on potentially vulnerable images. Anchore image scanning will identify any known vulnerabilities in the container images, enforcing a shift-left paragidm in the development lifecycle. Once vulnerabilities have been identified, reports can be generated listing infomation about the CVEs and vulnerable packages within the images. In addition, Anchore can be configured to send webhooks to specified endpoints if new CVEs are published that impact an image that has been previously scanned. At Anchore, we've seen integrations with Slack or JIRA to alert teams or file tickets automatically when vulnerabilities are discovered.  

#### Adding governance

Once an image has been analyzed and it's content has been discovered, categorized, and processed, the resulting data can be evaluated against a user-defined set of rules to give a final pass or fail recommendation for the image. It is typically at this stage that security and devops teams want to add a layer of control to the images being scanned in order to make decisions on which images should be promoted into production environments. 

Anchore policy bundles (structured as JSON documents) are the unit of policy definition and evaluation. A user may create multiple policy bundles, however for evaluation, only one can be marked as 'active'. A policy is expressed as a policy bundle, which is made up from a set of rules to perform an evaluation of an image. These rules can define check against an image for things such as:

- Security vulnerabilities
- Package whitelists and blacklists
- Configuration file contents
- Presence of credentials in an image
- Image manifest changes
- Exposed ports

Anchore policies return a pass or fail decision result.

To better gauge the flexbility of Anchore's policy engine, here is a full list of policy gates and triggers: https://anchore.freshdesk.com/support/solutions/articles/36000073896-anchore-policy-checks

#### Putting it together with compliance

Given the variance of compliance needs across different enterprises, having a flexible and robust policy engine becomes a necessity for organizations needing to ahere to one or many sets of standards. In addition, managing and securing container images in CI/CD environments can be challenging without the proper workflow. However, with Anchore, development and security teams can hardern their container security posture by adding an image scanning step to their CI, reporting back on CVEs, and fine tuning policies meet compliance requirements. With compliance checks in place, only container images that meet the standards laid out a particular agency or industry will be allowed to make their way into production ready environments.

## Conclusion

Taking a policy-based compliance approach is a multi-team effort. Developers, testers, and security engineers should be in constant collaboration on policy creation, CI workflow, and notification/alerting. With all of these aspects in-check, compliance can simply become part of application testing and overall quality and product development. Most importantly, it allows for organizations to create and ship products with a much higher level of confidence knowing that the appropriate methods and tooling are in place to meet industry specific compliance requirements. 