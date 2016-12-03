# SSMS-Spec
## Overview
This document outlines the research and development of Secure Messaging and Authenticated Key Exchanges, otherwise know as SMAKE. The main goals outlined in this document is this:
 * Friendly and Encrypted Messaging Application(SSMS)
 * Secure Password Authenticated Key Exchanges(HR-PAKE)
 * Application and Development Security(EUARA, "End-User Application Release Authentication)

The development of this application is split in into three phases, where each phase focuses on critical area of research. Each phase does not have to necessarily build off the preceding phase, but will probably be written as research and code matures.

Each of the three phrases are split into their own spec document, as outline below.

## Phase 1 - [Research and Development of EUARA](phase-1/overview.md)
The vast majority of phase 1 will focus on development a framework that can release and authenticate signed code to multiple environments, such as the browser, mobile and desktop application. Releases will be signed not by a single signer, but board of signers who's job is to protect the integrity of each release. A minimalist messaging application will written for testing purposes. The messaging application will be rewritten in Phase 3. The spec for Phase 1 can be found [here](phase-1/overview.md).

## Phase 2 - [Research and Development of a PAKE protocol and Message Encryption](phase-2/overview.md)
Phase 2 focuses on getting the encryption done right. These days encryption algorithms are far to strong even from the largest of government agencies but, only if the encryption algorithms are implemented correctly. In addition to encryption, Phase 2 will develop and implement a Password Authenticated Key Exchange(PAKE) and a Public Key Infrastructure(PKI). These two systems will allow for the secure transfer of public keys. The spec for Phase 2 can be found [here](phase-2/overview.md).

## Phase 3 - [Feature Enhancement of the Messaging Application(SSMS)](phase-2/overview.md)
Phase 3 will focus on maturing and enhancing the messaging application. The goal is to refine the code and produce a messaging application that is as feature rich and user friendly as other popular applications such as, Facebook Messenger and Google Talk. The spec for Phase 3 can be found [here](phase-3/overview.md).