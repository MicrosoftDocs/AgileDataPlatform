# Architectural Principles

## Introduction

These architectural principles will guide the architecture and ensure that it stays true to purpose.

## Minimise Trust

While traditional architectures place trust in a perimeter, cloud architectures must assume they will be attacked, and so require a different approach. No single component can be considered "trusted" and there should be no perimeters, since internal attacks are both more common and more successful than external attacks. As such, authentication, authorisation, and encryption should be included at every component, with strong credential management such as key rotation in place to reduce the time such an attack could be effective. This extends to compliance, with every team being responsible for demonstrating strong compliance within their project.

## Assume Change

Each module or component should expect change to happen. Loose coupling and external contracts can be utilised to make this easier to manage across the enterprise.

## Replaceability

Just as with change, it should be easy to change components. While a certain data warehouse might work well today, that might not be true tomorrow, and so the contract with the outside world must be based on provision of functionality, not on technology.

## State

Relying on state adds blockers to agility. If a component fails we should be able to replace it and the system function as intended. If we need to scale to accept more data, a cluster should be replaceable with a larger one, or a small script could be swapped out for an MPP solution. While a data platform might at first seem like the very definition of a stateful architecture, the components of it are not. For instance a data pipeline is not stateful, it is either running or completed, and if we run it a second time the outcome should be the same.

## Automation

Making changes at pace necessitates that those changes can be controlled and checked for quality, and that they are repeatable. This places a requirement to automate where possible.