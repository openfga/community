# OpenFGA Community

[![CNCF Status](https://img.shields.io/badge/CNCF-Incubation-blue)](https://www.cncf.io/projects/openfga/)
[![License](https://img.shields.io/badge/License-Apache%202.0-green.svg)](https://github.com/openfga/openfga/blob/main/LICENSE)

[OpenFGA](https://openfga.dev) is a high-performance, flexible authorization system based on Google's Zanzibar paper. It enables developers to implement fine-grained access control using a simple, expressive modeling language.

This repository is home to the OpenFGA community resources.

## Quick Links

| Resource | Description |
|----------|-------------|
| [Documentation](https://openfga.dev/docs) | Learn about OpenFGA concepts and usage |
| [Playground](https://play.fga.dev) | Try OpenFGA models in your browser |
| [Official SDKs](https://openfga.dev/docs/getting-started/install-sdk) | SDKs for JS, Go, .NET, Python, Java |
| [Discord](https://discord.gg/8naAwJfWN6) | Chat with the community |
| [Roadmap](https://github.com/orgs/openfga/projects/1) | See what's coming next |

## Table of Contents

- [Getting Involved](#getting-involved)
- [Governance](#governance)
- [Brand Assets](#brand-assets)
- [Community Projects](#community-projects)
  - [SDKs, Libraries and Tools](#sdks-libraries-and-tools)
  - [AI Tooling](#ai-tooling-that-helps-with-openfga-implementation)
  - [Management Applications](#openfga-management-applications)
  - [Integrations](#integrations)
  - [IDEs and Editors](#ides-or-editors)
  - [API Gateways / Proxies](#api-gateways--proxies)
  - [Operations](#operations)
  - [Container Images](#container-images)
  - [Sample Applications](#sample-applications)
  - [Articles & Videos](#articles--videos)
- [Community Meetings](#community-meetings)

## Getting Involved

- To engage with the OpenFGA Community check the [community channels](https://openfga.dev/docs/community)
- To report issues in a repository, use the GitHub Issues section in that repository
- To contribute, check out the [contribution guidelines](https://github.com/openfga/.github/blob/main/CONTRIBUTING.md)


Learn about the OpenFGA project's Governance model by reviewing [this GOVERNANCE.md file](https://github.com/openfga/.github/blob/main/GOVERNANCE.md).

## Brand Assets

Navigate to the [brand-assets folder](https://github.com/openfga/community/tree/main/brand-assets) to find logos and other brand-related assets.

## Community Projects

> **Note**: The projects listed below are community-maintained. For official SDKs and tools, see the [Official SDKs](https://openfga.dev/docs/getting-started/install-sdk) documentation.

### SDKs, Libraries and Tools

| Project | Language/Framework |
|---------|-------------------|
| [OpenFGA ASP.NET Core + Worker Services SDK](https://github.com/Hawxy/Fga.Net) | .NET |
| [OpenFGA Dart SDK](https://github.com/amondnet/openfga.dart) | Dart |
| [OpenFGA Elixir SDK](https://github.com/drewble/fga-elixir-sdk) | Elixir |
| [OpenFGA PHP SDK](https://github.com/scor/openfga-php) | PHP |
| [OpenFGA Ruby SDK](https://github.com/carlastabile/openfga-ruby-sdk) | Ruby |
| [OpenFGA Rust SDK](https://github.com/openobserve/openfga-sdk) | Rust |
| [Canonical OpenFGA Library](https://github.com/canonical/ofga) | Go |
| [Openlane OpenFGA Extensions](https://github.com/theopenlane/iam/tree/main/fgax) | Go |
| [A middleware to secure routes in Fiber](https://github.com/ZEISS/fiber-authz) | Go (Fiber) |
| [Official Quarkus extension for OpenFGA](https://github.com/quarkiverse/quarkus-openfga-client) | Java (Quarkus) |
| [Official Quarkus Zanzibar support](https://github.com/quarkiverse/quarkus-zanzibar) | Java (Quarkus) |
| [Benchmarking & Load Testing with k6](https://github.com/jon-whit/k6-openfga-test) | Testing |
| [OpenFGA Tuple Manager](https://github.com/paulosuzart/fgamanager) | Tool |
| [Tuna - Tuple Generator for OpenFGA](https://github.com/aberforth4/tuna) | Tool |
| [Postman Collection](https://github.com/guillempuche/postman_openfga) | Tool |


### AI Tooling that helps with OpenFGA implementation

- [OpenFGA Agent Skills](https://github.com/openfga/agent-skills)
- [DeepWiki](https://docs.devin.ai/work-with-devin/deepwiki-mcp)
- [Context7](https://github.com/upstash/context7)

### OpenFGA Management Applications

- [OpenFGA Studio](https://github.com/prakashm88/openfga-studio)
- [OpenFGA Admin Console](https://github.com/yehia2amer/OpenFGA-Admin-UI)
- [OpenFGA Dashboard](https://github.com/dz1922/openfga-dashboard)

### Integrations

- [Custom Open Policy Agent with prototypical support for OpenFGA](https://github.com/thomasdarimont/custom-opa-openfga)
- [Keycloak OpenFGA integration](https://github.com/embesozzi/keycloak-openfga-workshop)
- [Keycloak OpenFGA Event Publisher](https://github.com/embesozzi/keycloak-openfga-event-publisher)
- [Keycloak OpenFGA Custom Event Listener for integrating with OpenFGA via Kafka](https://github.com/embesozzi/keycloak-openfga-event-kafka)
- [OpenFGA SCIM Bridge](https://github.com/SUSE-Skyscraper/openfga-scim-bridge)
- [Implementing ReBAC for Kubernetes with OpenFGA](https://github.com/luxas/kube-rebac-authorizer)
- [OpenFGA Webhook Authorizer for Kubernetes](https://github.com/jon-whit/openfga-authorizer)

### IDEs or Editors

- [Tree Sitter grammar for OpenFGA](https://github.com/matoous/tree-sitter-fga)
- [Neovim plugin for OpenFGA modeling language support](https://github.com/hedengran/fga.nvim)

### API Gateways / Proxies

- [Apache APISIX](https://github.com/embesozzi/apisix-authz-openfga)
- [Envoy](https://github.com/openfga/openfga-envoy)
- [Heimdall](https://github.com/dadrus/heimdall/blob/main/docs/content/guides/authz/openfga.adoc)
- [Kong](https://github.com/dol/kong-authz-openfga)
- [Zuplo](https://github.com/zuplo-samples/openfga-demo)

### Operations

#### Kubernetes & Infrastructure

- [Canonical OpenFGA Operator](https://github.com/canonical/openfga-operator) - A [Juju Charm](https://charmhub.io/openfga-k8s) for deploying OpenFGA on Kubernetes
- [Kubernetes Operator](https://github.com/3schwartz/fga-operator)
- [Terraform for AWS/Postgres](https://github.com/craigpastro/terraform-aws-openfga)

### Container Images

- [OpenFGA Rock](https://github.com/canonical/openfga-rock) - OCI image based on Ubuntu built using rockcraft
- [ChainGuard image](https://images.chainguard.dev/directory/image/openfga/)
- [Docker Hardened Image](https://hub.docker.com/hardened-images/catalog/dhi/openfga)

### Admin UI
- [https://github.com/yehia2amer/OpenFGA-Admin-UI](https://github.com/yehia2amer/OpenFGA-Admin-UI/)

### Sample Applications

- [Go Google Drive style API](https://github.com/Sambego/fga-demo-api)
- [NextJS Google Drive style Demo](https://github.com/oktadev/fga-drive-example)
- [Flask Demo](https://github.com/openfga/flask-demo)
- [Fine-grained authorization for AI agents using OpenFGA](https://github.com/Siddhant-K-code/agentic-authz)

### Articles & Videos

- [OpenFGA Modeling Guides](https://www.youtube.com/watch?v=5Lwy9aHXXHE&list=PLUR5l-oTFZqWaDdhEOVt_IfPOIbKo1Ypt)
- [OpenFGA Community Presentations](https://www.youtube.com/playlist?list=PLUR5l-oTFZqUAdAibhLw7l5IdqDnQ5gga)
- [OpenFGA Community Meetings](https://www.youtube.com/playlist?list=PLUR5l-oTFZqUneyHz-h4WzaJssgxBXdxB)
- [OpenFGA for Python Flask Applications](https://auth0.com/blog/fine-grained-access-control-with-python-flask/)
- [How to Implement Relationship-Based Access Control (ReBAC) in a Ruby On Rails API?](https://auth0.com/blog/what-is-rebac-and-how-to-implement-rails-api/)
- [Securing data in your Next.js app with Okta and OpenFGA](https://vercel.com/blog/securing-data-in-your-next-js-app-with-okta-and-openfga)
- [OpenFGA for an Express + Typescript Node.js API](https://auth0.com/blog/express-typescript-fga/)
- [OpenFGA for Spring Boot Applications](https://auth0.com/blog/add-fga-to-spring-boot-api-with-openfga/)
- [Building a Secure RAG with Python, LangChain, and OpenFGA](https://auth0.com/blog/building-a-secure-rag-with-python-langchain-and-openfga/)
- [Understanding ReBAC and ABAC Through OpenFGA and Cedar](https://auth0.com/blog/rebac-abac-openfga-cedar/)
- [Continuous Authorization Testing: FGA, GitHub Actions, and CI/CD](https://auth0.com/blog/continuous-authorization-testing-fga-github-ci-cd/)
- [Using an API Gateway with Fine-Grained Authorization](https://auth0.com/blog/using-api-gateway-fine-grained-authorization/)
- [Handling the Dual-Write Problem in Distributed Systems](https://auth0.com/blog/handling-the-dual-write-problem-in-distributed-systems/)

## Community Meetings

We hold a monthly meeting to interact with the community, collaborate and receive/provide feedback. You can find more details, including the time, our agenda, and the meeting minutes [here](https://github.com/openfga/community/blob/main/community-meetings.md).