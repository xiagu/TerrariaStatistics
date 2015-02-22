Description
===========
This mod provides basic statistics on each player as well as an encounter (boss or invasion) DPS meter. It can also be used to provide status updates of encounters. For instance, messages for Frost Moon will display the wave number, points until next wave, overall percentage of the encounter completed, time in minutes/seconds left of night, and percentage of night completed.

Versions
--------
* 1.0.6 - First on github
* 1.0.7 -
	+ Fixed spam on EoW
	+ Fixed issues with Probes & Leeches from the Destroyer & WoF after killed
	+ Added a safety check
* 1.0.8 -
	+ Added subscribing to bosses. Gives you continuous reports of how much time is left for night bosses.
	+ Only players who have done damage in Boss encounters see after battle message now.
	+ Fixed spam on Plantera (left over spores)
	+ Refactored all boss "children" to eliminate reporting new boss battles

Commands
--------
/stat [playername] - Display most stats on a player if name provided, or yourself by default.

    Includes: Kills, Damage done, Max Hit, Crits, Crit%, Damage received, MaxHit, Times Critted, Amount Healed, Times Healed, Mana Recovered, Times Mana Recovered

/stat playername crit|crits|critical - Display game's information on melee/magic/ranged crits.


/boss [previous number] - Displays last boss battle stats.

/battle [previous number] - Displays last invasion battle stats.

    Duration in minutes/seconds
    Last Hit - Who got the 'kill' and for how much damage.
    For each player that did damage
        Total Damage contributed
        Percentage of Damage contributed overall
        DPS (damage per second) calculated.
    [previous number] returns previous battle report instead of latest.


/bosses - Provides number of recorded boss battles in memory.

/bosses clear - Clears records of boss battles. Records infinite (based on RAM) so clearing might be needed


/invasion
/event - Reports the progress of the current invasion. This is automatically subscription based but you can type it in manually as well

    Goblin Army
        Distance away
        Time in seconds until Army arrives
        On Arrival:
            Goblins Killed
            Invasion Size
            Percent Completed (kills vs remaining)
            Kills Remaining (to 'defeat' army)
    Pumpkin Moon & Frost Moon
        Current Wave / Max Waves
        Current Points / Max Points (for next wave)
        Overall Event Completion Percent (getting to final wave)
        Time left until morning - in minutes and seconds and percent
        On Final Wave - Accumulated points (keeps counting), Time until morning

/events - Displays number of events recorded in memory

/events clear - Clears the recorded events from memory


/wave - Displays debug info: Wave Count and Wave Kills

/wave number - Sets the current wave to provided number. Allows skipping to final wave


/unsub [boss|invasion]
/unsubscribe [boss|invasion] - Unsubscribes a player from receiving continuous Event or Boss reports


/sub [boss|invasion]
/subscribe [boss|invasion] - Subscribes a player to automatically receive Event reports during invasions and bosses (see /event)


/tliteral - Displays debug info: integer value of the Game Time variable

/ttm - Displays the time until morning in minutes, seconds, and overall percentage completed

/ttn - Displays the time until night in minutes, seconds, and overall percentage completed.

Known Issues
------------
- Flagging an npc as a boss will not end the encounter until expired. This is due to the checking the "parent" id of bosses. Could add a command to fix this.
