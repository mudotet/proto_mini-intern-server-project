# proto_mini-intern-server-project

Shared Protobuf schemas for the mini game client and server.

## Layout

- `game/app/`: request and response contracts.
- `game/model/`: shared data models.
- `game/blueprint/`: shop and Battle Pass configuration schemas.
- `game/error.proto`: shared business error response.

## Using a revision

Use a full commit SHA to pin a schema snapshot in Proto Studio or in a consumer submodule.
All `.proto` files belong to the same revision.
Keep the `game/` directory structure intact so imports resolve.

## Editing and export

Load this repository and a commit SHA in Proto Studio, edit through forms, review the source diff, and export the complete schema tree as a ZIP.
Review and commit exported changes manually, then update client and server to the same revision and regenerate their Protobuf code.
Generated code, runtime configuration, and credentials do not belong in this repository.

## Battle Pass

`game/model/battle_pass.proto` defines one-of reward types, Hero rarity/ownership, and progress. `game/blueprint/battle_pass.proto` defines shared node, Hero, and schedule configuration. `game/app/battle_pass/` contains view, purchase, single-node claim, and demo Quest grant contracts. The Quest grant contract represents a trusted-system award; exposing client-selected EXP is not a production Quest implementation.
