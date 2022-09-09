## Detecting Malicious Application Dependencies

The project aims to bring Package Hunter, the malicious dependency detecting tool, to Kubernetes cluster, thus granting it more robustness, flexibility and portability. It is broken down into several parts:
1. Provide a native env for Falco monitoring/alerting
2. Run Package Hunter in a stable and scalable manner
3. Decouple the system into individual components
4. Improve Disk & Time consuming by K8s features

### Intro
`ORIGIN`: [Gitlab-GSoC-2022-Project](https://gitlab.com/gitlab-com/marketing/community-relations/contributor-program/gsoc-2022/-/issues/2)

`STACK`: Kubernetes, Node.JS, Helm, GKE, Falco, GRPC

`DELIVERY`:
  - [Package-Hunter](https://gitlab.com/gitlab-org/security-products/package-hunter)
  - [Package-Hunter-Operator](https://gitlab.com/gitlab-com/gl-security/security-research/package-hunter-runner-integration)

### RoadMap

#### Package-Hunter
- Phase 0: [Optimize memory by recycling finished tasks](https://gitlab.com/gitlab-org/security-products/package-hunter/-/merge_requests/31)
- Phase 1:
  - 1.1 [Code Refact: Make product extensible and backward-compatible](https://gitlab.com/gitlab-org/security-products/package-hunter/-/merge_requests/41)
  - 1.2 [Feature: Setup connection between Package-hunter and Falco](https://gitlab.com/gitlab-org/security-products/package-hunter/-/merge_requests/43)
- Phase 2:
  - 2.1 [Feature: Initalize K8s Job Scheduling](https://gitlab.com/gitlab-org/security-products/package-hunter/-/merge_requests/48)
  - 2.2 [Feature: Recycling & Status Management](https://gitlab.com/gitlab-org/security-products/package-hunter/-/merge_requests/52)


#### Operator
1. [Migrate Falco to K8s DaemonSet](https://gitlab.com/gitlab-com/gl-security/security-research/package-hunter-runner-integration/-/merge_requests/9/diffs?commit_id=9a7538ac5097e10a24784f32156816b3f9011629)
2. Secret Provisioning
    - [Enable Secret Auto-generation and Installation](https://gitlab.com/gitlab-com/gl-security/security-research/package-hunter-runner-integration/-/merge_requests/9/diffs?commit_id=367d94508fb99a90433cdc307b609a9c3e5cc5b4)
    - [Mount Configuration through K8s Secret](https://gitlab.com/gitlab-com/gl-security/security-research/package-hunter-runner-integration/-/merge_requests/9/diffs?commit_id=041008050b419feac011d4e1ee45613a7cc5c5d0)
    - [Add Scripts to Simplify Configuration](https://gitlab.com/gitlab-com/gl-security/security-research/package-hunter-runner-integration/-/merge_requests/9/diffs?commit_id=d319ebf13fdc61492fa51aa9d1c9e44391a4d3d9)
3. Alerts Collection
    - [Introduce Falco-sidekick to Aggregate Alerts](https://gitlab.com/gitlab-com/gl-security/security-research/package-hunter-runner-integration/-/merge_requests/9/diffs?commit_id=f5c4285b2dbf00b4727376886bdcfc704d447e05)
    - [Configure Sidekick Webhook](https://gitlab.com/gitlab-com/gl-security/security-research/package-hunter-runner-integration/-/merge_requests/9/diffs?commit_id=3cbcebd61a69efe81b9fd00455fd526604c47f07)
    - [Documentation](https://gitlab.com/gitlab-com/gl-security/security-research/package-hunter-runner-integration/-/merge_requests/9/diffs?commit_id=67d030ac86f5098fd7a40ac594977f40bbeb152c)
4. [Package-hunter K8s Authorization and Authentication](https://gitlab.com/gitlab-com/gl-security/security-research/package-hunter-runner-integration/-/merge_requests/9/diffs?commit_id=9c407a3c4faff197e89bb13df4b5fb472dc3e527)

### Mentors
[Dennis Appelt](https://gitlab.com/dappelt)

[Ethan Strike](https://gitlab.com/estrike)

Special thanks to my mentors! Dennis is my direct mentor who supported me daily over the project developing. Ethan manages the secure team that keeps track of our progress and give much technical&non-technical helps. Appreciate their kindness and guidance to bring me the success of the project.

### Appendix

#### Design
![design](https://user-images.githubusercontent.com/48944635/189432834-7b2a2dee-2a3c-4e2b-9fc6-bf9702af0123.png)

#### Proof of Manifest
![demo](https://user-images.githubusercontent.com/48944635/189431544-b8fc6b7f-d057-42d1-9b3d-fa4f09bf68db.png)



