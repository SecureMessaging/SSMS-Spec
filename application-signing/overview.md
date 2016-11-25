# Application Signing
 This document focuses application security and describes a process where code is released by the developers, signed and authenticated on the end-user devices such as the mobile phone and the web browser.

## Table of Contents
 * Overview
 * Packaging and Deployment
   * Release Feed
   * Manifesto Feed
 * Release Manifesto
   * Updating Signers
     * Adding Signers
     * Removing Signers
   * Updating Signing Rules
   * Signing Code
   * Releasing Code
 * End-User Application
   * Version Locking
   * Release Downloading
   * Release Authenticating
   * Release Updating

## Overview
For desktop, mobile and web applications an application host will exist to download and authenticate versions of the software. The host application is permanent and will only consist of the installable and bootstrapper. No updates will ever be released and the current version will be locked. The child application will be the main application that provides the messaging interface and services. It will be downloaded by the host application whenever a new version is released.

**Version Security**: The host application will contain a minimum of 3 public keys whose corresponding private keys are solely owned by individual application release signers. **Application Release Signers** are individual people who vet each release of the child application and sign off on it using their private keys. The **Host Application** when updating the child application will verify that it has been signed by all signers. If the host application finds an invalid or missing signature, it shall do it's best to publicly record the event and resume to use the last valid version.

**Version Locking**: Version numbers will be maxed out on the host application. The app version number will be set to the largest number the package manager can use. This will ensure that no future versions of Host Application can be released.

The **Release Manifesto** is a JSON document describing the release settings for the Host Application. The manifesto must be signed by all the signers, as described in the manifesto. The manifesto describes the next code release the Host Application should download.

## Packaging and Deployment

Two package manger feeds(or repository) are used to deploy updates. A dedicated NPM server will used for both package feeds.

### Release Feed

All builds of the client application will be uploaded to the release repository. The Host Application will download versions of this feed based on what the release manifesto says.

### Manifesto Feed

A release manifesto will be generated for each client application build and uploaded to the Manifesto Feed. The Host application will check this feed for software updates.

## Release Manifesto