## Overview
## Goal
 * To provide encrypted P2P messaging via WebRTC.
 * To setup a playground to research:
   * Encryption speed and optimization 
   * Application Version Security 

## User Experience

Platforms: Browser, PC App, Mobile App 

### Experience A
 * User visits site or app
 * User clicks, “start conversation”
 * Site generates random conversation secret and loads conversation screen
 * User shares conversation secret with other users.
 * User sends messages


### Experience B
 * User receives shared conversation secret
 * User visits site or app
 * User clicks, “Join Conversation” and enters secret
 * Site loads conversation screen
 * User sends messages


## Encryption
This project will use PGP like message encryption. Each message will
 * Be encrypted with RSA256 
 * Have a unique unique RSA256 secret
 * Have a MAC
 * Use a public key to encrypt the secret


The key pair will be generated using the conversation secret such that any user with the secret will generate the same key pair.