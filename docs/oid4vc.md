# DIDComm and OpenID for Verifiable Credentials

The [OpenID for Verifiable Credentials](https://openid.net/sg/openid4vc/) protocols are focused protocols that follow patterns familiar with uses of the OpenID family of specs. The OID4VC protocols for Issuance and Verification are capable of issuing and presenting credentials of a variety of formats. DIDComm Protocols work very well alongside OID4VC protocols, and we'll explain how.

## Verifiable Credentials
Both sets of protocols are credential type agnostic - they can issue or present credentials of any type. Further, these protocols are capable of presenting credentials issued via the other protocol. Credentials issued via [OID4VCI](https://openid.net/sg/openid4vc/specifications/) can be presented via [DIDComm PresentProof](applications/vc_tech_vertical.md), and vice versa.

In addition to cross presentation and issuance, OID4VC users can benefit from the other credential-related features DIDComm provides. DIDComm provides messaging from the Issuer (or Verifier) to the holder without prior interaction. This communication is secure and mobile-device friendly. This enables prompting user action necessary for issuance or presentation in situations where the user is not anticipating the need. DIDComm also has a Revocation Notification protocol that allows the Issuer to notify the Holder that an issued credential has been revoked. This can smooth a user experience and prevent the presentation of a revoked credential, or facilitate the reissuance of replacement.

DIDComm protocols exist for many features beyond Verifiable Credentials. The next section includes notes about [human oriented communication](applications/human_communication_tech_vertical.md), which can often be used in concert with VC protocols to explain credential or business process details using longer explanations.

## Human Communication

DIDComm has [protocols](applications/human_communication_tech_vertical.md) for Messaging, Question & Answer, and even a basic menu behavior. These protocols can augment the experience of Verifiable Credential exchange, but can also be used to leverage the trust gained from VC exchange into other activities. Sending notifications, checking confirmations, and asking questions are all things easily accomplished with existing protocols.

## All DIDComm Protocols

DIDComm Protocols are easy to create for any purpose. Secure interaction is easy to facilitate, and DIDComm protocols help supply that functionlity.

## What's required?

In order to turn an OID4VC interaction into a DIDComm connection, the OID4VC exchange must include a DID that contains a DIDComm service endpoint, or can be updated to include a DIDComm Service Endpoint. Ideally, both parties share their DID in the exchange, allowing either to initiate a DIDComm relationship.

And that's it. Knowing the other party's DID and resolving the DID Document to find the DIDComm Service Endpoint enables you to engage in any of the supported DIDComm Protocols, including presenting credentials and more.

