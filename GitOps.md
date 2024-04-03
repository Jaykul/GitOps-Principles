# GitOps: Beyond Patterns and Principles

I like to think of GitOps as another iteration of _Agile_, following _DevOps_, and _Continuous Delivery_. Of course, those terms have been so **overused** in recruiting and marketing that I usually get strange looks, so I'm going to take _just 2 minutes_ to quickly go through the history before we talk about the definition of GitOps.

## Agile Software Development (2001)

In the [_agile manifesto_](http://agilemanifesto.org/) the principles of agile software development were laid out as having the goal of _satisfying customers through early and continuous delivery_ of software. The core ideas were to welcome change, reflect on the results and adapt your processes frequently, and to focus on _people_, _collaboration_, and _communication_.

## DevOps (2008)

As developers sought _agility_ and _continuous delivery_, they began to feel that traditional operations teams and frameworks (like [ITIL](https://www.ibm.com/topics/it-infrastructure-library)) were the bottleneck. The [DevOps movement](https://www.atlassian.com/devops/what-is-devops/history-of-devops) centered around the cultural change necessary to _unify_ software development (Dev) and operation (Ops) organizations, to establish common goals and shared principles and performance indicators.

## Continuous Delivery (or Deployment) (2010)

note: In a sense, Continuous delivery has been the theme all along, but it was still seen as a new idea when people started using it as a noun around 2010. Wikipedia describes it as "a software engineering approach where teams work in short cycles, ensuring the software can be reliably released _at any time_." Dr. Dobbs magazine declared it "The Agile Successor" as late as 2014.

As forseen in the Agile principles, Continuous Delivery teams are often integrated teams, with developers, testers, and operations engineers focusing on increasing the reliability and frequency with which they can build, test, and release software. This always includes automated build, test, and software deployment processes, and has the goal of reducing the cost, time, and _risk_ of delivering changes by having smaller, incremental updates to applications in production.


Continuous deployment is the natural outcome of continuous delivery done well -- IBM


## GitOps (2017)

The term GitOps was coined by Weaveworks CEO Alexis Richardson, and through the CNCF (Cloud Native Computing Foundation) they worked with many companies to established _four_ GitOps principles

> ## GitOps Principles
>
> GitOps is a set of principles for operating and managing software systems. These principles are derived from modern software operations, but are also rooted in pre-existing and widely adopted best practices.
>
> The desired state of a GitOps managed system must be:
>
> 1. Declarative
>
>     A system managed by GitOps must have its desired state expressed declaratively.
>
> 2. Versioned and Immutable
>
>     Desired state is stored in a way that enforces immutability, versioning and retains a complete version history.
>
> 3. Pulled Automatically
>
>     Software agents automatically pull the desired state declarations from the source.
>
> 4. Continuously Reconciled
>
>     Software agents continuously observe actual system state and attempt to apply the desired state.

So basically, GitOps brings infrastructure as code is truly continuous delivery, applied to infrastructure as code and desired state configuration.

## GitOps in Practice

Let's dig in to these GitOps principles two at a time.

### Versioned (and immutable) Declarative Desired State

I used to think the "versioned and immutable" part of this was redundant, but I'm learning to be explicit, and thus, to appreciate this. Even before we called it "GitOps," I thought it was obvious that to do infrastructure as code, you had to store the code in a version control system. It does _not_ have to be git -- that's just the most likely tool you have available.

Some people use "infrastructure as code" to describe systems that are build through imperative scripting and automation, and that's one of the reasons I've started talking about "GitOps" for everything. GitOps makes it explicit that for infrastructure as code, we need declarative configuration -- meaning the desired state is expressed in a way that is independent of the steps needed to get there.

There are many such systems nowadays, and this covers all of them. It could be Terraform or Bicep describing cloud resources, Ansible or DSC describing on-premises servers, Yaml describing Kubernetes resources, a combination of all of the above, or many others.  Obviously all of these have imperative code under the covers in the resource definitions and the tools themselves, it's only the desired state that is expressed declaratively.

### Continuous and Automatic Updates and _Reconciliation_ of State

The thing that **makes** GitOps are the _software agents_ that automatically pull the desired state from the source and continuously attempt to apply it. In my mind, this is the difference between "infrastructure as code" and GitOps. We are no longer just deploying infrastructure from code. We are continuously monitoring _and repairing_. The GitOps agent automatically pulls updates to the desired state, and we upgrade packages and apply configuration changes using the same process that enforces configuration and monitoring.

One point to mention here: it doesn't really matter _how_ this is achieved. WHether it's event-based monitoring of system changes, or polling the state over and over again. Whether the agent pulls directly from git, or there's a pipeline that moves code from source control to effectiveness. For those of you familiar with PowerShell DSC, a GitOps agent is a lot like the DSC LCM in pull mode: the agent continuously pulls new versions of the configuration, as well as checking for and reverting external changes...

---

# GitOps: Principles for Operating and Managing Software Systems

The principles of GitOps bring infrastructure as code and software engineering best practices to the operation and management of infrastructure and software. We'll see an example, and learn core principles you can begin applying to your infrastructure and software systems.

GitOps does not merely build fully configured systems from code -- it creates systems that continuously update and maintain their state and configuration.

The four principles of GitOps: Declarative desired state, Versioned desired state. Automatic application of changes. Continuous monitoring of state.

The current state of Infrastructure as Code allows us to build and rebuild environments from nothing to fully functional with a single command-line or the click of a button. GitOps takes this to the next level, applying changes automatically as they're checked in, and allowing rollback to be as easy as reverting a commit.

Not only can we go from nothing to fully deployed in a single step, a single pull-request is enough to reconfigure our infrastructure, deploy software, or updates our configuration.

# EXTRA JUNK

putting everything from the network to the software versions and every setting, into a single source of truth. Not only is every change is versioned and tracked (and easy to roll back), the GitOps pipeline means that each change is applied automatically,  and autmatically deployed, versioned and tracked.

controlled, scanned, checked a every part of our cluster can be deployed with a single command-line or the click of a button.

at the click of a buttoin a single deployment. With our software running in containers, GitOps lets us take it to the next level, where every version, every setting, every part of out cluster versiondeployKubernetes cluster --with all our software already installed and configured-- in a single step. GitOps lets us take it to the next level, where every pull-request we merge reconfigures our infrastructure and updates our configuration.

Not only that, but

GitOps is not just about agility and collaboration, it's the evolution of infrastructure as cattle.

There are many ways to deploy infrastructure to the cloud. Whether it's Pulumi, CloudFormation, Terraform or Bicep, you can get a Kubernetes cluster up in just a few minutes -- and GitOps can get your software deployed as fast as you can download the containers.

In this talk we'll discuss options a little, and go through a fully-automated example of how a simple pipeline can not only deploy any size Kubernetes cluster, but also deploy all the software and configuration to it, using GitOps.

If you're unfamiliar with GitOps and how it's revolutionizing software deployment, come along and see how it works in actual practice. We'll cover the basics of GitOps, why it's the best way deploy software to Kubernetes clusters, and how it can be used to deploy the clusters themselves.

We'll cover a few ways to deploy Kubernetes to the cloud, whether it's Pulumi, from Bicep
At work we routinely delete our clusters and recreate them from scratch to prove we can. It costs us 30 minutes or so

After I show you how to go from a git repository to a cluster full of software in one step, I'll show you how it all works, what it takes to keep it up to date, and how

Building world-class kubernetes clusters from infrastructure as code and GitOps can rebuild a Kubernetes cluster in 30 minutes.

# What tools are we using for GitOps?

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

One thing that you have to really understand when you start doing GitOps is that sometimes, even tools which are declarative may support changing _some_ things, but not others. For example, if you change the _name_ of something, most tools don't rename it -- they create a new one (And they might not even delete the old one).

In my example code, I have infrastructure as code for Azure in
