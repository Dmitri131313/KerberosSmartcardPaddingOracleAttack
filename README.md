# KerberosSmartcardPaddingOracleAttack


The Kerberos protocol is used by millions of users and net-
work administrators worldwide for secure authentication, key
distribution, and access control management to enterprise networks and services. Since its initial public deployment in
1989, the protocol has undergone many revisions to incorporate new cryptographic primitives and improve security.
For example, initially based solely on users’ passwords and
symmetric cryptographic primitives, current implementations
also support smartcard-based authentication with asymmetric cryptographic primitives for improved security. However,
this iterative revision process has resulted in implementations
riddled with legacy crypto primitives and protocol designs.
In this work, we show how we can exploit this legacy crypto
to completely break the security of the enterprise network.
Firstly, while arguably more secure, smartcard-based authentication uses RSA encryption with the notorious PKCS #1 v1.5
padding scheme. Although the RSA decryption is done securely inside the smartcard, a non-constant time unpadding
code runs on the client’s CPU. This makes both Windows’s
and several Linux distributions’ implementations vulnerable
to the Bleichenbacher attack that can recover cryptographic
session tokens. Secondly, we show that the RSA smartcard based authentication does not provide forward secrecy to the
cryptographic tokens that the server provisions to the client.
Thirdly, we propose and analyze different algorithmic approaches to minimize the overhead required to handle noisy
oracles in the Bleichenbacher attack. This general Bleichenbacher attack analysis may be of independent interest.
Finally, we demonstrate microarchitectural side channel-
based end-to-end attacks on the Windows Kerberos implementation. We start by showing how to recover tokens used
to encrypt session transferred remote files by Samba. We then
show how to amplify the number of decryptions performed
with a single user’s PIN code input, allowing us to accelerate
our attack and recover users’ (and admins’) credentials before
expiration. In addition, we describe a remote attack vector
that allows us to perform the attack and generate queries.
