# proto_mini-intern-server-project

Shared Protobuf schemas for the mini game client and server.

## Layout

- `game/app/`: request and response contracts.
- `game/model/`: shared data models.
- `game/blueprint/`: shop configuration schema.
- `game/error.proto`: shared business error response.

## Using a revision

Use a full commit SHA to pin a schema snapshot in Proto Studio or in a consumer submodule.
All `.proto` files belong to the same revision.
Keep the `game/` directory structure intact so imports resolve.

## Editing and export

Load this repository and a commit SHA in Proto Studio, edit through forms, review the source diff, and export the complete schema tree as a ZIP.
Review and commit exported changes manually, then update client and server to the same revision and regenerate their Protobuf code.
Generated code, runtime configuration, and credentials do not belong in this repository.
