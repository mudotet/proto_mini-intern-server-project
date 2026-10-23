# Battle Pass API contracts

These source schemas are part of the separate schema Git repository at `server/src/main/proto` in the Java application checkout. The application repository records a submodule commit; its diff does not expand the individual schema files.

| File | Request | Response |
| --- | --- | --- |
| [battle_pass.proto](battle_pass.proto) | `BattlePassRequestProto` (empty; GET accepts no body) | `BattlePassResponseProto` |
| [battle_pass_purchase.proto](battle_pass_purchase.proto) | `BattlePassPurchaseRequestProto` | `BattlePassPurchaseResponseProto` |
| [battle_pass_claim.proto](battle_pass_claim.proto) | `BattlePassClaimRequestProto` | `BattlePassClaimResponseProto` |
| [battle_pass_quest_grant.proto](battle_pass_quest_grant.proto) | `BattlePassQuestGrantRequestProto` | `BattlePassQuestGrantResponseProto` |

Shared progress, Hero rarity, ownership, and the single-reward `oneof` are in [game/model/battle_pass.proto](../../model/battle_pass.proto). Shared node and schedule configuration is in [game/blueprint/battle_pass.proto](../../blueprint/battle_pass.proto).

Mutation requests identify the intended Battle Pass. The node-claim request adds `node_id`; the server chooses its reward from configuration. The demo-only Quest grant request adds `quest_id`, `grant_id`, and `exp_bp`. Player identity comes from the authenticated Session; HTTP mutations use `X-Request-Id` for retries.

Use the application Gradle wrapper to regenerate Java; generated classes are build output, not schema source. Inspect schema changes with `git -C server/src/main/proto log --oneline` from the application repository root.
