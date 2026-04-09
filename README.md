# Friday Knowledge Base

Curated, human-approved knowledge for the Friday AI DevOps platform.

## How it works

1. Friday agents extract knowledge from conversations
2. Agent proposes a PR to this repo with the extracted knowledge
3. A human reviews and approves (or edits) the PR
4. On merge, Friday re-ingests the repo into its vector store and knowledge graph

## Structure

```
_shared/              # Cross-agent knowledge (all agents can access)
  services/           # Service registry, ownership, dependencies
  namespaces/         # Kubernetes namespace mappings
  teams/              # Team structure, oncall, escalation
  architecture/       # System design, infrastructure topology

devops/               # Friday DevOps agent
  runbooks/           # Operational procedures
  tooling/            # CI/CD, internal tools

security/             # Friday Security agent
  policies/           # Security standards, approved configs
  compliance/         # Compliance requirements, audit findings

sre/                  # Friday SRE agent
  monitoring/         # Alert thresholds, SLO definitions
  incident-response/  # Playbooks, severity definitions
  postmortems/        # Past incident learnings

cloud-engineering/    # Friday Cloud Engineering agent
  cost-optimization/  # Savings opportunities, RI plans
  architecture-patterns/  # Approved reference designs

it/                   # Friday IT agent
  onboarding/         # Service and developer onboarding
  documentation/      # Wiki references, tool guides

access-assist/        # Friday Access Assist agent
  iam-roles/          # IAM role definitions, permission boundaries
  rbac/               # K8s RBAC policies
```

## Writing knowledge entries

Each file is a Markdown document. Use this format:

```markdown
# Title

Brief summary of the knowledge.

## Details

Supporting details, configuration, or procedures.

## Source

Where this knowledge was learned (conversation, incident, documentation).
```

## Taxonomy

See [taxonomy.yaml](taxonomy.yaml) for category definitions and examples.
The agent uses this file to decide where new knowledge belongs.
Reviewers can override placement during PR review.
