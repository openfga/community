# Related Projects

A list of CNCF projects that target solving access control in different ways can be found below:

 - [Open Policy Agent (OPA)](https://www.cncf.io/projects/open-policy-agent-opa/) is a general-purpose policy engine that has an emphasis on policy enforcement for cloud infrastructure. Since OPA is a policy engine, it doesn’t define an authorization “model” but supports and accepts arbitrary structured data from a variety of systems so they can be inspected during an authorization check, it requires data to be provided during evaluation time. 
 
    OpenFGA is different since it is built for application authorization. Since authorization logic and data is pre-loaded to a centralized system, it can quickly provide an authorization decision to the application based on the provided user/object relationship. There is potential to use OpenFGA with OPA.
 
- [Paralus](https://www.cncf.io/projects/paralus/) is a tool that enables controlled, audited access to Kubernetes infrastructure. Paralus already incorporates some roles in their product to allow their users to manage access for their collaborators. There is potential collaboration between OpenFGA and Paralus to offer administrators the ability to manage access at a more granular level, which will improve their standing as a k8s access manager, especially for larger teams.

- [Kyverno](https://github.com/kyverno) is a project that focuses on implementing security policies for Kubernetes deployments.
