# Earthly: A write once, run anywhere CI/CD framework

Come learn about Earthly, a simple CI/CD framework that lets you create repeatable builds that run parallelized and cached locally, as well as in your favorite CI system.

Whether you're building PowerShell modules, binary artifacts in go, rust or C#, or container images, Earthly can act as a layer between your language-specific tooling and your cloud CI specs, simultaneously parallelizing and speeding up your builds and making failures reproducible locally, thus easier to troubleshoot, even when they are cross-platform, cross-repository builds!

In this talk we'll go through a few different scenarios featuring different languages and output types to show how to build them with Earthly, and how to run those builds locally and in cloud CI/CD. We'll talk about how Earthly's container-based builds are self-contained, isolated, reproducible and portable. Earthly works correctly whether you run it on your laptop or your colleagues, or in your cloud CI/CD platform. We'll also show some of Earthly's composability, with build logic across multiple build files at different levels in your directory structure, or even in other repositories. Finally, I'll show you some speed benchmarks, and how Earthly's automatic parallelization and caching can speed up your builds -- whether you're running them locally or in your CI system!

https://earthly.dev/earthly-github-actions
