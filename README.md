# Pizza Challenge

The two halves of the Bassment Pizza Challenge:

* **Pizza Referee** — a Dalamud plugin that referees in game: calls each round, judges the
  `/random` rolls, walks the queue, shouts the send-off and the win, and talks to the tracker.
* **Pizza Tracker** — the Windows desktop app that is the book of record: payments, wins,
  the deposit figure, players and history.

Both are made for one venue and shout in chat on your behalf, which is why the plugin lives
here and not on the official plugin list.

## Install the plugin (once)

1. In game: `/xlsettings` → **Experimental** → *Custom Plugin Repositories* → paste

       https://raw.githubusercontent.com/donovangst/pizza-challenge/main/repo.json

   press **+**, then **Save and Close**.
2. `/xlplugins` → search **Pizza Referee** → Install. Updates arrive through the installer like
   any other plugin.
3. `/pizzaref` opens the overlay. `/pizzaref help` lists the commands.

First time, run it dry: `/pizzaref dry on`, `/pizzaref add target 2` (targeting yourself),
`/pizzaref start`, `/random` a few times, `/pizzaref abort`, `/pizzaref dry off`.
Then Settings → Wins → set who gets the `/tell` on a win (target them and press the button).

## Install the tracker (optional)

Grab **Pizza.Tracker.Setup.1.12.1.exe** from the [latest release](https://github.com/donovangst/pizza-challenge/releases/latest)
and run it — per-user, no admin. If you already have it, the much smaller
**Pizza.Tracker.Update.1.12.1.zip** in the same release swaps in the new version
(unzip, run *Update Pizza Tracker.bat*). When both are open on the same PC they link
by themselves: payments logged in the tracker queue pies in game, wins go back.

## One referee per table

If two hosts both run the plugin at the same table, both will shout. Whoever is
refereeing runs it; the other leaves theirs idle.

## House rules the plugin enforces

440 or higher eats a slice; 439 or below ends the round. 0 counts as 1000. The very first roll
of a round landing exactly on 440 wins the round outright. Only a plain `/random` counts —
never `/dice` or `/random <number>`. A roll made before the ROUND call still counts, and a
roll made straight after a lost round counts for the next one.

When a gil trade completes, the plugin offers to log it (*Log 10 pies* on the overlay or
`/pizzaref trade`) — it never logs a trade by itself. Adding the same name twice within 20
seconds is held as a slip until you confirm. If someone else at the table yells your ROUND
line, you get a warning: two referees means two sets of shouts.

Typed a name wrong? When the real character rolls, the overlay shows *"Will'ow Smith rolled
600 - not a name on Willow's entry"* with a **That's Willow** button; `/pizzaref bind` does the
same. The rolls that were ignored are judged on the spot, in order.

_Plugin 0.8.1 · Tracker 1.12.1_
