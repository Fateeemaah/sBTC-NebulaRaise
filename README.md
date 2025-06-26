

#  sBTC-NebulaRaise

**sBTC-NebulaRaise** is a decentralized crowdfunding smart contract built on the Stacks blockchain using Clarity. It enables space-focused projects (or any visionary initiatives) to raise STX from the community in a trustless, transparent, and governance-driven way. Contributors can vote on fund release, get refunds if milestones fail, and participate in project lifecycles securely.

---

## 📦 Features

### 🚀 Project Lifecycle

* **Submit Projects**: Creators launch campaigns with a name, fundraising goal, and deadline.
* **Contribute STX**: Anyone can support active projects with STX tokens before the deadline.
* **Voting Governance**: Contributors vote post-deadline on whether the creator can withdraw funds.
* **Fund Withdrawal**: Project creators can only withdraw funds if:

  * The funding goal is met,
  * Voting threshold is satisfied,
  * Voting period has ended.
* **Refunds**: If a project fails to reach its goal or secure enough support, contributors can claim refunds.

---

## 🧠 Smart Contract Architecture

### ✅ Constants & Configuration

* `EXTENSION_THRESHOLD`: 75% of goal must be reached to allow deadline extensions.
* `MAX_EXTENSION_DAYS`: Up to 30 days extra allowed.
* `VOTING_PERIOD_DAYS`: 7 days voting period after deadline.
* `MIN_VOTE_THRESHOLD_PERCENT`: At least 60% of votes in favor required to release funds.
* `MIN_VOTE_COUNT_THRESHOLD`: At least 10 votes required for quorum.

### 🔐 Error Codes

Custom errors include:

* `ERR_UNAUTHORIZED`, `ERR_NOT_FOUND`, `ERR_ALREADY_EXISTS`, `ERR_GOAL_NOT_REACHED`, etc.

### 📊 Data Maps

* `projects`: Stores metadata for each project.
* `contributions`: Tracks each contributor’s amount.
* `votes`: Tracks contributor votes per project.

---

## 🛠️ Public Functions

### `submit-project (name, goal, deadline)`

* Starts a new campaign.

### `contribute (project-id, amount)`

* Adds STX support to a campaign before its deadline.

### `vote (project-id, in-favor)`

* Contributor votes on whether the project can release funds.

### `withdraw-funds (project-id)`

* Creator withdraws funds after a successful campaign and vote.

### `refund (project-id)`

* Contributor withdraws funds if campaign fails or vote fails.

### `cancel-project (project-id)`

* Creator cancels project before any contributions are made.

### `extend-deadline (project-id, new-deadline)`

* Extend campaign duration if 75% goal is reached and within limit.

---

## 🔍 Read-Only Functions

* `get-project`: Get project metadata.
* `get-contribution`: Get amount contributed by a user.
* `get-vote`: See how a user voted.
* `get-voting-status`: Shows total votes, favor votes, and if threshold is met.

---

## 🧪 Testing Guidelines

1. **Deploy** the contract using Clarinet or Stacks testnet.
2. **Simulate workflows**:

   * Project creation, contribution, voting, withdrawal, refund.
3. **Edge cases**:

   * Invalid input, duplicate votes, unauthorized access, deadline extensions.

---

## 📈 Future Improvements

* NFT or badge issuance for backers
* Milestone-based fund disbursement
* Cross-contract DAO integration
* Creator reputation tracking

---

## 🪐 Example Use Cases

* Space technology funding
* Educational STEM campaigns
* Science outreach programs
* Community satellite launches

---

## 🧾 License

MIT License — free to fork, use, and contribute with attribution.

---

## 🔤 Project Metadata (Clarinet `Clarinet.toml` or Manifest)

```toml
[project]
name = "cosmofund"
version = "0.1.0"
description = "Decentralized Crowdfunding Protocol for Visionary and Space-focused Projects"
```

---
