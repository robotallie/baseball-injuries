# There's No Crying in Baseball - Unless You Get an Injury
This repository contains datasets and analyses of baseball gamelogs and Disabled List data.

# Datasets
The data was scraped from two sources:
- `injuries.csv` : Injury data for seasons 2000 - 2016 was obtained from ProSportsTransasctions.com, and was reduced to only those being relinquished to the list, and does not include those who are being acquired back from the DL. (http://www.prosportstransactions.com/baseball/index.htm).
- `GL2000.TXT` - `GL2016.TXT` : Individual season game log data for seasons 2000 - 2016 was obtained from RetroSheet.org. The information used here was obtained free of charge from and is copyrighted by Retrosheet.  Interested parties may contact Retrosheet at "www.retrosheet.org".
- `TeamCurrentNames.csv` : Data connecting former and current team 3-letter abbreviations, regions, cities and nicknames, used in the game log data, used to merge the injury data with the game log data.
- `MLBPlayerIDs.csv`: Data containing the name and ids for all MLB players featured in the game logs, used to connect injured players to specific game logs where that player was in the starting lineup

## Injury Data: see `injury_data_scrape.ipynb` for the web-scraping from ProSportsTransactions.com
- Date - Date of placement on the Disabled List
- Relinquished - Name of Player
- DL_Length - Length of time spent on the Disabled List
- Injury_type - The type of injury if known

## Game Log Data:
 * 'date' - Date of the game 
 * 'num_game' - Number of the game of the series between two teams (0,1,2)
 * 'day' - Day of the week
 * 'v_team','v_league' - Visiting team's 3-letter abbreviation and league
 * 'h_team', 'h_league' - Home team's 3-letter abbreviation and league
 * 'v_team_game_num', 'h_team_game_num' - Game number for each team in the season
 * 'v_team_score','h_team_score' - Scores for home team and visiting team for that game
 * 'game_length_outs' 
 * 'day_night': Whether night or day, mostlly night: ('N': 29485, 'D':14242)
 * 'when_complete' - If the game was postponed, date the game was completed
 * 'forfeit' - Whether game was forfeited
 * 'protest' - Whether game was protested
 * 'park_id' - The park where the game was played
 * 'attendance' - Game attendance. 165 entries of '0' were filled in with the average park attendance
 * 'time_game_min' 
 * 'v_line_scores','h_line_scores' - Inning by inning scores
 * Visiting Team Stats:
   * 'v_at_bats','v_hits','v_doubles','v_triples','v_homeruns','v_RBI','v_sac_hits','v_sac_files','v_hit_pitch',
   * 'v_walks', 'v_int_walks', 'v_strikeouts', 'v_stol_base', 'v_caught_steal', 'v_grnd_dbl_plays', 
   * 'v_awd_fst_catch_intf', 'v_left_on_base','v_pitchers','v_ind_earn_runs','v_team_earn_runs',
   * 'v_wild_pitch','v_balks','v_putouts','v_assists','v_errors','v_pass_balls','v_dbl_plays', 
   * 'v_trp_plays'
 * Home Team Stats:
   * 'h_at_bats','h_hits','h_doubles', 'h_triples','h_homeruns', 'h_RBI','h_sac_hits',
   * 'h_sac_files','h_hit_pitch','h_walks', 'h_int_walks','h_strikeouts', 'h_stol_base',
   * 'h_caught_steal','h_grnd_dbl_plays', 'h_awd_fst_catch_intf','h_left_on_base',
   * 'h_pitchers','h_ind_earn_runs','h_team_earn_runs','h_wild_pitch','h_balks',
   * 'h_putouts','h_assists','h_errors','h_pass_balls','h_dbl_plays','h_trp_plays','
* Umpire, manager infro
   * h_plate_ump_id','h_plate_ump_name','first_b_ump_id','first_b_ump_name',
   * 'sec_b_ump_id','sec_b_ump_name','third_b_ump_id','third_b_ump_name', 
   * 'lf_ump_id','lf_ump_name','rf_ump_id','rf_ump_name',
   * 'v_mgr_id','v_mgr_name','h_mgr_id','h_mgr_name',
* Important players information
   * 'w_pitch_id','w_pitch"name','l_pitch_id','l_pitch_name','sv_pitch_id','sv_pitch_name',
   * 'game_win_rbi_bat_id','game_win_rbi_bat_name'
* Starting lineups for visiting and home team:
    * 'v_start_pitch_id','v_start_pitch_name', 'h_start_pitch_id', 'h_start_pitch_name', 
    * 'v_pl_1_id','v_pl_1_name', 'v_pl_1_pos','v_pl_2_id','v_pl_2_name', 'v_pl_2_pos',
    * 'v_pl_3_id','v_pl_3_name', 'v_pl_3_pos','v_pl_4_id','v_pl_4_name', 'v_pl_4_pos',
    * 'v_pl_5_id','v_pl_5_name', 'v_pl_5_pos','v_pl_6_id','v_pl_6_name', 'v_pl_6_pos',
    * 'v_pl_7_id','v_pl_7_name', 'v_pl_7_pos', 'v_pl_8_id','v_pl_8_name', 'v_pl_8_pos',
    * 'v_pl_9_id','v_pl_9_name', 'v_pl_9_pos',
    * 'h_pl_1_id','h_pl_1_name', 'h_pl_1_pos','h_pl_2_id','h_pl_2_name', 'h_pl_2_pos',
    * 'h_pl_3_id','h_pl_3_name', 'h_pl_3_pos','h_pl_4_id','h_pl_4_name', 'h_pl_4_pos',
    * 'h_pl_5_id','h_pl_5_name', 'h_pl_5_pos','h_pl_6_id','h_pl_6_name', 'h_pl_6_pos',
    * 'h_pl_7_id','h_pl_7_name', 'h_pl_7_pos','h_pl_8_id','h_pl_8_name', 'h_pl_8_pos',
    * 'h_pl_9_id','h_pl_9_name', 'h_pl_9_pos',
* 'addl_info' - Miscellaneous information
* 'table_acq_from' -Gamelog origination

# EDA for Injuries
* baseball-injury-predictions.ipynb

# EDA for Game Logs
* baseball-injury-prediction.ipynb

# Model Pipeline & Evaluation
