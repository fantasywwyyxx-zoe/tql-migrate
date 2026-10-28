# tql-migrate

Tokyo Quest Log — save migration page.

The game's canonical home moved from `fantasywwyyxx-zoe.github.io/tokyo-quest-log/`
to `https://tokyoquestlog.com`. Browser storage is per-origin, so saves written
under the old origin are stranded there. This page is hosted on the same
`fantasywwyyxx-zoe.github.io` origin (in its own repo, so the old repo's custom
domain redirect does not apply), reads the player's legacy local save, lets them
log in with the game's email-code auth (Supabase), merges old vs. cloud save
with the game's progress-first rule (level > EXP > clears > savedAt), and
uploads the winner to the `saves` table. The player then opens
tokyoquestlog.com, logs in with the same email, and the game downloads it.

The game links here from its login window （旧アドレスのセーブデータを取り込む）.
