---
title: GitOps -- Beyond Patterns and Principles
info: |
  # GitOps

  ## Beyond Patterns and Principles

  Learn more at [HuddledMasses.org/GitOps](https://HuddledMasses.org/GitOps)
keywords: GitOps,DevOps,Continuous Delivery,Infrastructure as Code,Kubernetes
drawings:
    persist: false

mdc: true
theme: ./theme
colorSchema: light
defaults:
    leftFooter: /public/images/CC_By-SA_icon.svg
    rightFooter: /images/PSDOGSummit.png
    layout: default
layout: cover
background: https://images.unsplash.com/photo-1516670428252-df97bba108d1?ixlib=rb-4.0.3&q=85&fm=jpg&crop=entropy&cs=srgb&dl=adrien-converse-kCrrUx7US04-unsplash.jpg&w=1920
---

<span class="text-8xl text-white" style="font-weight:700;" >
    Git<span class="text-blend">Ops</span> <!-- <logos-git-icon /> --> <!--light-icon icon="git-pull-request"/-->
</span>
<div class="text-5xl text-primary-lighter mb-2rem" style="font-weight:500;" >
    Beyond Patterns and Principles
</div>
<div>
    Joel Bennett
</div>
<div>
    April 8-11, <span class="text-blend">2024</span>
</div>

---
layout: image-right-pop
image: https://HuddledMasses.org/assets/images/avatar.png
---

# Joel "Jaykul" Bennett

## Principal DevOps Engineer

``` text
Solving problems with code
15x Microsoft MVP for PowerShell
```

  <div class="absolute bottom-16 left-16">
    <a href="https://fosstodon.org/@Jaykul"><!-- <logos-mastodon-icon /> --> @Jaykul@FOSStodon.org</a><br/>
    <a href="https://github.com/Jaykul"><!-- <logos-github-icon /> --> github.com/Jaykul</a><br/>
    <a href="https://HuddledMasses.org"><!-- <emojione-v1-statue-of-liberty /> --> HuddledMasses.org</a><br/>
  </div>

<!--

For those of you who came to this talk despite not knowing me, thank you, and let me introduce myself.

I'm Joel Bennett. I'm from upstate New York by way of the grasslands of Guanacaste, Costa Rica. I have been "Jaykul" (pronounced J. Cool) online since the 1990s, and I'm currently a Principal DevOps Engineer! I've been a Microsoft PowerShell MVP for 15 years, an open source programmer for over 25 years, a Christian for uhm, let's go with "over 40 years," and bilingual for even longer than that.

-->

---
layout: section
background: https://images.unsplash.com/photo-1516670428252-df97bba108d1?ixlib=rb-4.0.3&q=85&fm=jpg&crop=entropy&cs=srgb&dl=adrien-converse-kCrrUx7US04-unsplash.jpg&w=1920
---

# What is GitOps?

<v-clicks>

## Principles for Operating and Managing Software Systems

### We are not merely building infrastructure from code

### We seek to create _systems_ that continuously update and repair themselves

</v-clicks>

<!--
So, what is GitOps? Can anyone put it in a single sentence?

The [OpenGitOps][1] project -- which is a CNCF Sandbox project from the [GitOps Working Group][2] under the CNCF App Delivery TAG) defines GitOps as

**{NEXT}** "a set of principles for operating and managing software systems."

**{NEXT}** GitOps definitely includes infrastructure as code, but it's not that simple.

**{NEXT}** GitOps is about creating systems that continuously update and repair _themselves_.

## I hope you'll hear me when I say:

### GitOps is about _operating_ and _managing_ software systems, not _building_ them.

You can follow GitOps Principles even when you're hosting _third party_ software, and not writing your own applications, but it's not relevant if you are building software for others to run. In other words, GitOps Principles apply only to a _strict subset_ of DevOps, and GitOps is not a _replacement_ for DevOps.

I have to say that _for SaaS_, I do think of GitOps as the next iteration on _Agile_, following _DevOps_, and _Continuous Delivery_. But those terms are so **overused** in recruiting and marketing that sometimes GitOps practitioners actually object to being associated with them, so I'm going to take _just 2 minutes_ to quickly **{NEXT}** go through the historical context before we talk about the definition of GitOps.

