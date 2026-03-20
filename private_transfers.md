
```sh
$ cd /tmp
$ git clone https://github.com/solana-foundation/solana-bootcamp-2026

$ cd /tmp/solana-bootcamp-2026/05-private-transfers/main/circuits/withdrawal
$ nargo compile
$ sunspot compile target/withdrawal.json
$ sunspot setup target/withdrawal.ccs
$ export GNARK_VERIFIER_BIN="/home/ubuntu/src/sunspot/gnark-solana/crates/verifier-bin"
$ sunspot deploy target/withdrawal.vk
$ solana program deploy target/withdrawal.so
# PROGRAM_ID = 584LUeBAc5FJxyU4K52wkN7Fdn8osPbP3B1F1sAms5Ew
# Replace it in the anchor/programs/private_transfers/src/lib.rs SUNSPOT_VERIFIER_ID
# Replace it in the anchor/Anchor.toml sunspot_verifier
# Replace it in the frontend/src/constants.ts SUNSPOT_VERIFIER_ID

# Change the url in anchor/package.json ANCHOR_PROVIDER_URL
# Change the url in backend/src/server.ts DEVNET_ENDPOINT
# Change the url in frontend/src/constants.ts DEVNET_ENDPOINT

$ cd /tmp/solana-bootcamp-2026/05-private-transfers/main/anchor
$ anchor keys sync
$ anchor build
$ anchor program deploy --provider.cluster localnet
# PROGRAM_ID = 9gEScV71ivuAKPbegpstbm9NRYf35muXEmGG4Ak6pePv
# Replace it in backend/src/server.ts PROGRAM_ID
$ bun run init-pool

$ cd /tmp/solana-bootcamp-2026/05-private-transfers/main/backend
$ bun install
$ bun run dev

$ cd /tmp/solana-bootcamp-2026/05-private-transfers/main/frontend
$ bun install
$ bun run dev
```
