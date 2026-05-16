# Known Limits

CANAL is promising, but the claims must stay precise.

## Do Not Claim

- unlimited context
- perfect recall
- magic memory
- compressed-domain attention
- support for every model on every machine
- public production security without normal deployment hardening

## Current Limits

1. **Model differences matter.**

   CANAL has been tested across several model families, but every model can
   still have its own behavior. New popular models need proof runs.

2. **Huge-context runs can be slow.**

   CANAL expands what can run locally. It does not make every 1M-token workflow
   instant on consumer hardware.

3. **Linux/CUDA is the current proof target.**

   Mac/Metal may be possible later, but it is not the main validated target
   yet.

4. **SSD mode is a narrower claim than RAM mode.**

   SSD spill safety has passed current tests. RAM-backed CANAL is the stronger
   current release claim.

5. **Document packs need clean source material.**

   If a document pack contains stale or conflicting facts, exact QA can retrieve
   the wrong historical claim.

6. **Binary preview is not a polished installer.**

   The first outside package is a controlled preview for technical local-model
   users.