[1]: https://opengitops.dev/
[2]: https://github.com/cncf/tag-app-delivery/tree/main/gitops-wg

-->

---
rightHeader: What is GitOps?
---

# Historical Context

<!--
```mermaid {fontFamily: 'Ubuntu', theme: 'forest'}
flowchart LR
    Agile{{Agile}} --> DevOps
    DevOps --> CI/CD
    Agile --> CI/CD
    CI/CD --> GitOps
    DevOps --> GitOps
    Agile --> GitOps
```
-->

```mermaid {fontFamily: 'Ubuntu', gitGraph: { mainBranchName: 'Agile', showCommitLabel: false } }
gitGraph
    commit tag: "1993"
    commit
    branch DevOps
    checkout DevOps
    checkout Agile
    commit tag: "2001: Agile Manifesto"
    branch Continuous
    checkout DevOps
    commit tag: "2008"
    checkout DevOps
    checkout Continuous
    merge DevOps tag: "2010"
    checkout Agile
    commit
    checkout DevOps
    commit
    checkout Continuous
    branch GitOps
    checkout Continuous
    commit
    checkout GitOps
    commit tag: "2017"
```

<!--
... go through the historical context before we talk about the definition of GitOps.
-->

---
rightHeader: What is GitOps?
clicks: 3
---

# Historical Context

## Agile Software Development (2001)

