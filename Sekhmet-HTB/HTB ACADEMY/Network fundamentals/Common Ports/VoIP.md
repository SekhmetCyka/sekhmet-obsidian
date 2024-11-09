### VoIP (Voice over Internet Protocol)

- **Definition**:
  - Method of transmitting voice and multimedia communications over the internet.
  - Examples include Skype, WhatsApp, Google Hangouts, Slack, and Zoom.
  
- **Common VoIP Ports**:
  - **TCP/5060 and TCP/5061**: Used for the Session Initiation Protocol (SIP).
  - **TCP/1720**: May be used by some VoIP systems for the H.323 protocol, although SIP is more widely used.

- **Protocols**:
  - **Session Initiation Protocol (SIP)**:
    - Signaling protocol for initiating, maintaining, modifying, and terminating real-time sessions.
    - Involves video, voice, messaging, and other communication applications and services.
    - Uses requests and methods between endpoints.
    
  - **H.323 Protocol**:
    - Set of standards for multimedia communication over packet-based networks.
    - Less commonly used than SIP in VoIP systems.

### Common SIP Requests and Methods

- **INVITE**: Initiates a call by inviting a user to participate in a session.
- **ACK**: Confirms that the client has received a final response to an INVITE request.
- **BYE**: Terminates a session between two users.
- **CANCEL**: Cancels any pending requests.
- **OPTIONS**: Queries the capabilities of servers.
- **REGISTER**: Registers a user's location and associates the user's SIP address with their current location.

SIP uses these methods to manage and control communication sessions effectively between endpoints on the internet.

| **Method** | **Description**                                                                                                    |
| ---------- | ------------------------------------------------------------------------------------------------------------------ |
| `INVITE`   | Initiates a session or invites another endpoint to participate.                                                    |
| `ACK`      | Confirms the receipt of an INVITE request.                                                                         |
| `BYE`      | Terminate a session.                                                                                               |
| `CANCEL`   | Cancels a pending INVITE request.                                                                                  |
| `REGISTER` | Registers a SIP user agent (UA) with a SIP server.                                                                 |
| `OPTIONS`  | Requests information about the capabilities of a SIP server or user agent, such as the types of media it supports. |
