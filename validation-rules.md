# Validation Rules – Claims Processing API

## 1. Claim Creation Validations
- policyNumber is mandatory
- incidentDate cannot be a future date
- claimAmount must be greater than zero
- claimType must be one of MOTOR, HEALTH, LIFE

## 2. Document & Assessment Validations
- Claims cannot move to UNDER_ASSESSMENT without mandatory documents
- Documents can only be submitted for SUBMITTED or DOCUMENTS_PENDING states

## 3. Decision Validations
- Decision API can only be invoked in DECISION_PENDING state
- APPROVE moves claim to APPROVED
- REJECT moves claim to REJECTED
- Any other transition returns 409 Conflict

## 4. Payout Validations
- Payout initiation allowed only for APPROVED claims
- Rejected claims are ineligible for payout
