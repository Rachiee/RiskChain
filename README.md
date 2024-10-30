# RiskChain

**RiskChain** is a decentralized insurance smart contract built on Clarity that allows users to purchase, manage, and claim insurance policies in a trustless and transparent way. By leveraging smart contracts, RiskChain eliminates intermediaries, ensuring faster processing, secure policy ownership, and verifiable claim management. 

## Features

- **Policy Creation**: The contract owner can define insurance policy templates with coverage amounts, premiums, and expiration terms.
- **Policy Purchase**: Users can buy insurance policies with specified coverage and duration. Premiums are calculated based on coverage amount and policy length.
- **Claim Filing**: Insured users can file claims against their policies. The contract automatically verifies claim eligibility and transfers the payout if conditions are met.
- **Fund Management**: Collected premiums are stored in an insurance fund, which is used to pay out valid claims.
- **Read-Only Queries**: Provides read-only functions to check policy details, claim status, and the current balance of the insurance fund.

## Contract Components

### Constants and Errors

- **Contract Owner**: The creator of the contract is set as the owner, responsible for managing policy templates.
- **Errors**: Custom errors include:
  - `err-owner-only`: Only the contract owner can create policies.
  - `err-not-insured`: Indicates a user without a valid policy trying to make a claim.
  - `err-invalid-claim`: Invalid claim amount exceeding policy coverage.
  - `err-insufficient-payment`: Insufficient funds in the insurance fund for claim payout.

### Data Maps

- **`insurance-policies`**: Stores details of each user’s policy, including coverage, premium, and expiration.
- **`insurance-claims`**: Tracks claim amounts and statuses for each insured user.

### Variables

- **`insurance-fund`**: Holds the total STX collected from premiums and available for claim payouts.

## Functions

### Admin Functions

- **`create-policy`**: Allows the contract owner to create a new insurance policy with specific coverage, premium, and duration.

### User Functions

- **`purchase-policy`**: Allows users to purchase a policy, transferring the calculated premium to the insurance fund and setting up coverage for a defined term.
- **`file-claim`**: Enables users to file a claim, which deducts the requested amount from the insurance fund if the claim is valid and within coverage limits.

### Read-Only Functions

- **`get-policy-details`**: Returns a user’s policy details, such as coverage amount, premium, and expiration.
- **`get-claim-details`**: Provides information on a user’s past claims, including amount and status.
- **`get-fund-balance`**: Returns the current balance of the insurance fund.

## Usage

RiskChain provides a decentralized insurance platform where users can securely purchase and claim policies without intermediaries. By enforcing transparent policy conditions and streamlined claims management, RiskChain brings trust and accessibility to decentralized insurance.

---

### License

This project is licensed under the MIT License.