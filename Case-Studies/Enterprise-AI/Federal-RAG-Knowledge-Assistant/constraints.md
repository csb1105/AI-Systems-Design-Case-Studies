# Constraints

## Technical Constraints
- The system must generate responses only from approved and retrievable source documents.
- The retrieval layer must support metadata filtering for access control, document type, topic, office, and sensitivity level.
- The system must maintain source attribution for generated responses.
- The model must not expose restricted or unauthorized content.
- Document ingestion must support version control and document freshness checks.
- The architecture must support secure deployment within federal or enterprise environments.

## Operational Constraints
- Source documents may be distributed across multiple repositories.
- Documents may vary in format, quality, structure, and update frequency.
- Users may ask questions that require context from multiple documents.
- Some queries may not have sufficient source evidence to support an answer.
- Human review may be required for high-risk, policy-sensitive, or ambiguous responses.

## Governance Constraints
- Responses must remain grounded in authorized sources.
- Audit logs must capture user queries, retrieved sources, generated outputs, and system actions.
- Access must be governed by role, organization, sensitivity level, and need-to-know.
- The system must support compliance with privacy, security, and records management requirements.
