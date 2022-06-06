# ERC721

Currently Released ERC721 contracts and key functionality.

## GenFrens:
- Based largely on the Filaments & Blu3prints contracts by @abwagmi.
- Has single or double mint functionality w/ ERC721A for gas savings on double mints.

## SN0WCR4SH:
- Built on top of the GenFrens contract.
- Added a MerkleRoot for whitelist.
- Added a 'contributor' mint function that the owner could add addresses to post deploy.
- Added 'mintOgBatch' to allow the owner to airdrop the first X tokens to an array of addresses after deploy. 
- Also added a 'disallowIfStateIsChanging' modifier to avoid the potential for flashbot bundles to game the hash generation.


## Folded Faces:
- Built on top of the SN0WCR4SH contract.
- Streamlined the anonymice hash function to improve mint gas. Previously the whole hash was created and stored on mint. This approach instead stored a start hash and start nonce in the HashNeeds struct, which is then used to build the full hash in a view function when token buildHash is called internally by other functions. This caused ~33% gas savings for mints.

