# KickPredict Project Plan

## Resources

1. Team
2. Match
3. Prediction

## Relationships

### Team <-> Match

One team can play many matches.

Each match contains:

- one home team
- one away team

The `match` table stores:

- `home_team_id`
- `away_team_id`

Both are foreign keys referring to `team.id`.

### Match <-> Prediction

One match can have many predictions.

Each prediction belongs to one match.

The `prediction` table stores:

- `match_id`

This is a foreign key referring to `match.id`.

## Database Design

### team

| Column | Type | Description |
|---|---|---|
| id | INTEGER | Primary key |
| country | TEXT | Country name |
| group_name | TEXT | World Cup group |
| coach | TEXT | Coach name |

### match

| Column | Type | Description |
|---|---|---|
| id | INTEGER | Primary key |
| home_team_id | INTEGER | Refers to team.id |
| away_team_id | INTEGER | Refers to team.id |
| match_date | TEXT | Date of the match |
| stadium | TEXT | Stadium name |
| home_score | INTEGER | Home team score |
| away_score | INTEGER | Away team score |
| status | TEXT | scheduled, finished, cancelled |

### prediction

| Column | Type | Description |
|---|---|---|
| id | INTEGER | Primary key |
| match_id | INTEGER | Refers to match.id |
| username | TEXT | Name of the person predicting |
| predicted_home_score | INTEGER | Predicted score for home team |
| predicted_away_score | INTEGER | Predicted score for away team |
| created_at | TEXT | Date prediction was created |