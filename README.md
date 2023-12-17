# ICC Cricket World Cup 2023 Data Analysis using SQL

https://www.kaggle.com/datasets/jdaustralia/icc-cwc23-all-innings-cleaned/versions/11?resource=download

# The Analysis includes
1. Data Exploration
2. Data cleaning
3. Analysis and Insights

# Data Exploration

Issued found
1.The player table had values as V Kohli(IND) which was not needed as there is a seperate column for the team.
2. Column 4s,6s,sr(strike rate) had datatype of nvarchar which would make operations such as sum() difficult to perform.

# Data Cleaning
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

# Analysis and Insights
## 1.Player with most runs

![image](https://github.com/HarshitaPandey08/SQL/assets/53274845/99c06e06-33ea-40df-a70e-e7cfa8a964b0)

![image](https://github.com/HarshitaPandey08/SQL/assets/53274845/a6ac4370-366c-4c9a-a2df-e9158c6dd7d9)

## 2.player with most wickets

![image](https://github.com/HarshitaPandey08/SQL/assets/53274845/21288070-a2d7-4e2e-a342-0dbab3d7a7f8)

![image](https://github.com/HarshitaPandey08/SQL/assets/53274845/cab292df-c013-4fe7-901b-0d096a01db5a)


## 3.player with most 6s

![image](https://github.com/HarshitaPandey08/SQL/assets/53274845/2b3da887-b1fa-48f6-818d-cc26c4031fe5)

![image](https://github.com/HarshitaPandey08/SQL/assets/53274845/56120681-4d67-4675-8ccc-97a87bf39126)


## 4.player with 4s

![image](https://github.com/HarshitaPandey08/SQL/assets/53274845/84e83803-3b19-4edd-9fed-4d93d42e43e4)

![image](https://github.com/HarshitaPandey08/SQL/assets/53274845/c7a524ba-783d-44b1-bc65-3c88dafcf7dc)


## 5.best strike rate

![image](https://github.com/HarshitaPandey08/SQL/assets/53274845/fed8d5f6-e28b-4fb2-8e4d-0f9afa840e5c)

![image](https://github.com/HarshitaPandey08/SQL/assets/53274845/a206d302-774e-476e-845d-958ef8874ccc)


## 6.ground with most and least runs

![image](https://github.com/HarshitaPandey08/SQL/assets/53274845/d624aaf5-d42c-4678-8975-556062ba531b)

![image](https://github.com/HarshitaPandey08/SQL/assets/53274845/af1fe8ce-7ef9-471e-8d2b-4f9502826c10)


## 7.team with most and least cumulative runs

![image](https://github.com/HarshitaPandey08/SQL/assets/53274845/7bfa939b-0c33-4e2b-9781-97e13f568e40)

![image](https://github.com/HarshitaPandey08/SQL/assets/53274845/453f9e0b-7680-482d-8288-f385bbfa2e49)


## 8.ground with most and least wickets 

![image](https://github.com/HarshitaPandey08/SQL/assets/53274845/c09c4f3e-9086-4b04-810a-72e615a5e7cb)

![image](https://github.com/HarshitaPandey08/SQL/assets/53274845/6b3f75de-f797-4638-8599-24f0a07a7bd2)


## 9.team with most and leat cumulative wkts

![image](https://github.com/HarshitaPandey08/SQL/assets/53274845/350d37e7-351f-4e09-989e-d416e94022be)

![image](https://github.com/HarshitaPandey08/SQL/assets/53274845/54acf31c-e083-435b-8bad-caa5f023b006)


## 10.player with best economy

![image](https://github.com/HarshitaPandey08/SQL/assets/53274845/0da41561-cf89-45ff-9ab2-4cd1b44d992b)

![image](https://github.com/HarshitaPandey08/SQL/assets/53274845/0a2b0a4f-9782-4ec2-bd57-b0db953f1a06)




