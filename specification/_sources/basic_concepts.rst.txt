Basic Concepts of the DatumChi Protocol
=============================================


----------------
DatumChi Domain
----------------

A *Domain* in the DatumChi Protocol is the owner of a set of identities, collaborations, and related nodes created and managed using the DatumChi Protocol, and initially configured using the Domain Name System.

The Domain is uniquely identified by its "Domain Key," described below.


^^^^^^^^^^^^^^^^^^^^^^^^^
DNS Domain Configuration
^^^^^^^^^^^^^^^^^^^^^^^^^

The DatumChi Protocol relies on the internet's most robust directory service that exists for initial configuration of a DataumChi domain: DNS.

For the domain in which you want to run your DatumChi services, you must add the following DNS records:

* SRV - to define the identity and collaboration services for your node

  * For example: datumchiidentity.tcp.node.example.com. 86400 IN SRV 0 5 7717 node.example.com.
  * For example: datumchicollaboration.tcp.node.example.com. 86400 IN SRV 0 5 7707 node.example.com.

* TXT - to prove domain's ownership of a public key (the *"Domain Key"*)

  * datumchi_pubkey -> Gblahblahblah
  * datumchi_signature -> (signed sha256Hash(hostname) with privkey)

* Key Encoding: Ed25519 using base32 encoding
* Signature Encoding: Using base32 encoding (?)

----------------
Identities
----------------

* Addressing format: [name@gmail.com:/optional/path]datumchi.com

* Nodes have primary domain over their identities

----------------
Participant
----------------
* A participant, utilizing an Identity, creates Collaborations and Data States within them
* A participant utilizes the network through a Device

----------------
Collaborations
----------------

* Collaborations are activities between identities, where this collaboration requires identities to agree to some state, data, set of data, or etc


----------------
Data State
----------------

* A "data state" is a piece of data that two or more identities should agree to
* "Data states" will change over time, and "data states" may have attributes available to some parties in a collaboration
* Collaborations can change things over time ("Account Model"), or constantly retire and recreate things ("UTXO")

* Data States can have some standard attributes:

  * Originator address of the thing when first created
  * Required signatories of the thing - acceptance of the thing
