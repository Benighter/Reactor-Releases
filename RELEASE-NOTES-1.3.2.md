# Reactor 1.3.2 — One more ripple

Online moves now start their normal placement and chain animation immediately, while the server confirms the move. The next turn and ranked result remain server-owned. Rejected moves restore the authoritative board, and delayed snapshots cannot undo a confirmed move.

- After a human online match, offer a rematch that every player must accept. The next arena keeps the same players, team seats, format, rated/friendly choice and clock, with fresh time banks. Repeat acceptance cannot create duplicate arenas.
- A declined or expired offer opens Find a New Match with the previous format and clock, plus a Main Menu action. Friendly games offer a fresh invitation room. Bot introductions still require disclosure and stay within the lifetime cap.
- The rated recap fills the progress bar from the match's saved points. A promotion fills the old tier, reveals the new GPT badge with a short cinematic transition, then shows progress toward the next rank. Losses, deranking and protection display the actual server result. Reduced motion shows the final state immediately.
- Fixed damaged punctuation in sign-in, account, friends and online screens.
- Opponent turns check for updates every 250 ms after the previous request completes. Your own turn uses a quieter interval. Requests never overlap, disconnected checks back off, and completed games stop idle polling.
- Active-match checks now use one bounded database call for membership, match and names. Presence writes are throttled and leaderboard ranks refresh when the match ends.
- Bot thinking time is now 550 ms, with bot requests held while a native move or chain animates.
- Retained all four formats, independent ladders, lower-rank protection, clocks, optional rated bot introductions, ten playable lessons, CC0 sounds and existing accounts and offline saves.

Validation: 34 local checks and 26 native regression/layout checks. Live native checks cover immediate placement, hash parity, stale replies, rejected-move recovery, a real winning bot chain and save isolation. A four-client live check completed rematches and declines in all four formats, preserved teams and clocks, rejected duplicate starts, and verified a real promotion and deranking. Phone/desktop result reviews cover promotion, deranking, two/three/four-player rematch offers and the retained matchmaking choices. Eight comparable live checks reduced median server round-trip time from 518 ms to 378 ms on this PC; connection conditions still affect delivery.

This is the direct Android beta (code 10), with the original package and signing identity. Android asks for installation approval. The classic Windows copy remains private and is updated locally. Google Play preparation continues separately with com.benighter.reactor, R10 once and no ads; this release does not claim Play availability.
