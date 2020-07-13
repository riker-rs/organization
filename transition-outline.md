# Riker Reorganization

## Introduction
Riker is a Rust actor system that has been developed by a single maintainer and small group of contributors since 2018.

As Rust and the actor model has grown in interest so has Riker. For Riker to continue to grow and seize the opportunities ahead, a transition to a more effective development process is required.

Lee Smith, the founder and maintainer of Riker has called for this transition in a GitHub issue: [Issue #102](https://github.com/riker-rs/riker/issues/102).

The purpose of this document is to gain alignment and consensus  on forming the first steps of transition. Several Riker users (developers that use or have contributed to Riker) have provided input on how they would like to move forward. However, anyone interest in contributing through PRs or comments to this document may do so.

The style of this document is semi-official, optimizing for ideas and shared thoughts, rather than concrete guides and rules. Concrete materials must however emerge from this process.

Ultimately, this document aims to set direction and initial targets/goals of the reorganization, much like an RFC.

## Background
Riker started out as another project, a closed-source Rust library, to provide easy to use concurrency abstracted using the actor model. Rust async primitives were not part of the standard library and other libraries were too low level.

Riker, the open source project that spun off has provided the Rust community with a familiar actor model, taking inspiration from actor systems on other languages, in particular Scala's Akka, and Erlang.

There has always been a firm belief that Rust is unique and therefore, while drawing inspiration from Akka and Erlang provides guidance, simply copying core concepts from those systems isn't the best approach. I.e. Rust needs its own actor system.

Another firm belief is that Riker should not attempt to provide concurrency primitives. The concurrency primitive in Erlang is the actor, and in the early days of Akka that was the default goto concurrency type too. Rust however was created with concurrency in mind from its first release, with a roadmap to futures and async. For concurrent IO operations in Rust, please use the excellent async capabilities developed by the Rust core team.

## Opportunity & Vision
The Rust language has provided solutions to two major problems:

1. Safety to low level performant code through its unique use of ownership
2. Modern language design and semantics to low level performant code in the form of traits and other concepts

This has made Rust unique in that it provides developers the power and performance of low level languages such as C and C++, while also providing developers the benefits of modern language design. It is the belief of the Riker developers that these solutions are increasingly important in today's environment.

The future's problems lie not in large cloud systems hosted on abundant, powerful server infrastructure, but instead in resource limited environments, that are often mission critical.

Essentially, Rust provides a robust solution to developing systems at scale where speed, efficiency and safety are paramount. Typical examples are: xyz.

So why Riker?

While the Rust language and libraries are first-class solutions, there are no major frameworks that assist developers, especially for production environments.

Today, Rust is mostly chosen for the actual language features. Many successful languages however are chosen because of a tried and tested set of tools or components, often unified by some model. Scala's Akka for example provides such a framework, that uses the common actor model and concepts such as supervision. For many Scala developers they were introduced to the language via Akka. And for Erlang developers a major attraction is it's use of actors.

To summarize:

- Async is difficult to reason about
- State is difficult to manage in Async (especially in Rust's strict ownership system) 
- Large projects are difficult to maintain using low level async
- The Actor Model is familiar, proven and widely used
- Actor Model provides a language agnostic abstraction, without boxing developers off from Rust's power
- Actor model compliments Rust's fundemental concept of ownership (Actors own their state) and safety (Actors provide resilience through 'let it fail' supervision)
- Common framework for solving common problems
- Entry point to Rust. Onboarding for non-Rust developers

Riker's ultimate goal is to supply individuals and teams with a product that is future proof.

## Core Team
Initially there will be four members of the Core Team.

The first tasks of the CT will be:
- Establish communication guides and channels
- Solve immediate pace of code review and merge of PRs
- Provide outline of roadmap and direction
- Local development environment setup guide
- Pull Request requirements and process
- Code style requirements
- RFC process, including templates and guide

Long term the CT will work to establish workgroups that will ideally be empowered to work autonomously.

## Governance & Contribution
Riker will initially use the Liberal Community governance style, employing the RFC (Request for Comments) document process for changes to code.

While Riker remains primarily a Rust library, major changes to code will require an RFC document to be submitted. Everyone is able to participate in the discussion and it will be the decision of the Core Team to approve, or reject, resulting proposals.

It is expected that the governing structure will evolve in to a DAO (Distributed Autonomous Organization) as the framework grows. Such a move will only take place if and when certain conditions (yet to be defined) are met.

The DAO will reserve the right to issue its own cryptocurrency token. The token can be used to participate in governance decision making and sharing of funds generated by any economic activity that the DAO undertakes.

## Website
- State the problem
- Why use Riker, both from Rust perspective and non-current Rust developers
- Areas of key focus and opportunity, e.g. SBCs, resource limited environments, blockchain, web browsers (WebAssembly)
- Roadmap. E.g. on https://beam.mw/#exchanges
- Polls on features and direction
- Should communicate to individuals and teams. Individuals will value the independence of the organization and teams will have reassurance of long term commitment

## Workgroups
- Core (system, kernel, actor modules, performance)
- CI and Publishing (should this be part of Core?)
- Documentation
- Ecosystem (Actor patterns, Rust, http, interop with common libraries, end-to-end guidance). Should this be part of Documentation?
- Community (Twitter, Rust groups, etc)

## Policy
Respect is the ultimate governing ideal for persons participating in Riker. Persons who are giving their time to add value to the project will be respected.

- Respect that people are unique yet equal
- Respect that people have differing views and opinions

Successful human aggregates are historically those that respect and promote cooperation between persons holding contrary opinions. Those that enforce a single, monolithic view are short lived.

Unless otherwise stated, group communication will be limited to Riker-specific topics.

The core team will be responsible for reviewing policy changes.

## References
- [Open source best practices](https://opensource.guide/best-practices/)
- [Open source governance](https://opensource.guide/leadership-and-governance/)
- [Healthy open source](https://medium.com/the-node-js-collection/healthy-open-source-967fa8be7951)
- [Six lessons from RFC process](https://opensource.com/article/17/9/6-lessons-rfcs)



 

