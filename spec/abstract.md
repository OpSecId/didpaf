## Abstract

The Pluggable Attestation Fragments DID Method is a combination of the simple self-resolveable nature of did:key and the ability to list services through did:web. It should be paired with an existing did method for narrowly scoped use cases. Features include:

- On demand generation of new keypairs, without the need to update the DID Document.
- The ability to list and link keypairs to use cases and identities implicitly.
- A pluggable approach, making it easy to implement this with any existing did method used by the implementer without disruption.
- A method to optionally enhance self-resolveable dids with provided services.
