# Investigation

**Bounty Link:** [Bounty name](link)<br/>
**Reward:** $<br/>
**Code Link:** [Repo name](link)<br/>
**Fork Link:** [Fork name](link)<br/>

## Use Case

Here we aim to thoroughly understand the target project’s architecture without running any code. 80% of all bugs and exploits come from business logic exploits.

- [ ] Read the white paper: *white paper link*
- [ ] Read any available technical resources to gain insights into the project’s purpose, architecture, and underlying technologies
  - [ ] *Resource link*
  - [ ] *Resource link*
  - [ ] …
- [ ] Read reports on previous audits & get familiar with similar protocols
  - [ ] *Audit link*
  - [ ] *Audit link*
  - [ ] …

## Dev Environment

We want to get the code up and running locally so we can test things against it while investigating the details
- [ ] Code is running locally
- [ ] Verified the “happy path”
- [ ] (optional) test are passing locally

Idea 💡 Automated Test Suites: This doesn’t exist yet, but we were discussing writing contracts or contract generators to test common vulnerabilities against bounties. A really easy first step could be “fork repo -> run automated scans in CI/CD to get the test env set up”. Would likely save a lot of time. We’ll build this suite as we go. 

## Project Architecture and Code Review

Perform a comprehensive review of the project’s source code.
- solidity-metrics: Solidity Code Metrics to get the scope of the project, and place them in Scoping Phase Sheets, organized by size. Start with the least complex and work your way up to build context. Also a good way to split up work with a team!
- Analyze smart contracts, libraries, and other code involved by taking notes on/in the fork. Constantly be thinking, “How can I break this?” or “Does this do what it should be doing?”
- Look for common vulnerabilities like reentrancy, overflow/underflow, permission issues, improper input validation. Leverage code analysis tools to identify potential issues
- Communicate with the developers!!
- USE AI

### Notes

*Add notes here*

## Potential Attack Surfaces
Identify Attack Surfaces
- Identify and list the the different components and attack surfaces within the project. [i.e. smart contracts, decentralized apps, blockchain interactions, APIs, etc]. Understand how these components interact with each other and external systems.
- Map Attack Surfaces [This helps in prioritizing your testing efforts.]
  - Map out the attack surface by identifying the entry points and potential paths an attacker could exploit.
Nmap is a useful tool to see which ports are open. Use wordlists to check for possible openings: i.e. /content (Status: 301) [Size: 316] [--> http://10.10.117.255/content/]
  - Consider both internal and external interactions, such as user inputs, contract calls, or external dependencies.

## Manual Testing and Auditing
Test with Test net
- Deploy the project on a test net environment if available.
- Test different scenarios, transactions, and edge cases to uncover potential vulnerabilities or unexpected behavior.

Validate Fuzz, Input, and Invariant Logic
- Conduct fuzzing and input validation testing to identify vulnerabilities caused by unexpected or malicious inputs. See Fuzz & Invariant Tests | The secret to finding CRITICAL vulnerabilities faster
- Test for input sanitization, boundary conditions, and potential injection attacks. Use various tools and techniques to generate different input patterns and payloads.

Audit Smart Contracts
- **Pay special attention to the smart contracts within the project.**
- Perform a thorough security audit, **analyzing the contract's logic, data flow, and potential vulnerabilities.**
- **Check for secure coding practices, proper access control mechanisms, and potential code vulnerabilities.**

Test Blockchain Interaction
- If the project interacts with a blockchain, perform specific testing related to the blockchain integration.
- **Verify the integrity of data on the blockchain, analyze transaction validation, and test for potential blockchain-specific vulnerabilities like double-spending or front-running attacks**

Test API and External Integration
- If the project exposes APIs or integrates with external systems, thoroughly test those interactions.
- Verify the input validation, authentication mechanisms, and potential security risks associated with external dependencies. Test for data leakage or unauthorized access.