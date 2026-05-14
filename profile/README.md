
<p align="center">
  <a target="_blank" href="https://mojaloop.io">
    <img src="https://raw.githubusercontent.com/mojaloop/.github/main/profile/mojaloop_logo.png"/>
  </a>
</p>

# 1. Welcome to the Mojaloop Open Source Site on Github

**Quick-links**:
* Review the documentation: http://mojaloop.io/documentation
* Join the Conversation on Slack: https://mojaloop.io/slack
* Latest Mojaloop release: https://github.com/mojaloop/helm/releases/tag/v17.2.0

## 2. From a Technical Perspective

Mojaloop implements a set of core functions:

  |Alias Resolution|Clearing|Settlement|
|:--------------:|:--------------:|:--------------:|
|Payee address or **alias resolution**, ensuring that the account-holding institution – and thereby the correct payee account - is reliably identified|**Clearing** of payments end to end, with robust measures that remove any element of doubt about the success of a transaction|Orchestration of **Settlement** of cleared transactions between financial institutions using a model agreed between those institutions, and according to a predefined schedule.|

&nbsp;
(Note: This is taken from the Product section of the Mojaloop official documentation at docs.mojaloop.io where you can find more details)

These core functions are supported by some [unique characteristics](https://github.com/mojaloop/documentation/blob/master/docs/product/features/transaction.md#unique-transaction-characteristics), which
together make Mojaloop a low cost, inclusive instant payments system:

1.  **A Three Phase Transaction Flow**, as follows:
	+  **Discovery,** when the Payer's DFSP works with the Mojaloop Hub to determine where the payment should be sent, so ensuring that transactions are not misdirected. This phase resolves an alias to a specific Payee DFSP and, in collaboration with that DFSP, an individual account.

	 + **Agreement of Terms, or Quotation,** when the two DFSP parties to the transaction both agree that the transaction can go ahead (supporting, for example, restrictions relating to tiered KYC), and on what terms (including fees), **before** either commits to it.

	+  **Transfer,** when the transaction between the two DFSPs (and by proxy their customers' accounts) is cleared, and it is guaranteed that both parties have the same, real-time view of the success or failure of the transaction.
&nbsp;

2.  **End to End Non-Repudiation** guarantees that each party to a message can be assured that the message has not been modified, and that it really was sent by the purported originator. This underlying technology is leveraged by Mojaloop to guarantee that a transaction will only be committed if *both* the Payer *and* the Payee DFSPs accept that it is, and neither party can repudiate the transaction. Naturally, it also guarantees that no third party can modify the transaction.
3.  **The PISP API is made available through the Mojaloop Hub,** not by individual DFSPs. Consequently a fintech can integrate with the Hub and immediately be connected to **all** connected DFSPs. 

**Note** In Mojaloop terms, a DFSP - or Digital Financial Service Provider - is a generic term for any financial institution, of any size or status, that is able to transact digitally. It applies equally to the largest international bank and the smallest Microfinance Institution or mobile wallet operator. "DFSP" is used throughout this document.   
&nbsp;

## The Mojaloop Ecosystem

### The Core
In reading this document, it is important to understand the terminology used to identify the various actors, and how they interact. The following diagram provides a high level view of the Mojaloop ecosystem.

![Mojaloop Ecosystem](https://github.com/mojaloop/documentation/blob/master/docs/product/features/ecosystem.svg)

### Overlay Services
Around the core illustrated in the above diagram there are a set of overlay services, which also form part of the complete Mojaloop open source package. These are:
- The **Account Lookup Service** (ALS), and a number of oracles that are used by the ALS in alias resolution;
- A set of **portals**, built to use the Business Operations Framework, which allow a hub operator to interact with/manage the Mojaloop Hub;
- A **Merchant Payments** module, which supports merchant registration and the issuing of merchant IDs, including the generation of QR Codes which can be scanned to initiate a merchant transaction;
- The **Testing Toolkit** (TTK), which allows engineers to simulate any aspect of the Mojaloop core ecosystem, to facilitate their development, integration and testing efforts;
- An **Integration Toolkit** (ITK), part of the [connectivity support](https://github.com/mojaloop/documentation/blob/master/docs/product/features/connectivity.md) library, which facilitates the connection between a DFSP and a Mojaloop Hub;
- **ISO 8583 integration**, which allows ATMs (or an ATM switch) to be integrated with a Mojaloop Hub, for cash withdrawals;
- [**MOSIP integration**](https://www.mosip.io), which allow payments to be routed to a MOSIP-based digital identity, rather than (say) a mobile phone number.

### Feature List

This document presents a feature list which covers the following aspects of Mojaloop:

-   [**Use Cases**](https://github.com/mojaloop/documentation/blob/master/docs/product/features/use-cases.md), describing the use cases supported by every Mojaloop deployment.
-   [**Transactions**]([./transaction.md](https://github.com/mojaloop/documentation/blob/master/docs/product/features/transaction.md)), describing the Mojaloop APIs, how a transaction proceeds, and the aspects of a Mojaloop transaction that make it uniquely suited to the   implementation of an inclusive instant payments service.

-   [**Risk Management**]([./risk.md](https://github.com/mojaloop/documentation/blob/master/docs/product/features/risk.md)), setting out the measures taken to ensure that no DFSP participating in a Mojaloop scheme is exposed to any counterparty risk, and that the integrity of the scheme as a whole is protected.

-  [**Connectivity Support**](https://github.com/mojaloop/documentation/blob/master/docs/product/features/connectivity.md), describing the various tools and options for straightforward onboarding of participating DFSPs.

-  [**Portals and Operational Features**](https://github.com/mojaloop/documentation/blob/master/docs/product/features/connectivity.md), such as portals for user and service management, and the configuration and operation of a Mojaloop Hub.
-  [**Fees and Tariffs**](https://github.com/mojaloop/documentation/blob/master/docs/product/features/tariffs.md) sets out the mechanisms that Mojaloop provides to support a range of different tariff models and the opportunities for participants and hub operators to levy fees.

-  [**Performance**](https://github.com/mojaloop/documentation/blob/master/docs/product/features/performance.md)), outlining the transaction processing performance adopters might expect. 
- [**Deployment**](https://github.com/mojaloop/documentation/blob/master/docs/product/features/deployment.md), describing the different ways to deploy Mojaloop for a range of different purposes, and the tools that facilitate these deployment types. 
- [**Security**](https://github.com/mojaloop/documentation/blob/master/docs/product/features/security.md), covering the security of the transactions between connected DFSPs and the Mojaloop Hub, the security of the Hub itself (including the operator portals), and the QA Framework currently being developed to validate the security and quality of a Mojaloop deployment.
- [**Engineering Principles**](https://github.com/mojaloop/documentation/blob/master/docs/product/features/engineering.md), such as algorithmic adherence to the Mojaloop specification, code quality, security practices, scalability and performance patterns (amongst others).

-   [**Invariants**](https://github.com/mojaloop/documentation/blob/master/docs/product/features/), setting out the development and operational principles to which any Mojaloop implementation must adhere. This includes the principles which ensure the security and integrity of a Mojaloop deployment.

&nbsp;
### Continuous Development
No software is ever finished, and Mojaloop is no exception. There are always new features to be considered, new APIs to be implemented, new portals to be added, and of course there is always ongoing maintenance, and security requires constant vigilance.

The Mojaloop Roadmap addresses and prioritises these needs, placing them on a timeline, and defines them as a set of workstreams. Each of these work streams has a workstream lead, responsible for defining, managing and delivering the workstream to the Mojaloop Community. The workstream lead is supported by a number of contributors, who may be engineers helping to implement a feature, or those who can document the feature, or people helping to define the requirements.

You can view the current set of workstreams and their latest status reports in the [**Continuous Development** section](https://github.com/mojaloop/documentation/blob/master/docs/product/features/development.md) and https://community.mojaloop.io/active-workstreams.

## 3. Mojaloop Github Repositories

Mojaloop GitHub repos are categorized here into core repositories, libraries and supporting services: https://docs.mojaloop.io/technical/technical/deployment-guide/mojaloop-repository-update-guide.html#repository-categories

## 4. Licensing

Mojaloop Open Source Software (OSS) is licensed under Apache 2.0: https://github.com/mojaloop/project/blob/master/LICENSE.md 

## 5. Join the slack community!

[Self-invite](https://join.slack.com/t/mojaloop/shared_invite/zt-3gmte4pgw-CZQHK5JEOGHid4ajcBNCDQ) yourself to the Mojaloop community to discuss issues, features or any topics related to Mojaloop (or reach out to one of the [Administrators](mailto:info@mojaloop.io) ).
