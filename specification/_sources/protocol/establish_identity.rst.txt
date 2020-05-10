Establish Identity
======================

.. image:: EstablishIdentity.png

Every single participant (as well as collaborations, bots, and the like) require an *Identity* to be established.  While each identity type is different, there are some standard templates available that make it easier for you to be attested by *Trusted Identity Attestors*.

=====  ===========
Step   Description
=====  ===========
1      Device (or user of the device) creates an Identity data structure
2      Identity attests to its own identity attributes using the Identity private key
3      Device calls EstablishIdentity, passing in an authentication token and an identity to establish
3.1    Identity Service should authenticate token, if required
3.2    Identity Service verifies attestations within the identity service
3.3    Identity Service stores the Identity
3.4    Identity Service returns an OK back to the Device
=====  ===========
