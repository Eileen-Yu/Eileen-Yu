---
title: Empowering Kubebuilder - My GSoC 2023 Journey with Phase 2 Plugin
categories: [tech]
---

I am thrilled to have the opportunity to participate in the Google Summer of Code
(GSoC) again this year with CNCF, as to continue my exploration in the cloud native field!

In this post, I would share the highlights of my endeavors, learnings, and contributions during this exhilarating summer ☀️

### About Kubebuilder

[Kubebuilder](https://github.com/kubernetes-sigs/kubebuilder) is a remarkable tool that streamlines the process of constructing Kubernetes APIs using custom resource definitions (CRDs).

As the Kubernetes ecosystem proliferates, tools like Kubebuilder that assist developers in crafting Kubernetes-native applications become invaluable. 

To see more about Kubebuilder: https://book.kubebuilder.io/introduction

### Mentors

I was so fortunate to have the guidance and mentorship of [Bryce Palmer](https://github.com/everettraven), [Camila Macedo](https://github.com/camilamacedo86) and [Rashmi Gottipati](https://github.com/rashmigottipati)!

Their sensible insights, unweaving support, and responsive feedback not only taught me much professional knowledge, but also were instrumental in aligning my contributions with the broader community vision.

### My Project

My contribution is mainly around external plugin, which enables users to develop, use, maintain and release their own plugins independently for customized layouts or addons on top of the scaffolds done by Kubebuilder's default scaffolding.

An external plugin is an executable (can be written in any language) that implements an execution pattern that Kubebuilder knows how to interact with. 

<p align="center">
  <img src="https://github.com/kubernetes-sigs/kubebuilder/assets/48944635/c11094b8-64bc-4523-9dd5-b7197ac75178" title="How the external plugin communicates with Kubebuilder">
  <br>
  <em>How the external plugin communicates with Kubebuilder</em>
</p>

The introduction of external plugin extends Kubebuilder's functionality. With external plugin, there would be some more obvious improvements:

- Plugins can be developed separately and integrated into Kubebuilder as needed.
- Plugins do not have to be compiled with the Kubebuilder CLI binary.
- Kubebuilder can discover and use external plugins in a chaining mode.
- Grant greater flexibility and modularity for Kubebuilder, extending the ecosystem.
- Give users the freedom to customize and extend plugins.
- Easier to maintain and update the external plugins.


#### 1. Getting familiar with plugin architecture

End-to-end (E2E) tests serves as a pragmatic approach for deep architectural comprehension of plugins.
This practice has provided me with insights into the plugin interoperability and systemic behavior, encompassing not merely isolated functionalities but also overall robustness and reliability.
It contributes to a more holistic understanding of system architecture and improving the overall quality of the software stack.

For enhanced long-term maintainability, we have integrated GitHub's Dependabot into our development pipeline.
This automated tool systematically scans for outdated dependencies and proactively fetches updates, thereby streamlining the version management process.
This integration not only keeps our codebase current but also mitigates potential security vulnerabilities by ensuring that we are always utilizing the most up-to-date software packages.

`Deliverables`:

[Add e2e tests for sample external plugin](https://github.com/kubernetes-sigs/kubebuilder/pull/3419)

[Update go version for external plugin sample](https://github.com/kubernetes-sigs/kubebuilder/pull/3412)



#### 2. Improving Plugin Usability: Features and Fixes

Given that the external plugin is in its early stage of development, our deep-dive into its functionalities revealed a series of challenges.
To address these, we've implemented a set of enhancements and bug fixes. 

Notably, we've introduced a feature that allows users to tailor the installation for their plugins.
Additionally, we've extended the plugin's capability to scaffold files in nested directories. 
To bolster the quality assurance process, unit tests have been added to validate these new functionalities.

At present, we are actively working to synchronize configuration settings between Kubebuilder and the external plugins.
This integration aims to capture a history of utilized plugins and their associated combinations, as well as keep a record of scaffolded resources like APIs and webhooks.
This advancement will significantly enhance the 'chaining mode' capabilities, thereby offering users increased flexibility in their scaffolding endeavors.

`Deliverables`:

[Make external plugin path configurable](https://github.com/kubernetes-sigs/kubebuilder/pull/3437)

[Ensure external plugin can scaffold files in new directories](https://github.com/kubernetes-sigs/kubebuilder/pull/3519)

[Externalize config struct to be available for external plugin](https://github.com/kubernetes-sigs/kubebuilder/pull/3554)

[Pass config between KB and external plugin](https://github.com/kubernetes-sigs/kubebuilder/pull/3526)



#### 3. Crafting Comprehensive User Tutorials With JavaScript Example

In order to flatten the learning curve associated with our external plugin offering, we've diligently crafted extensive documentation.
This guides users through the entire process of writing, building, and installing a plugin that is compatible with Kubebuilder. 

One of the most compelling features of our external plugin framework is its language-agnostic design, allowing plugins to be developed in any programming language.

To validate this flexibility and gain deeper insights into our plugin architecture, I developed a sample plugin using JavaScript.
This hands-on experience not only enriched the tutorial content, providing substantial value to our users, but also served as a practical example in our official guidelines, offering users an illustrative case study.

`Deliverables`:

[Add tutorial for external plugin](https://github.com/kubernetes-sigs/kubebuilder/pull/3488)

[Sample KB external plugin written in JavaScript](https://github.com/Eileen-Yu/kb-js-plugin)

### Showcase

![output](https://github.com/kubernetes-sigs/kubebuilder/assets/48944635/1aac358e-6488-4166-bdef-0b73d916423a)
