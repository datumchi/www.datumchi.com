Introduction and Use Cases
=============================================

--------------------------
Overview & Guiding Pillars
--------------------------



The DatumChi Protocol attempts to solve the problem of secure, private, distributed messaging using a federated, decentralized identity system coupled with a data collaboration model that ensures consistency between all the participants with, or without, the use of public consensus systems such as traditional Blockchains.

The DatumChi Protocol's "Guiding Pillars" are:

* Provide an open, free, and easy to understand protocol that allows any protocol-compliant nodes to participate
* Provide local control of the node, including whether the node interacts with the general public or only with select few participants, but strong incentives to participate within a larger ecosystem
* Encourage the creation of applications which work off of data ordered and confirmed using distributed technology
* Integration means diversification. Don't assume anything about potential integrations.
* Encourage a democratic governance process that is transparent, allows for evolution, and allows for succession



-------------------------------------------
Reference Implementation & Compliance Tests
-------------------------------------------

To bootstrap usage of the protocol, we've created reference implementations of the protocol, and some compliance tests that can be used to ensure compliance of the protocol for other implementations. Both the reference implementation(s) and the compliance tests are completely free for anyone to use.

The DatumChi Protocol Reference Implementations currently consist of:

* DatumChi Protocol Identity Service, a Golang-based implementation of the DatumChi Identity Service endpoints
* DatumChi Protocol Collaboration Service, a Golang-based implementation of the DatumChi Collaboration Service endpoints
* DatumChi Protocol Tools, a suite of small utility tools that help anyone interact with the Protocol
* For testing the reference implementations, there exists tests to ensure compliance with the protocol. These should also help any other developer who wants to build an implementation of the protocol using the platform and language of their choice:
* DatumChi Protocol Tests, a suite of tests that use Ginkgo to ensure compliance with the DatumChi Protocol


---------------------------------------------
Use of Existing Infrastructure where Possible
---------------------------------------------

The FairX Protocol attempts to use existing robust infrastructure to accomplish its goals instead of trying to re-create the world. To that end:

* Domain Nodes are specified in the best distributed registry on the planet: DNS
* Communication between nodes uses a well-known, established, and efficient data encoding package (protobufs) along with an open source TLS-enabled RPC standard for secure node-device-node communication (gRPC). This means Websockets over HTTP/2 using standard SSL/TLS certificates for secure communication.


---------------------------------------------
Example Use Cases
---------------------------------------------

* Distributed Invoicing and Billing with Integrations with Traditional and Crypto payments
* Decentralized Social Networking
* Passwordless Login Systems
* The orchestration of executable contracts between participants


---------------------------------------------
Project Inspirations
---------------------------------------------

^^^^^^^^^^^
R3's Corda
^^^^^^^^^^^

Also "not a blockchain," I always felt RGB had the right architectural sense for where the real problems existed, and Corda is an excellent product
Corda handles data privacy and delivery in a manner that makes compliance with i.e. GDPR a breeze.

I do have some philosophical issues with two fundamental parts of Corda: its chosen language (Kotlin) and the JVM in general, and the UTXO data model as a primitive data structure.

I also feel that integration with Corda is clumsy, with operations equally clumsy.

^^^^^^^^^^^^^^^^^^^
Hyperledger Fabric
^^^^^^^^^^^^^^^^^^^

* The DatumChi Protocol borrows heavily from Fabric's use of the ordering service to order data change events, with endorsement by participating nodes part of the protocol
* Fabric relies too much on the client orchestrating consensus activities such as transaction endorsements and ordering
* Fabric is a bear to set up, and has a terrible privacy construct in the form of channels and private data collections
* Fabric is basically an IBM product. I know they don't want it to be. But it is.


^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
Stellar's Federated Identity
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Stellar is a distributed ledger system which uses a unique consensus algorithm that achieves finality in 3-5 seconds (though, there are some gotchas)
It uses a federation protocol in order to map a user string (such as "alice@alpha.com") to a Stellar ledger address (such as "GA3EIUB26VTYNMM42Z6PBPUDEI3A73UCLWXBB7B4T2EOZZUOQ65OMHZC")

FairX Protocol borrows heavily against this idea, while allowing for identity-to-identity attestation of attributes, the open attribute policy with standards, and strong integration with the data collaboration system instead of just serving a mapping to an address
