---
title: "Cloud Migration: Patterns"
date: 2021-07-28T10:54:33+02:00
draft: false
author: "[Michael Frank]https://github.com/Michael-Frank/)"
tags: ["Cloud", "Migration", "Architecture", "Business and IT"]
image: "cloud-migration/road-to-cloud.jpg"
summary: "There is only one way to to do cloud migration properly: Linking business and technology."
---

In a time of rapid technological change, decision-makers in companies are often confronted with the challenge of future-proofing their existing applications and systems. This article is aimed in particular at technical and business decision-makers whose applications and systems are still predominantly running "on-prem", i.e. in classic operation, and are not based on mainframes. Are you driven by the need to migrate your applications to stay competitive? If you're looking for a guiding perspective in this migration dilemma, you've come to the right place.


In this article, we delve into the "bottom up" perspective and show why it not only makes sense, but is actually necessary, to make applications and systems "cloud-ready" - regardless of whether your organization has already made the leap to the cloud or whether that move is still in the planning stages.

In particular, we point to the [migration strategy we employed in the LEAP project](https://blog.qaware.de/posts/cloud-migration-this-is-the-way/) and why refactoring, even to a limited extent, can be crucial.



## Bottom up vs Top Down
Ideally, business has a good cloud strategy and strong commitment pushing the cloud move "top down", and at the same time from the "bottom up" all technical teams have an equally strong desire to leverage the offered technical and organization benefits if cloud technologies.

However, there are many "bottom up" cases, where teams are pushing to the cloud before strong business commitment is there.
And there are cases where companies have a clear "top down" strategy for their cloud platform in place, but lack adoption of their cloud platform and struggle to find a good strategy to move over their legacy landscape.

We will look at both cases and show what has worked for us and our customers.

## Team driven "bottom up" migration
Doing "bottom up" migrations the teams usually have a lot of questions and "What-Ifs" in their mind. Let me try to tackle some of them in a Q&A Style.

Imagine your company announced "Hey, we will (probably) moving to the cloud (soon / once its ready)" and your team is sitting on some not-so-cloud-friendly applications that need some love and polishing to keep them maintainable anyway. So now you need to decide on the best course of action. Sound familiar? Good, then this section might be for you.

Why not take the chance to refactor the applications right now, and on the way also make them cloud friendly.

**Safe harbor statement:**
We are strong believers in the **cloud-friendly** (or **Lift and extend**) cloud migration strategy, where an existing application can be economically adapted to run on a cloud platform. However, it is not a one-size-fits-all solution, and there are [other migration strategies](https://blog.qaware.de/posts/cloud-migration-this-is-the-way/) that may be better suited for your specific application.

You may ask: But my companies cloud platform is not available yet or still in flux. Cant I just wait?
You could, but you probably already know your companies cloud platform is very likely to be at least some kind of "container runtime" or better "some sort of kubernetes" being it on-prem, public cloud, or managed or in-house.

**Targeting Kubernetes is a sane choice!**  
but leveraging cloud design principles are beneficial for any runtime! So it makes sense to implement them as early as possible and is usually faster than expected.

The cloud design (and migration) principles are:
* Implementing the infamous  [12 factor](https://12factor.net/) principles
* Security
* Elimination of toxic dependencies
* Proper isolation of state
* Observability and diagnosability
* Resilience

Migration teams are encouraged to exceed this baseline if possible within the frame of the migration. New applications are build cloud-natively.
With *cloud-friendly*, the focus is on the outcome: Secure applications that can be maintained and operated easily.


By following them early you can avoid doing work twice/wrong! But that's not all:
- containerizing your application is beneficial on its own, as it allows for easier deployment, portability, and scalability even on legacy systems.
- having a gentle start into the cloud world instead of being forced into it makes it more joyful (e.g. because your current servers/platform or even the whole data center are being forcefully discontinued by management)
- By being familiar with cloud technology early on, you can ask "the right questions" and you can maybe even influence and participate in shaping your future cloud platform.
  (This one is pretty huge!)
- As early adopters you are the cloud experts in your company, which is good for you and your teams standing
- And of course production stability and maintainability of your application will rise, as cloud design principles and operation patterns have proven them self over and over to increase these.


Sounds nice but...
- where do i host my containers if the company platform is not ready? Maybe you can  use a public cloud managed kubernetes. And don't be afraid to host your own kubernetes. There are awesome distributions for each usecase. e.g. coming from a single host world, or maybe some small shop floor on-prem system? Why not microk8s? To list them all and their usecases would go far beyond the scope of this article.
- i don't need Kubernetes. Plain Docker is dying, swarm is dead. We had to go against the flow at some point and its painful, as you are forced to solve many issues where K8s and its ecosystem already have ready to use solutions. Kubernetes is today's standard for running containerized applications.



## Team driven "bottom up" migration
Top down, the business goals and constraints of the migration must be clearly defined.
Typical goals are:

* Cost savings
* Migrating within a budget
* Better user experience by improving performance
* Improving developer and operations experience
* Decommissioning data centers

![How a migration program is set up](/images/cloud-migration/migration-program-setup.jpg)

Our approach: Transparency, Good Planing, Stakeholder management and Migration Industrialization as a Service:

1. **We take care to help shape, understand and communicate the goals and constraints of the migration and align the organization**.
   The journey will only be successful if the destination is clear.
2. **We create a single source of truth that reliably provides in-depth transparency about the state of the application landscape to migrate.**
   We tap into existing sources of information and use a tool-based approach to analyze and classify applications.
   Born from experience, we act with a healthy distrust of pre-existing documentation and high-level declarations. The truth is in the code.
   - In the past we did this with our own custom tooling!
   - Today there is CNCF's [Konveyor, most noteably "Konveyor Tackle"](https://www.konveyor.io/) to help you!
3. **We link the business view and the technical foundations.** Results:
   * Reliable bottom-up assessment and planning of the migrations
   * Detecting and resolving problems before they hurt
   * Ensuring compliance and security
   * Confidence that the goals can be achieved
4. **We ensure and efficient and effective migration by:**
   * Helping you design and set up the migration program right from the start
   * Industrializing architecture, common parts and work:
     We solve challenges once, automated as far as possible and in high quality.
   * Establishing an *inner source* approach, facilitating communication and providing transparency across teams.
   * Including enabling from the beginning. The existing teams know their applications best. We ensure that they will be
     able to maintain their newly cloudified applications easily. Many teams will be able to carry out the migrations themselves.
   * Taking responsibility for the outcome and working closely with you and your partners.
5. **We support the after-migration period, ensuring that cost, stability and performance goals are met.**


Trivia: k8s vs kubernetes - never dared to ask? the developers thought the word "kubernetes" (ancient greek for "helmsman") was too long in everyday life. Just leave out the middle 8 letters and replace them with an "8" and you get K8s.


## See also
* [Cloud Migration: This is the Way](https://blog.qaware.de/posts/cloud-migration-this-is-the-way/)
* [The good, the bad & the ugly of migrating hundreds of legacy applications to a cloud native platform](https://www.slideshare.net/QAware/the-good-the-bad-the-ugly-of-migrating-hundreds-of-legacy-applications-to-a-cloud-native-platform), Robert Bichler, Josef Adersberger, Handelsblatt annual conference on strategic IT management, 2019
* [IDG Cloud Migration Studie 2021](https://info.qaware.de/de-de/cloud-migration-studie-2021) (German)
