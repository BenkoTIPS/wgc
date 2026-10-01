# DevOps

[Home](wgc.md) | [IaC](IaCOverview.md) | [DevOps](wgcDevOps.md) | [Naming](wgcNaming.md) | [Tagging](wgcTagging.md) | [Policy](wgcPolicy.md) | [LandingZones](wgcLandingZone.md)

DevOps brings development and operations practices together so that application and infrastructure changes can be delivered safely, repeatedly, and with useful feedback. For the Well Governed Cloud, DevOps provides the delivery process around the standards described in the [Infrastructure as Code](IaCOverview.md), [Policy](wgcPolicy.md), and [Azure Landing Zones](wgcLandingZone.md) documents.

## Delivery Principles

- **Version everything** - Keep application code, IaC, configuration templates, pipeline definitions, and documentation in source control.
- **Automate repeatable work** - Use pipelines for validation, provisioning, deployment, and verification.
- **Shift checks left** - Detect formatting, security, policy, and configuration issues before deployment.
- **Use least privilege** - Give pipeline identities only the permissions required for their deployment scope.
- **Promote through environments** - Validate changes in lower environments before production, using the same definitions wherever possible.
- **Make changes observable** - Record deployment results and monitor the health of the resources and applications that were changed.

## CI/CD Workflow

A typical workflow is:

1. A change is proposed through a pull request.
2. Automated checks run for code quality, IaC formatting, validation, security, and policy compliance.
3. IaC produces a reviewable plan or preview of the resource changes.
4. Approved changes are merged and deployed to a development or test environment.
5. Smoke tests and health checks verify the deployment.
6. Promotion to production requires the appropriate approval and uses the same versioned artifacts.

## Environment and Configuration Management

Keep environment-specific values separate from reusable deployment definitions. Store non-secret configuration in reviewed configuration files or approved platform configuration, and store secrets in a managed secret store such as Azure Key Vault. Do not commit credentials, connection strings, or private keys to source control.

Use consistent names and tags across environments as defined in the [Naming Standards](wgcNaming.md) and [Tagging Standards](wgcTagging.md). Make ownership, environment, and source clear enough to support operations and cost management.

## Operations and Governance

DevOps does not end when a deployment succeeds. Teams should define ownership, monitor availability and performance, review security findings, manage dependencies, and remove obsolete resources. Pipeline identities, service connections, and deployment logs should be reviewed regularly.

Changes that affect shared resources or landing zone controls should follow the governance requirements in the [Policy](wgcPolicy.md) and [Azure Landing Zones](wgcLandingZone.md) documents.

## Related Documents

- [Infrastructure as Code](IaCOverview.md)
- [Naming Standards](wgcNaming.md)
- [Tagging Standards](wgcTagging.md)
- [Policy](wgcPolicy.md)
- [Azure Landing Zones](wgcLandingZone.md)