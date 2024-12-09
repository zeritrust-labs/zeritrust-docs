# The ZeriTrust Project - Open security research

## Project Overview
The ZeriTrust Project extends "Zero Trust" approach and aims to facilitate and partially automate software verification for security and correctness throughout its entire lifecycle - from development through building, delivery, and execution.

The name represents approach to minimizing (zeroing) required blind trust to software creators.

## Problem Statement

As software users, when we entrust our valuable data, personal information, secrets, or anything we wouldn't want to share with anyone, we always have to trust someone. We must trust software creators that our data is securely protected and always used as intended. Even when using open-source software, where we can theoretically analyze the code ourselves, we usually have to trust experts to analyze the code for us and not miss any vulnerabilities. Some companies commission professional audits, but this process remains painstaking and slow, involving manual checking of paths, endpoints, and functionalities. And we have to finally trust that someone did their job well.

## Why This Matters

### For Users
Users need cryptographic proof and transparency, not just developers declarations, to verify:
- Who creates the software and if they are who they claim to be
- Whether the software being downloaded and run was actually built from the published sources
- If data is stored securely and processed only for the purposes it was provided for
- In case of End-to-End Encryption, whether the data truly never leaves the device in plain text
- Whether the software does nothing more than it declares - who it communicates with and what data it sends
- If the software contains no known vulnerabilities

### For Developers
While open source enables code review, the security audits are complex, challenging, time-consuming and ideally, should be repeatable for each release

The project helps developers answer crucial questions:
- How to persuade your users that your software is secure?
- How to persuade yourself that what you've created is as secure as possible?
- How to to answer above questions for every new release?

Even closed-source software can provide some level of transparency and proofs for security correctness.

## Project Scope

1. Collecting/linking publicly available knowledge (state of the art) regarding certain aspects of securing the software development process and secure coding, as well as tools, in one place.
2. Designing  runtime and data processing "contracts" that can be declared by the software creator, delivered with the software, and verified.
3. Providing recipes and/or tools for software creators.
4. Providing tools for users to facilitate software verification.

## Structure

### 1. Threat Modeling
We start by defining the threat model. Any discussion about security can devolve into an endless back-and-forth of more or less probable scenarios. Therefore, we must have specific threats that we analyze and want to defend against.

- Main `threat-model.md` file containing basic assumptions and methodology
- `/threats` directory containing detailed threat models for specific areas

### 2. Problems and Solutions
- `/topics` directory with main topics (e.g. build-signing)
- Each topic includes:
  - Problem description
  - Related [threats](#1-threat-modeling)
  - Current market practices

### 3. Implementation
All tools and implementations will be developed as separate repositories under the [ZeriTrust Labs](https://github.com/zeritrust-labs) organization. This approach allows for:
- Independent versioning of each tool
- Focused development and testing
- Clear separation of concerns
- Independent contribution guidelines for each tool
- Specific security requirements per tool

## Roadmap

Next [security topics](#2-problems-and-solutions) that will be covered by project:

**Phase 1 (Current Focus)**
- [ ] **Commit Signing and Verification** - Guides how to enforce cryptographic signing of commits
- [ ] **Reproducible Builds** - Discover how to creating deterministic build processes that allow verification that distributed artifacts match the source code

**Phase 2**
- [ ] **Data Containers** - Developing secure storage patterns for sensitive data with encryption at rest and strict access control mechanisms
- [ ] **Runtime Contracts** - Establishing transparent declarations of IO operations and communication patterns that can be verified during execution

**Phase 3**
- [ ] **Protected Data Chamber** - Creating isolated regions for sensitive data processing with controlled boundaries and verifiable data flow constraints
- [ ] **Build Contracts** - Delivering signed metadata from the build process including build logs, test reports, and security scan results

Each topic will undergo threat modeling and security analysis before implementation.

## Project Status

This project is currently in the "Ideation Phase". Many aspects may change, and numerous elements will need further refinement. At present, it represents an ambitious but fluid concept, and it's possible that several topics will conclude at the "knowledge gathering" stage.

The experimental password manager "Lock-Sphere" will serve as a proving ground for techniques, recommendations, and tools developed within this project. This practical application will help validate concepts and demonstrate real-world implementation of the security principles being developed.