The [_agile manifesto_](http://agilemanifesto.org/) prioritized collaboration and flexibility...

<v-clicks every="2" >

## DevOps (2008)

DevOps centers on cultural change, unifying Dev and Ops organizations with common goals and shared KPI.

## Continuous Delivery (or Deployment) (2010)

Continuous Delivery became a noun, with a focus on automated pipelines, and small, frequent releases.

## GitOps (2017)

GitOps is a _set of principles_ for operating and managing software systems.

</v-clicks>

<!--

Back in 2001 engineers who were doing what they called "agile software development" got together and signed the _Agile Manifesto_. There were twelve principles behind it, but the first and highest priority was to **satisfy the customer through early and _continuous delivery_ of valuable software.** The core ideas were about _people_ and their attitudes, and how we manage them in projects: let them self-organize, welcome change, reflect on the results, _adapt_ your processes. The agile manifesto focused on people, and how they _collaborate_, and _communicate_.

However, as developers sought _agility_ through _continuous delivery_, they began to feel that traditional operations teams and frameworks (like [ITIL](https://www.ibm.com/topics/it-infrastructure-library)) were the bottleneck. Thus was born the [DevOps movement](https://www.atlassian.com/devops/what-is-devops/history-of-devops), which was all about the _cultural change_ necessary to _unify_ software development (Dev) and operation (Ops) organizations. Adopting DevOps meant finding common goals and principles between those two groups, and establishing shared performance indicators so they wouldn't be working at cross-purposes.

Meanwhile, teams that had not hit bottlenecks started talking more about "Continuous Delivery." They created integrated teams, with developers, testers, and operations engineers together, and focused on increasing the reliability and frequency with which they could build, test, and release software. They found some success by mostly treating _people problems_ as tangential, and focusing on the technical processes required: **automated** build, test, and deployment. Ultimately they began to show success at reducing both _cost_ and _risk_ by enabling small, incremental changes, released frequently. In 2014, Dr. Dobbs magazine actually called Continuous Delivery "The Agile Successor."

Which finally brings us to GitOps.

The GitOps principles are derived from modern software operations and are rooted in _all of these_ pre-existing and widely adopted best practices. This new term "GitOps" was coined by Weaveworks CEO Alexis Richardson, and through the CNCF (Cloud Native Computing Foundation), quickly became a term of art which they have worked to define and promote.

-->

---
rightHeader: What is GitOps?
layout: two-cols
layoutClass: open-gitops
leftClass: col-span-4
rightClass: col-span-8
---

# GitOps

## Principles

### v1.0.0 {.pl-3}

::right::

### Declarative {.before:content-['1']}

<v-click at="1" >

A _system_ managed by GitOps must have its desired state expressed _declaratively_.

</v-click>

### Versioned and Immutable {.before:content-['2']}

<v-click at="1" >

Desired state is _stored_ in a way that enforces immutability, versioning and retains a complete version history.

</v-click>

### Pulled Automatically {.before:content-['3']}

<v-click at="1" >

Software agents automatically pull the desired state declarations from the source.

</v-click>

### Continuously Reconciled {.before:content-['4']}

<v-click at="1" >

Software agents _continuously_ observe actual system state and _attempt to apply_ the desired state.

</v-click>

<!--
So (according to the GitOps Working Group) ...

The desired state of a GitOps managed system must be: ...

**{NEXT}**

Actually, take a minute to read this yourself. This is the entirety of what the Cloud Native Computing Foundation wrote about GitOps.

**{PAUSE}**

As you can see, GitOps does not focus on collaboration, nor on people or organizations. It's simply _practical principles_ for managing software systems: how should we express and store the desired state, and how do we ensure that the system _remains_ in that state.

### Let's talk about these a little...
-->

---
layout: image-right
rightHeader: What is GitOps?
image: /images/turtles-all-the-way-down.jpg
bleed: true
---

# Declarative

The code for the desired state is _independent_ of the steps needed to get there.

<v-click>

# Versioned and immutable

## It's code all the way down

1. The software _source_ is code
2. The infrastructure _source_ is code
3. The configuration _source_ is code
4. _All **source** code is version controlled_

</v-click>

<!--
What does it mean that our desired state is _declarative_?:

In programming, we talk about Imperative code, which describes a set of steps to be taken to achieve a goal, and about Declarative code, which simply describes the goal itself.

The Desired State of systems always needs to be written _declaratively_,
expressing _how things should be_, without regard for _how they currently are_,
because there are too many possible actual states.
We succinctly describe our desired state, and rely on an agents or operator to analyze the current state and determine the specific steps to be taken...

**{NEXT}**

Versioned and immutable:

I tend to think that versioning your state declaration is so obvious at this point that it goes without saying, but some people need every detail spelled out, and others will _deliberately_ flaunt anything that's not in writing. For the record:

1. Developers have been tracking changes to their source code for decades
2. Of course, you know you should declare your infrastructure as (source) code
3. Now, you need to treat your configuration as source code too
4. And obviously, you need to store _all code_ in your version control system

It does _not_ have to be git, but you should probably use whatever your developers use.

The bottom line is that you have versions of your desired state that are immutable, and you can revert, and thus (re)deploy an old version.

-->

---
layout: image-right
rightHeader: What is GitOps?
image: /images/robotic-agents.jpg
bleed: true
---

# Pulled Automatically

GitOps uses **software agents** that **pull** the desired state from source. This scales well, and only requires _read_ access to source.

<v-click>

# Continuously Reconciled

**Reconciliation** is the process of ensuring the _actual state_ matches the _desired state_. It's triggered _whenever_ there is a divergence -- whether a new version of the desired state, or drift in the actual state.

</v-click>
<v-click>

## Continuous Deployment is great

### But please don't conflate

</v-click>

<!--

The key thing that **distinguishes** GitOps are _software agents_ that automatically pull the desired state from source and _continuously_ attempt to apply it through a process known as **{{NEXT}}** reconciliation.

Reconciliation is _**not** just_ triggered by commits to source control. GitOps includes continuous monitoring and repairing. It's not just about _deploying_ when there's a new versions, it's about _monitoring_ the system, and keeping it in the desired state.

GitOps is deliberately defined so it can expand to define more of the _desired state_ of systems -- not just what infrastructure is there, and which version of the software, but also what the _performance_ and _availability_ of the system _should be_.

#### Now. You _will_ see people talking about "push GitOps" ...

_Here's my two cents:_ People who downplay the "pull" are usually also downplaying the "agents" and most often they are coopting the term "GitOps" to describe _whatever they were already doing_ with continuous deployments. That's not useful.

**{{NEXT}}**

There's nothing wrong with Continuous deployment.

**{{NEXT}}**

But let's not confuse the two. Using pipelines to trigger Continuous Deployment on merge to main is not GitOps. It's Continuous Deployment.

**{{NEXT}}**

-->

---
layout: default
rightHeader: What is GitOps?
---

# GitOps wants to be more

<v-clicks>

## Conceptually different

> GitOps follows [control theory](https://en.wikipedia.org/wiki/Control_theory) and operates in a closed-loop, where feedback represents how previous attempts to apply a desired state have affected the actual state. Actions are taken based on policies, it order to _reduce deviation_ over time.

- ### Is the Azure Pipeline Agent a GitOps agent?
- ### Is Windows Desired State Configuration (DSC) a GitOps agent?

</v-clicks>

<!--
GitOps is not _just_ Continuous Deployment. But also, GitOps _wants_ to be more than it currently is...

**{{NEXT}}**
There is a _conceptual_ difference, because as I said before,
the core of GitOps are these automated agents,
and they monitor the current state,
in addition to polling for new versions.

But it's more than that. Although they failed to capture this in the four principles, Open GitOps explains in their glossary that ...
**{{NEXT}}**

GitOps is based on control-theory, a field of engineering and applied mathematics that develops systems like cruise control and thermostats.
This means that Agents should work to drive the system to it's desired state while minimizing delay, overshoot, and steady-state errors, ensuring stability and optimality.

In other words, although a _minimum_ implementation today might just:
- automatically destroy deviating cattle servers or containers and
- deploy new infrastructure or containers based on the template, then
- deploy the correct version of the software, and
- set the configuration to the current values ...

The goal is for agents to make smaller changes to move the system _toward_ the desired state.
They should be _feedback_ driven, and _policy_ driven, and they should _reduce deviation_ over time.

**{{NEXT}}**
Here are a couple of questions for you:
- Is the Octopus Deploy Agent a GitOps agent?
- Is Windows Desired State Configuration (DSC) a GitOps agent?

The Octopus Deploy Agent is like the Azure Pipelines Agent, it's a _push_ agent, and it just waits for jobs to be pushed to it. It does not monitor anything.

On the other hand, DSC (or the LCM, specifically), has versioned and declarative desired state, which it pulls automatically, and continuously reconciles. It's not a perfect match, because it doesn't actually have multiple versions in the source... but it's very close. At work we've built a system where we manage our desired state as json files, and "build" MOF files (and publish to the Pull server) on commit to main. Each of our servers has the LCM configured in pull mode to continuously monitor and pull new versions....


-->

---
layout: section
contentClass: grid grid-cols-2 gap-1em
background: https://images.unsplash.com/photo-1516670428252-df97bba108d1?ixlib=rb-4.0.3&q=85&fm=jpg&crop=entropy&cs=srgb&dl=adrien-converse-kCrrUx7US04-unsplash.jpg&w=1920
---

<div class="col-span-2">

# Best Practices

Or, how do I GitOps?

</div>

<v-clicks>

## Standardization

## Twelve-Factor Apps

## Change Management

</v-clicks>

<!--

We **definitely** don't have time for a full deep dive into best practices, but I want to touch on a few things that I think are most useful to people who are just getting starting with GitOps Principles.

A great example of this is the Twelve-Factor app, a methodology for writing software that works well in software as a service environments. 12 Factor Apps are designed to be _declarative_, _portable_, _scalable_, and _concurrent_. I only consider two of the "factors" in this methodology to actually be a _requirement_ for GitOps. I also believe these practices are important regardless of your hosting environment. If you're doing GitOps on Kubernetes, I almost consider them all to be mandatory. Have your developers and architecture check 12Factor.net and get agreement on standardizing as much of this as possible in your development organization.

Finally, change-management.

As I said before: you don't _have_ to use Git, but you should use the same source control systems and branching strategies across your organization. You need to have clear processes for how changes are proposed, reviewed, and deployed. When all of your changes are done through code, the merge request process in your favorite source control server becomes an easy place to build change-management processes. You can enforce policies and sign-off, require reviews by operators, enforce automated testing, etc. You can use builds and policies to enforce your processes across your organization.

You should have a clear process for how changes are rolled back, and how they are audited. You should have a clear process for how changes are tested, and how they are monitored. You should have a clear process for how changes are communicated, and how they are documented. You should have a clear process for how changes are planned, and how they are prioritized. You should have a clear process for how changes are tracked, and how they are reported. You should have a clear process for how changes are managed, and how they are measured.

-->


---
rightHeader: Best Practices
---

# Standardization

In short, you can't control a train or a ship with the autopilot for a Tesla.

<v-click>

## Especially with micro-services

### Automation requires standardization

### Reduce variations and alternatives

### Avoid custom one-off implementations

</v-click>

<!--

Remember, GitOps assumes you're already doing DevOps. Everything is based on a culture of collaboration, continuous improvement, shared goals, and shared responsibility.

Let's talk about this as control theory. Let's say you're building a thermostat or a cruise control. Imagine I built an auto pilot for a sports car, and then tried to use it to control my fleet of tractor trailers. Or imagine I built a thermostat for the forced-air system in a small home, and tried to apply it at my school with hot water radiators.

The biggest _improvements_ from following GitOps Principles come when you're managing systems that are made up of many small services, where those services are all built with the same technologies and frameworks, are packaged and deployed the same way, have similar configuration, monitoring, and management options, and even have similar density and scale requirements.

None of this is to say you can't have different classes of systems, just that each time you have something that's different it will cause friction and extra work.

For each type of system, all the teams that interact with it need to build custom knowledge and understanding, and in the worst case, unique, one-off agents or agent configurations.

-->

---
rightHeader: Best Practices
---

# Standardization

<div class="columns grid grid-auto-flow-col gap-1em grid-rows-1">

<div>

### Start small

<v-click>

- Source control
- Pull requests
- Continuous **Delivery**
- Automate Deployments
- Health checks

</v-click>
</div><div>

### Best of breed tools

<v-click>

- Code-based
- Declarative
- Idempotent


</v-click>
</div><div>

### Dependency management

<v-click>

- Vulnerability scanning
- Prevent stale
- Included in Health Checks
- Included in Auto Scaling

</v-click>
</div>


</div>

<!--

To minimize the cost of managing systems with software agents, we need to standardize _everything_ that we can. Beyond how we build and deploy the software, to how we manage dependencies, how services are configured, how they scales (and how we know they need to scale). We increase our ability to change quickly by standardizing as much as possible.

### STEP

Don't assume that what works for others will work for you.
- Start small, with a single project.
- If you don't have source control, start with that.
- If you don't use pull requests, start with that.
- If you don't have automatic builds that deliver versioned packages, start with that.
- If you don't have automated deployments, start with that.
- If you don't have health checks, add those.

### STEP

As you identify your next steps, evaluate and choose tools.
Try to always **PICK THE BEST TOOLS**. Remember this is about standardization.
- We don't want to be tempted to switch later
- We don't want teams to have reasons people to use alternatives

Use the same tools across all your projects until that tool is so far behind you can't justify it anymore.
Don't be afraid to re-evaluate and choose better tools, but try to always migrate _everything_ when you migrate.

When you're picking tools, keep those two words in mind: declarative and idempotent.
- Infrastructure and configuration should be declarative whenever possible.
  If you can't find declarative tools, try to build your automation scripts as declarative tools!
- The automation that applies the configuration should be idempotent, so that it can be run repeatedly without causing harm.
  Again, if you can't find idempotent tools, wrap the tools in scripts to make them idempotent.

### STEP

Finally, make sure you have a good dependency management system.
This isn't just about libraries, it's also about service-to-service dependencies.
Make sure you know where your dependencies are, that you have health checks and scaling in place.

-->

##
---
layoutClass: columns grid-rows-5
rightHeader: Best Practices
---
<div class="col-span-3">

# Twelve-Factor Apps

</div>

<!-- <v-clicks> -->

<div>

### I. Codebase

One codebase tracked in revision control, many deploys

</div><div>

### II. Dependencies

Explicitly declare and isolate dependencies

</div><div>

### III. Config

Store config in the environment

</div><div>

### IV. Backing services

Treat backing services as attached resources

</div><div>

### V. Build, release, run

Strictly separate build and run stages

</div><div>

### VI. Processes

Execute the app as one or more stateless processes

</div><div>

### VII. Port binding

Export services via port binding

</div><div>

### VIII. Concurrency

Scale out via the process model

</div><div>

### IX. Disposability

Maximize robustness with fast startup and graceful shutdown

</div><div>

### X. Dev/prod parity

Keep development, staging, and production as similar as possible

</div><div>

### XI. Logs

Treat logs as event streams

</div><div>

### XII. Admin processes

Run admin/management tasks as one-off processes

</div>

<!-- </v-clicks> -->

---
class: grid-cols-12
rightHeader: Best Practices
---

# Change Management

<div class="leftColumn col-span-6">

<v-clicks>

## Separate Repositories

Don't mix infrastructure, application and configuration

- Independent life-cycles
- Separate approval processes
- Different team ownership

</v-clicks>

</div><div class="rightColumn col-span-6">

<v-clicks>

## Environment Considerations

- Create versioned configuration artifacts
- Import artifacts, or inherit a shared base
- Use overlays for different environments
- Think about versioning and promotion of the base

</v-clicks>

</div>

<!--
The goal in GitOps is continuous deployment, but we still need to version ... everything.

I'm not a big fan of mono-repos in general, but for GitOps we have a few special reasons for separating our infrastructure, apps, and configuration repositories.

- The primary reason is to keep the versioning separate, and avoid triggering CI/CD pipelines for config or infrastructure changes. You don’t want a configuration change (like scaling a deployment from three to four nodes) to trigger a CI/CD rebuild and test of your application (not to mention creating containers, etc).
- You also don't want to hold up CI/CD builds with the change management approvals you might need for infrastructure changes
- You may have different teams responsible for infrastructure and application code or configuration, and different code-review or approval processes.

You could, hypothetically, put a bunch of path filters on your triggers and validation rules, etc., but that adds unnecessary complications and potential for error.

**HOWEVER**. You might be tempted to have separate branches per environment, or even separate repositories per environment, most of us with experience _doing_ this are advising against that. Why?

- Promoting from one environment to another is usually not as simple as a merge
- Much cannot be promoted from one environment to another: configuration, secrets, scale, etc.

Regardless of what tools you're actually using and what your hosting environment is, consider the layout used for Kustomize and Helm, where you have a "base" directory and then an overlay directory for each environment...

Make sure you consider how to protect your _production_ environment from changes that you are testing in _staging_ or _development_ environments.
-->

---

# Let's Talk about Declaring Infrastructure

The current state-of-the-art in infrastructure as code has a lot of "gotchas" and you're going to need to learn what they are in each case.

We have so many options, but some of them only work on one tech stack, or work better on one tech stack than another.

- Bicep or Arm
- Terraform
- Pulumi
- CloudFormation (!?)
- Ansible
- DSC
- Kubernetes

Are all of these declarative? Are they idempotent?

One thing that you have to really understand when you start doing GitOps is that sometimes, even tools which are declarative may support changing _some_ things, but not others. For example, if you change the _name_ of something, most tools don't rename it -- they create a new one (and they might not even delete the old one).

<!-- I'm not even kidding when I say ChatGPT filled in this list, in this order -->



One point to mention here: it doesn't really matter _how_ this is achieved. WHether it's event-based monitoring of actual state changes, or polling the state over and over again. Whether the agent pulls directly from git, or there's a pipeline that moves code from source control to effective application. For those of you familiar with the old Windows PowerShell DSC, a trivial GitOps agent might just be the old LCM in pull and repair mode, configured with short intervals...

As I said about Infrastructure as Code, there are many tools here, and we've clearly not reached peak GitOps -- picking agents right now comes down to making the right trade-offs for your systems -- you will probably need to combine several of these tools to get where you want to be.



**{NEXT}**

There are many systems and frameworks for Infrastructure as Code, and picking one comes down to making the right trade-offs for your systems. It could be Terraform or Bicep describing cloud resources, Ansible or DSC describing on-premises servers, Yaml describing Kubernetes resources, but most likely, it's a combination of several systems.

I have to add: don't get carried away about _declarative_ code -- all of these frameworks have imperative code under the covers in the "resources" and the tools themselves, we are only concerned with keeping our expression of desired state separate from the steps required to get there, so that we can ...
[^1]: [Harness](https://www.harness.io/blog/gitops-the-push-and-pull-approach), [DevOpsSchool](https://www.devopsschool.com/blog/gitops-approach-pull-vs-push/)