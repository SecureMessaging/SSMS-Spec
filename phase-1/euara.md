# End-User Application Release Authentication System
 This document focuses application security and describes a process where code is released by the developers, signed and authenticated on the end-user devices such as the mobile phone and the web browser. This system is designed to protect the user and application against the following attacks.

 * DNS Hijacking
 * Malign versions
 * Man-in-the-Middle(MitM) attacks

## Table of Contents
 * Overview
 * Definitions
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

## Definitions / Terms

 * **Feed** - A NPM repository used to store and download software releases
 * **User Application** - Is the JavasScript/HTML application that user's interact with and the one that will be signed with each release. 
 * **Application Verifier** - For mobile and desktop is the native application and for the browser is an extension. The main purpose of the Application Host is to download the Front End Application verify its integrity and then run it. It is there to ensure the User Application has not been tampered with. 

## Overview
For desktop, mobile and web applications a application host will exist to download and authenticate versions of the software. The Application Verifier is permanent, no updates will be released and the current version will be locked. The User Application will be the main application that provides the messaging interface and services. It will be downloaded by the Application Verifier whenever a new version is released.

**Version Security**: The Application Verifier will contain a minimum of 3 public keys whose corresponding private keys are solely owned by individual application release signers. **Application Release Signers** are individual people who vet each release of the User Application and sign off on it using their private keys. The **Application Verifier** when updating the User Application will verify that it has been signed by all signers. If the Application Verifier finds an invalid or missing signature, it shall do it's best to publicly record the event and resume to use the last valid version.

**Version Locking**: Version numbers will be maxed out on the Application Verifier. The app version number will be set to the largest number the package manager can use. This will ensure that no future versions of Application Verifier can be released.

The **Release Manifesto** is a JSON document describing the release settings for the Application Verifier. The manifesto must be signed by all the signers, as described in the manifesto. The manifesto describes the next code release the Application Verifier should download.

## Packaging and Deployment

Two package manger feeds(or repositories) are used to deploy updates. A dedicated NPM server will used for both package feeds. The first package feed will house each manifesto release and the second is for the User Application releases.

### Release Feed

All builds of the client application will be uploaded to the release repository. The Application Verifier will download versions of this feed based on what the release manifesto says.

### Manifesto Feed

A release manifesto will be generated for each client application build and uploaded to the Manifesto Feed. The Application Verifier will check this feed for software updates.

## Release Manifesto  

The Release Manifest instructs the **Application Verifier** what to download and who the signers are.


Click [Here](release-manifest.json) for an example manifest.


