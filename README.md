Hackathon Week 3
================

#Names

(Chris Wittenberg)[http://github.com/cwitty1919] (Ian Ker-Seymer)[http://github.com/ianks] 

#Part1


## 2a

```
sourcetype="github_events" type="PushEvent" | stats count by actor.login
```

![image](https://www.dropbox.com/s/pkg1m4e5x0djhes/Screenshot%202014-09-15%2019.09.32.png?dl=1)


## 2b
 
 ```
 sourcetype=hackdata | timechart count by type
 ```
 ![image](2b.png?raw=true)



## 2c

```
sourcetype=hack_events type=PullRequestEvent | stats count as Count by actor.login
```
## 2d
 
 ```
sourcetype="hackdata" | stats count(eval(type="PullRequestEvent")) as Count by payload.action
 ```
 ![image](2d.png?raw=true)

## 2e

```
sourcetype="github_events" type="PullRequestEvent" | stats count by actor.login
```
## 2f
 
 ```
sourcetype="hackdata" "repo.name"="CSCI-4830-002-2014/challenge-week-2" type="PullRequestEvent" | timechart count
 ```
 ![image](2f.png?raw=true)
![image](https://www.dropbox.com/s/fc9skwzrcg9lv9k/Screenshot%202014-09-15%2018.49.40.png?dl=1)

```
sourcetype=hackdata | timechart count by type
```

#Part 3
```
sourcetype=hack_events type=PushEvent | timechart count limit=30
```
Question: When did individuals push their changes?
![image](part3_1.png?raw=true)

```
sourcetype="hackdata" | timechart count(eval(type="PullRequestEvent")) by payload.action usenull=f
```
Question: What were the different actions performed on pull requests done over time?

![image](part3_2.png?raw=true)

```
sourcetype=hack_events type=IssuesEvent | chart count by actor.login
```
Question: Who created the most issues?

![image](part3_3.png?raw=true)