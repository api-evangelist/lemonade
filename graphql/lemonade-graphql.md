# Lemonade GraphQL Schema

## Overview

Lemonade is an AI-native digital insurance company offering renters, homeowners, car, pet, term life, and business insurance. Its platform is built around behavioral economics and AI-powered claims processing, including the "AI Jim" virtual claims bot that can approve claims in seconds.

The Lemonade Insurance API (available to partners via the developer portal at https://api-doc-portal.lemonade.com/) enables embedding insurance quoting, policy creation, and payment flows into third-party products. This GraphQL schema is a conceptual representation of the domain model underlying the Lemonade platform, derived from publicly available documentation, the partner API, and Lemonade's product surface area.

## Schema Design

The schema covers the full insurance lifecycle across all Lemonade product lines:

- **Quoting** — requesting and receiving insurance quotes for renters, homeowners, condo, car, pet, life, and business policies
- **Policy Management** — creating, modifying, renewing, and canceling policies; managing endorsements and riders
- **Claims** — filing claims, AI-assisted triage via AI Jim, instant approvals, settlements, and payments
- **Underwriting** — risk scoring, KYC verification, pricing factors, and documentation
- **Customers and Beneficiaries** — user profiles, billing, and coverage beneficiaries
- **Bundling** — multi-product bundle policies

## Key Types

| Type | Description |
|---|---|
| `Policy` | A live insurance policy in any product line |
| `PolicyType` | Enum of supported policy types (renters, homeowners, condo, car, pet, life, business) |
| `Coverage` | A specific coverage element attached to a policy |
| `CoverageLimit` | The maximum payout amount for a coverage element |
| `Deductible` | The amount the insured pays before coverage applies |
| `Premium` | Periodic payment amount and schedule for a policy |
| `Claim` | A filed insurance claim |
| `ClaimType` | Category of claim (theft, fire, water, liability, etc.) |
| `ClaimStatus` | Current processing status of a claim |
| `Incident` | The event underlying a claim filing |
| `IncidentDescription` | Natural language description of the incident |
| `ClaimSettlement` | The resolution of a claim after review |
| `ClaimPayment` | Disbursement of claim settlement funds |
| `Quote` | A price estimate for a prospective policy |
| `QuoteRequest` | Input parameters for generating a quote |
| `QuoteResponse` | Returned quote with pricing and coverage options |
| `Risk` | Abstract risk factors considered during underwriting |
| `PropertyRisk` | Risk factors specific to a physical property |
| `PersonalPropertyRisk` | Risk related to personal belongings |
| `LiabilityRisk` | Risk exposure for third-party liability |
| `PropertyDetails` | Structural and location details of insured property |
| `HomeAddress` | Full address for an insured property or mailing address |
| `RentalProperty` | A rental unit being insured under a renters policy |
| `Condo` | A condominium unit being insured |
| `House` | A standalone house being insured under a homeowners policy |
| `Apartment` | An apartment unit being insured |
| `PetPolicy` | Insurance policy covering a pet |
| `PetCoverage` | Coverage details specific to a pet insurance plan |
| `CarPolicy` | Auto insurance policy |
| `CarCoverage` | Coverage details for an auto policy |
| `LifePolicy` | Term life insurance policy |
| `LifeCoverage` | Coverage details for a life insurance policy |
| `BusinessPolicy` | Commercial / business insurance policy |
| `Device` | A mobile device being insured |
| `MobilePolicy` | Device insurance policy |
| `TravelerPolicy` | Travel insurance policy |
| `BundlePolicy` | A bundle combining two or more policy types |
| `Underwriting` | Underwriting decision record for a policy |
| `RiskScore` | Computed risk score used in pricing and eligibility |
| `PricingFactor` | An individual factor that influences the premium amount |
| `KYC` | Know Your Customer identity verification record |
| `Documentation` | A document associated with a policy or claim |
| `AIJim` | Lemonade's AI claims handling agent |
| `ClaimAI` | AI-assisted analysis applied to a claim |
| `InstantClaimApproval` | Record of a claim approved instantly via AI |
| `Endorsement` | A modification to coverage added to an existing policy |
| `Rider` | An add-on coverage extension attached to a policy |
| `Payment` | A payment transaction (premium or claim disbursement) |
| `BillingCycle` | Billing frequency and next payment date |
| `Cancellation` | A policy cancellation record |
| `Renewal` | A policy renewal record |
| `User` | A Lemonade platform user account |
| `Customer` | An insured customer profile |
| `Beneficiary` | A designated beneficiary on a life policy |

## Schema Source

This is a **conceptual schema** synthesized from:

- [Lemonade Partner API documentation](https://api-doc-portal.lemonade.com/)
- [Lemonade API announcement blog post](https://www.lemonade.com/blog/introducing-lemonade-insurance-api/)
- [Lemonade product pages](https://www.lemonade.com/)
- [Lemonade GitHub organization](https://github.com/lemonade-hq)
- Public knowledge of Lemonade's AI Jim claims system and product line

Lemonade does not publish a public GraphQL endpoint or official GraphQL schema. This schema represents the domain model implied by the REST partner API and public documentation, expressed in GraphQL SDL for developer reference and integration planning purposes.

## Resources

- Partner API Portal: https://api-doc-portal.lemonade.com/
- API Overview: https://www.lemonade.com/api
- GitHub: https://github.com/lemonade-hq
- Blog: https://www.lemonade.com/blog/
- Terms of Service: https://www.lemonade.com/api-terms
