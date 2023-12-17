#ICC Cricket World Cup 2023 Data Analysis using SQL

https://www.kaggle.com/datasets/jdaustralia/icc-cwc23-all-innings-cleaned/versions/11?resource=download

The Analysis includes
1. Data Exploration
2. Data cleaning
3. Analysis and Insights

Data Exploration

Issued found
1.The player table had values as V Kohli(IND) which was not needed as there is a seperate column for the team.
2. Column 4s,6s,sr(strike rate) had datatype of nvarchar which would make operations such as sum() difficult to perform.

Data Cleaning
1. The code below would solve the player column issue as mentioned in the data exploration section
update [sql].[dbo].[CWC23_all_innings$]
set player=TRIM(SUBSTRING(player, 1, CHARINDEX('(', player) - 1))
WHERE CHARINDEX('(', player) > 0;

2. The below code will change the datatype of columns 4s,6s and sr to float from nvarchar.

alter table [sql].[dbo].[CWC23_all_innings$]
alter column [4s] float

alter table [sql].[dbo].[CWC23_all_innings$]
alter column [6s] float

alter table [sql].[dbo].[CWC23_all_innings$]
alter column sr float

Analysis
1.
