# infinite-cincinnati-data

<https://infinitecincinnati.com>

This repo contains CSV data exported from Out of the Park Simulator
for each Infinite Cincinnati timeline.

Data was exported separately for each timeline by opening that timeline's
saved game and exporting database data as a CSV file. The CSV data from
each timeline was combined into a single CSV file by adding an extra
"timeline" column to the front of timeline-specific CSV data.

## `games.csv`

Contains information about the game's summary
(runs/hits/errors/innings) and other summary information.

Columns:

* `timeline`
* `game_id`
* `league_id`
* `home_team`
* `away_team`
* `attendance`
* `date`
* `time`
* `game_type`
* `played`
* `dh`
* `innings`
* `runs0`
* `runs1`
* `hits0`
* `hits1`
* `errors0`
* `errors1`
* `winning_pitcher`
* `losing_pitcher`
* `save_pitcher`
* `starter0`
* `starter1`

## `games_score.csv`

Contains more detailed manifest of runs scored,
inning by inning, for each timeline.

Columns:

* `timeline`
* `game_id`
* `team`
* `inning`
* `score`

## `players.csv`

Not timeline-specific. Other data files reference players by Player ID,
this file contains the map of Player ID to Player Name.

* `player_id`
* `team_id`
* `league_id`
* `position`
* `role`
* `first_name`
* `last_name`
* `nick_name`
* `age`
* `date_of_birth`
* `city_of_birth_id`
* `nation_id`
* `second_nation_id`
* `weight`
* `height`
* `retired`
* `free_agent`
* `last_league_id`
* `last_team_id`
* `organization_id`
* `last_organization_id`
* `language_ids0`
* `language_ids1`
* `uniform_number`
* `experience`
* `person_type`
* `bats`
* `throws`
* `personality_greed`
* `personality_loyalty`
* `personality_play_for_winner`
* `personality_work_ethic`
* `personality_intelligence`
* `personality_leader`
* `historical_id`
* `historical_team_id`
* `best_contract_offer_id`
* `injury_is_injured`
* `injury_dtd_injury`
* `injury_career_ending`
* `injury_dl_left`
* `injury_dl_playoff_round`
* `injury_left`
* `dtd_injury_effect`
* `injury_id`
* `prone_overall`
* `prone_leg`
* `prone_back`
* `prone_arm`
* `fatigue_pitches0`
* `fatigue_pitches1`
* `fatigue_pitches2`
* `fatigue_pitches3`
* `fatigue_pitches4`
* `fatigue_pitches5`
* `fatigue_points`
* `fatigue_played_today`
* `running_ratings_speed`
* `running_ratings_stealing`
* `running_ratings_baserunning`
* `college`
* `draft_year`
* `draft_round`
* `draft_supplemental`
* `draft_pick`
* `draft_overall_pick`
* `draft_eligible`
* `hidden`
* `draft_league_id`
* `draft_team_id`
* `turned_coach`
* `hall_of_fame`
* `rust`
* `inducted`
* `strategy_override_team`
* `strategy_stealing`
* `strategy_running`
* `strategy_bunt_for_hit`
* `strategy_sac_bunt`
* `strategy_hit_run`
* `strategy_hook_start`
* `strategy_hook_relief`
* `strategy_pitch_count`
* `strategy_pitch_around`
* `strategy_no_pinch_if_rested`
* `strategy_never_pinch_hit`
* `strategy_defensive_sub`
* `strategy_dtd_sit_min`
* `strategy_dtd_allow_ph`
* `local_pop`
* `national_pop`
* `draft_protected`
* `morale`
* `morale_player_performance`
* `morale_team_performance`
* `morale_team_transactions`
* `expectation`
* `morale_player_role`

## `players_at_bat_batting_stats.csv`

Contains a table of the pitcher, batter, and outcome of every
at-bat in the game, plus pitch information, launch velocity, etc.

* `timeline`
* `player_id`
* `game_id`
* `opponent_player_id`
* `team_id`
* `sac`
* `balls`
* `strikes`
* `result`
* `base1`
* `base2`
* `base3`
* `Close`
* `pinch`
* `inning`
* `run_diff`
* `outs`
* `sb`
* `cs`
* `rbi`
* `r`
* `spot`
* `hit_loc`
* `hit_xy`
* `exit_velo`
* `launch_angle`

## `players_game_batting.csv`

Contains a table of batting performance of each player
for the single exhibition game played in that timeline.

* `timeline`
* `player_id`
* `year`
* `team_id`
* `game_id`
* `league_id`
* `level_id`
* `split_id`
* `position`
* `ab`
* `h`
* `k`
* `pa`
* `pitches_seen`
* `g`
* `gs`
* `d`
* `t`
* `hr`
* `r`
* `rbi`
* `sb`
* `cs`
* `bb`
* `ibb`
* `gdp`
* `sh`
* `sf`
* `hp`
* `ci`
* `wpa`
* `stint`
* `ubr`


## `players_game_pitching_stats.csv`

Each row of this file cntains information about a pitcher's stats
from one particular Game 3 timeline.

* `timeline` - which timeline's Game 3 this stat comes from
* `player_id` - player id
* `year` - (ignore)
* `team_id` - (see teams df)
* `game_id` - (ignore)
* `league_id` - (ignore)
* `level_id` - (ignore)
* `split_id` - (ignore)
* `ip` - innings pitched
* `ab` - at bats
* `tb` - total bases
* `ha` - hits allowed
* `k` - strikeouts (**NOTE: THIS COLUMN IS NOT ACCURATE**)
* `bf` - batters faced
* `rs` - ??? (runs scored? seems to be same as `r`)
* `bb` - walk/base on balls
* `r` - runs
* `er` - earned runs
* `gb` - ground balls?
* `fb` - fly balls?
* `pi` - pitches?
* `ipf` - ??? (intentional pitchout first?)
* `g` - games?
* `gs` - games stared? grand slams?
* `w` - wins
* `l` - losses
* `s` - saves?
* `sa` - ??? (single against? stolen against?)
* `da` - ??? (double against?)
* `sh` - ??? (shutouts? what is SHO?)
* `sf` - ???
* `ta` - ??? (triple against?)
* `hra` - ??? (home run against?)
* `bk` - ??? (balk?)
* `ci` - ???
* `iw` - intentional walks
* `wp` - ??? (walks.......?)
* `hp` - ??? (hits.......?)
* `gf` - ???
* `dp` - double plays (?)
* `qs` - ???
* `svo` - save opportunities?
* `bs` - ???
* `ra` - ???
* `cg` - complete game(s) (?)
* `sho` - ??? (shutouts?)
* `sb` - stolen base(s) (by? against?)
* `cs` - caught stealing
* `hld` - ??? (ld = line drive...?)
* `ir` - inherited runs
* `irs` - iherited runs scored
* `wpa` - (WPA percent? walks per...?)
* `li` - ???
* `stint` - ???
* `outs` - ???

## `teams.csv`

Contains information about the two teams. Mainly useful
because the teams are referenced by Team ID in most files.
This file contains the Team ID to Team Name mapping.

* `team_id`
* `name`
* `abbr`
* `nickname`

rest of keys are irrelevant.
