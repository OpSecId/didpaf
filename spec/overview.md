## Overview

The following is a `tl;dr` summary of how `did:paf` works:

The did syntax is `did:paf:<domain>:<uuid>`. A did document can optionally be resolved by the following translation: `https://paf.<domain>/<uuid>/did.json`. This is the same as a regular did:web transformation, except the pat subdomain is implicitly added to the domain value.

The resolved document MUST NOT contain any verification material. It MAY contain a list of services or any other metadata at the discretion of the did controller.

When an attestation is made with this did, it will display a `publicKeyMultibase` encoding of the public key used for signing the data as the did fragment: `did:paf:<domain>:<uuid>#<publicKeyMultibase>`.

When a verifier needs to verify this value, it can inject this as a Multikey verificationMethod in a did document. The verifier MAY resolve the did document through the web prior to injection, and append this verificationMethod to the fetched ressource, or simply derive a DID document from the fragment value, following similar rules to did:key.

A known fragments file is available at the location: `https://paf.<domain>/<uuid>/fragments.json`, which lists all authorized fragments. This file is used to link a specific fragment to a human readable use case. If the fragment isn't part of this file, a verifier might chose or not to consider it based on it's previous relations with the did. The fragments file SHOULD be signed by an authorized guardian.
