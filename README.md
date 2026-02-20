# openwire-boundary-proof
Cryptographic provenance and boundary verification for Simforia OpenWire OSINT Ops.
## Authorship & Provenance Verification

This repository includes a cryptographically signed boundary declaration establishing authorship for Simforia OpenWire OSINT intellectual property.

To verify:

cd proof

ssh-keygen -Y verify \
  -f allowed_signers \
  -I openwire \
  -n file \
  -s simforia-boundary-v2.txt.sig < simforia-boundary-v2.txt

Expected result:

Good "file" signature for openwire

To verify (PowerShell):

Get-Content simforia-boundary-v2.txt -Raw |
ssh-keygen -Y verify `
  -f allowed_signers `
  -I openwire `
  -n file `
  -s simforia-boundary-v2.txt.sig
