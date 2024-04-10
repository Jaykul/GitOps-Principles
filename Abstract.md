# GitOps: Beyond Patterns and Principles

In this walk-through we'll go beyond the core principles to practical tools, code and deployment patterns. We'll start with 12 Factor apps, breeze through declarative infrastructure frameworks, and end with continuous delivery and GitOps tools. By the end we'll have a full Kubernetes cluster with working software deployments.

At it's core, GitOps is just continuous delivery applied to the whole system, and actually done continuously. Deploy your infrastructure as code, and automatically deploy your software packages and configuration to that infrastructure.

High quality recipes are out there for deploying almost anything. Don't start from scratch, build on the shoulders of giants.

This is a code, configuration and demo-heavy talk, centered around the deployment of a Kubernetes cluster in the cloud and the automatic delivery of software and configuration to that cluster. We'll talk principles, and illustrate with working code the participants can clone from GitHub.

1. [Agile Manifesto](http://agilemanifesto.org/)
2. [Principles of Agile Software](http://agilemanifesto.org/principles.html)
3. [12 Factor Apps](https://12factor.net/)
4. [GitOps Principles](https://opengitops.dev/#principles)
5. [Control Theory](https://en.wikipedia.org/wiki/Control_theory)
6. [Crash-Only Software](https://www.usenix.org/legacy/events/hotos03/tech/candea.html)
7. [Crash-only Software: More than meets the eye](https://lwn.net/Articles/191059/)
8. [History of DevOps (Atlassian)](https://www.atlassian.com/devops/what-is-devops/history-of-devops)
9. [DevOps (Wikipedia)](https://en.wikipedia.org/wiki/DevOps)
10. [DORA](https://dora.dev/)
11. [Continuous Delivery (Wikipedia)](https://en.wikipedia.org/wiki/Continuous_delivery)
12. [Continuous Delivery: The Agile Successor (Dr. Dobbs)](https://www.drdobbs.com/architecture-and-design/continuous-delivery-the-agile-successor/240169037)
13. [Continuous Deployment (IBM)](https://www.ibm.com/topics/continuous-deployment)
14. [Git best practices: Workflows for GitOps Deployments](https://developers.redhat.com/articles/2022/07/20/git-workflows-best-practices-gitops-deployments#separate_your_repositories)
15. [The GitOps Guide](https://configu.com/blog/the-gitops-guide-principles-examples-tools-best-practices/#GitOps_Best_Practices)
16. [CNCF Landscape](https://landscape.cncf.io/)

Some of us hold that the original practice of "Agile" included the infrastructure engineering practices, but as "Scrum" became the dominant methodology (it omitted the engineering practices), the movement to automate operations and infrastructure splintered from "Agile" and became "DevOps".

Photo by <a href="https://unsplash.com/@yancymin?utm_content=creditCopyText&utm_medium=referral&utm_source=unsplash">Yancy Min</a> on <a href="https://unsplash.com/photos/a-close-up-of-a-text-description-on-a-computer-screen-842ofHC6MaI?utm_content=creditCopyText&utm_medium=referral&utm_source=unsplash">Unsplash</a>

Photo by <a href="https://unsplash.com/@adrienconverse?utm_content=creditCopyText&utm_medium=referral&utm_source=unsplash">Adrien Converse</a> on <a href="https://unsplash.com/photos/a-close-up-of-a-water-droplet-with-a-blue-background-kCrrUx7US04?utm_content=creditCopyText&utm_medium=referral&utm_source=unsplash">Unsplash</a>

Photo by <a href="https://unsplash.com/@fiveamstories?utm_content=creditCopyText&utm_medium=referral&utm_source=unsplash">Alex Shutin</a> on <a href="https://unsplash.com/photos/panoramic-photography-of-mountains-kKvQJ6rK6S4?utm_content=creditCopyText&utm_medium=referral&utm_source=unsplash">Unsplash</a>

Photo by <a href="https://unsplash.com/@8moments?utm_content=creditCopyText&utm_medium=referral&utm_source=unsplash">Simon Berger</a> on <a href="https://unsplash.com/photos/landscape-photography-of-mountains-twukN12EN7c?utm_content=creditCopyText&utm_medium=referral&utm_source=unsplash">Unsplash</a>

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

Maybe add some addons from https://www.npmjs.com/

- slidev-addon-rabbit // a customer-facing timer
- slidev-addon-asciinema
- slidev-addon-watermark
- slidev-addon-chartjs
- @katzumi/slidev-addon-qrcode
