Authenticate Device
======================

.. image:: DeviceAuthentication.png

Device authentication allows for devices, or components outside of the scope of the DatumChi Protocol but **utilize** the DatumChi Protocol to create and manage collaborations, to authenticate themselves against their previously registered DeviceKey with a signature utilizing the corresponding private key.

=====  ===========
Step   Description
=====  ===========
1      Device creates a DeviceInfo data structure using its device public key and calls the identity services requesting a challenge
1.1    Identity service generates a challenge, and returns that back to the device
2      The Device combines the challenge returned by the Identity Service, concatenates the domain we're interacting with, and signs with the Device Private Key
3      The Device creates a DeviceInfo data structure, adds its Device Public Key and signature to the challenge, and sends to the Identity Service
3.1    The Identity Service verifies the signature in the DeviceInfo
3.2    If the signature checks out, generate an authentication token (JWT) for future calls
3.3    Return the AuthenticationToken to the Device
=====  ===========
