# Git Open Source Hodler

(Yes, it's [Hodler](https://en.wiktionary.org/wiki/hodl)).

**GOSH** is a blockchain built around securing the software supply chain and capturing the immense value in open source projects. This is achieved through record-setting blockchain tech, distributed programming, and a decentralized architecture - integrated into the same familiar git, meaning there is no change to the workflow.

### Motivation

The Software Supply Chain is a high-impact area. Yet there exists a distinctive lack of secure, trustless, verifiable, and transparent delivery of source code/binaries to developers and users in all software fields. Storing your code on a git means it has an owner, a single point of control, which leads to security vulnerabilities. Currently there is no industrial solution available that is not centralized and thus not dependent on the decisions of a few actors. The main way in which GOSH solves this issue is through allowing developers to build consensus around their code, so the more code is written, the more secure it becomes.

### Objective

To create a truly decentralized development environment so that open source repositories can be run, governed, and monetized collectively. All the while, mitigating security and transparency issues arising from a conventional software supply chain.

### Architecture

1. Build a scalable multithreaded, multisharded content addressable blockchain
2. Implement Git using [smart contracts](on-chain-architecture/gosh-smart-contracts.md)
3. Implement [DAO](on-chain-architecture/organizations-gosh-dao-and-smv.md) on top of that Git to allow building consensus around the code
4. Formally verify the smart contracts
5. Represent all entities by hashes (container images, git commits, blubs, pull requests etc.);
6. Allow anyone to add some metadata with signature to any entity;
7. Allow anyone to decide whose metadata to trust;
8. Build chain/tree of trust: dependencies can be organized using the same architecture, and containers built

### Instruments and utilities

A variety of utility tools to assist with all the aspects of the solution are under active development. Explore the tools available now to get started with GOSH:

* create and manage your on-chain repositories through [GOSH Web](working-with-gosh/gosh-web.md) or directly in the [Docker Extension](working-with-gosh/docker-extension.md)
* work with on-chain repository as if you use a regular git repository with [Git Remote Helper](working-with-gosh/git-remote-helper.md)
<!-- * [build and sign](working-with-gosh/build-and-sign-images.md) images straight from GOSH -->
<!-- * [verify images](working-with-gosh/verify-images-in-docker-extension.md) -->
