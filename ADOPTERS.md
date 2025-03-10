# Who's using OpenFGA

OpenFGA is used by a wide range of companies and projects, and implementation services are offered by several consulting firms.

If you are using OpenFGA or providing services and your name is not on this list, please send us a PR!

## Companies/Projects using OpenFGA in production

These companies and projects are using OpenFGA in production.  If your company is using OpenFGA open a PR to add your company or project name and a description of how you are using OpenFGA.

| Company / Project | Use Case |
|-------------------|----------|
| [Okta FGA](https://fga.dev/) | Okta uses OpenFGA as the core engine for their Authorization as a Service product. |
| [Twintag](https://twintag.com) |  |
| [Mapped](https://www.mapped.com/) | MAPPED uses OpenFGA to model our business entities, including organizations, users, service accounts, plans, features, permissions, and roles. OpenFGA serves as the authoritative source for our service-to-service OAuth services, such as client credentials flow and token exchange flows. Additionally, we leverage OpenFGA to manage IoT identity authorizations.  |
| [Procure Ai](https://www.procure.ai/) | ProcureAi uses OpenFGA for user - > roles -> feature permission assignments, as well as fine grained data access permission to check what users can see within our procuretech solution. |
| [Canonical](https://ubuntu.com/) | Canonical is using OpenFGA as the backend permission service for the following internal and open source projects. We have also created an Ubuntu based, security maintained [container](https://github.com/canonical/openfga-rock) and a [Kubernetes operator](https://charmhub.io/openfga-k8s) based on Juju.<br><br>[Juju](https://juju.is/) - open source orchestration engine for software operators that enables the deployment, integration and lifecycle management of applications at any scale, on any infrastructure.<br><br>[Lxd](https://canonical.com/lxd) - open source solution for managing virtual machines and system containers. OpenFGA is used to govern both end user and service accounts permission.<br><br>[Microcloud](https://canonical.com/microcloud) - full stack private cloud solution based on LXD, Ovn and Ceph.<br><br>[Ubuntu Pro](https://ubuntu.com/pro) - Pro is Canonical's premier enterprise security subscription. OpenFGA is used in the backend services to govern customers entitlements (e.g. access to product support) and simplify self management operations.<br><br>Internal identity platform - self-hosted internal identity provider to govern access to Canonical privileged infrastructure.<br><br>Internal contact service - internal CPQ system to raise and approve customer quotes.<br><br>[Maas](https://maas.io/) (upcoming) - bare metal provisioning system, OpenFGA will be used to govern users, API and “sites” permissions.|
| [Wolt](https://wolt.com/) |  |
| [Italarchivi](https://www.italarchivi.it/) |  |
| [Read AI](https://www.read.ai/) |  |
| [Virtool](https://www.virtool.ca/) | Virtool uses OpenFGA to store and access administrator privileges. Replacement of our hand-rolled access control solutions by OpenFGA is on our roadmap. |
| [Configu](https://configu.com/) | Configu uses OpenFGA to provide organization administrators with advanced access control. By assigning roles and attributes to members, administrators ensure precise and secure access to configurations, tailored to each user’s specific responsibilities and needs. |
| [Fianu Labs](https://fianu.io/) |  |
| [ExcID](https://www.excid.io) | ExcID is developing access control solutions for data sharing leveraging OpenFGA. Particularly, multiple instances of OpenFGA are used for storing the relationships among data sources, as well as among data consumers. At the time of access control decision, appropriate relationships are combined. This is achieved using technologies such as W3C Verifiable Credentials and OAuth 2.0 token exchange. ExcID has combined OpenFGA with open-source user management systems and Policy Enforcement Points (PEPs). |
| [Minder](https://mindersec.github.io/) | [Minder](https://github.com/mindersec/minder/) uses OpenFGA to store hierarchical user->project permissions.  This is also used by [Stacklok](https://stacklok.com/)'s cloud service to store user access. |
| [Eiwa](https://eiwa.ag/) |  |
| [Moss](https://getmoss.com/) |  |
| [Agicap](https://agicap.com/) |  |
| [Instill AI](https://www.instill.tech/) |  |
| [Zuplo](https://zuplo.com) |  |
| [OpenObserve](https://openobserve.ai/) |  |
| [OpenLane](https://github.com/theopenlane) | OpenLane is using OpenFGA to provide fine grained authorization in our SaaS product offering. We are also maintaining an OSS [wrapper](https://github.com/theopenlane/iam/tree/main/fgax) and an [ent](https://entgo.io/) integration for [generation](https://github.com/theopenlane/iam/tree/main/entfga) of policies within our codebase. |
| [Sourcegraph](https://sourcegraph.com/) | Sourcegraph built [an internal-facing framework](https://sourcegraph.notion.site/MSP-IAM-framework-01f6e471a62245968453bfcb2cf052a3) aims to standardize how services think about and manage roles and permissions by offering a Zanzibar-style relationship-based access control (ReBAC) solution based on OpenFGA. |
| [Docker](https://docker.com/) |  |
| [Bump](https://www.bump-charge.com/) | Bump leverages OpenFGA to model car policies between companies and their employees, enabling the authorization of charging for company electric vehicles. |
| [Patika Global Technology](https://patikaglobal.com/) |  |
| [Gilion](https://www.gilion.com/) | Gilion leverages OpenFGA to handle a multi-tenancy setup that requires granular access management with hierarchies for different types |
| [flex](https://flex.team/) | flex leverages OpenFGA to implement a robust, centralized authorization system in our all-in-one HR SaaS Platform. This system delivers highly customizable Role-Based Access Control (RBAC), supporting hierarchical permission management across multiple levels - from organization and department level down to individual users and resources. This granular approach ensures precise access control while maintaining flexibility and scalability required for the entire platform. |
| [Lakekeeper](https://github.com/lakekeeper/lakekeeper) | Lakekeeper is an Apache-License Iceberg REST Catalog written in Rust that manages access to all your Iceberg tables in the heart of your Data & Analytics platform. Learn more about how we automate OpenFGA Store & Model management with Rust on [GitHub](https://github.com/lakekeeper/lakekeeper) and make sure to leave us a star!  |
| [Skyral](https://www.skyral.com/) | Skyral is a British software company that builds advanced modelling and simulation technology for enterprise, defence, and national security customers worldwide. We are using OpenFGA to build fine-grained authorization into our product to provide flexible access controls wherever it is deployed. |
| [Apache Syncope](https://syncope.apache.org/) | Apache Syncope is a full-fledged, multi-component Identity and Access Managemement system. OpenFGA can be optionally enabled in the deployments to allow for authorization checks.|

## Companies offering OpenFGA implementation services

These companies offer services and assistance implementing solutions with OpenFGA. This list is provided as a resource for organizations seeking expert assistance in adopting OpenFGA solutions but listed companies have not been individually evaluated or endorsed by the OpenFGA project. If your company provides OpenFGA implementation services, add your details by sending us a PR!

| Company | Company description and services offered | Contact |
|---------| ---------------------------------------- | ------- |
| [Kilterset](https://kilterset.com) | Experts in identity, we can assist in planning, crafting, testing, deploying, optimizing, and migrating complex app ecosystems to an FGA model. | [Contact form](https://kilterset.com/contact) |
| [Mrikal](https://www.mrikal.com) | Mrikal is a product studio and specializes in access control and permissions management solutions. We offer services including identity and access management (IAM), Fine-grained access control, custom software development, and consulting. Our focus is on enhancing security and simplifying management of digital resources for businesses | kalyan@mrikal.com [+91-8595270617](https://wa.me/918595270617) |

## Articles describing OpenFGA adoption

- GoDaddy: [Fine-grained authorization with OpenFGA and OAuth](https://www.godaddy.com/engineering/2023/12/12/authorization-oauth-openfga/)
- Configu: [Authorization Over Configurations using OpenFGA](https://configu.com/blog/authorization-over-configurations-using-openfga/)
- ExcID: [Relation-based access control using Verifiable Credentials](https://medium.com/@excid/relation-based-access-control-using-verifiable-credentials-d8e542a0ce1)
- Stacklok Minder: [Using OpenFGA to build a relationship-based authorization model in Minder](https://stacklok.com/blog/using-openfga-to-build-a-relationship-based-authorization-model-in-minder)
