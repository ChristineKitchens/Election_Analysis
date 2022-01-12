# Election Analysis

## Overview of Election Audit
A Colorado Board of Elections employee issued the following tasks to complete the election audit of a recent local congressional election.

1. Calculate the total number of votes cast.
2. Get a complete list of the candidates who received votes
3. Calculate the total number of votes each candidate received
4. Calculate the percentage of votes each candidate won.
5. Determine the winner of the election based on the popular vote.

## Election-Audit Results

### Total Voter Turnout
- There were 369,711 votes cast in the election

### County Turnout
- Records indicate counties had the following turnout:
| County  | Percentage of Votes | Total Votes |
| ------------- | ------------- | ------------- |
| Jefferson | 10.5% | 38,855 |
| Denver | 82.8% | 306,055 |
| Arapahoe | 6.7% | 24,801 |

- Largest County Turnout: <b>Denver</b>
### Candidate Results  
- The candidates were:
  - Charles Casper Stockham
  - Diana DeGette
  - Raymon Anthony Doane

- The candidate results were:

| Candidate  | Percentage of Votes | Total Votes |
| ------------- | ------------- | ------------- |
| Charles Casper Stockham  | 23.0%  | 85,213 |
| Diana DeGette  | 73.8%  | 272,892 |
| Raymon Anthony Doane  | 3.1%  | 11,606 |

- The winner of the election was:
  - <b>Diana DeGette</b>, who received 73.8% of the vote and 272,892 number of votes

## Election-Audit Summary
- While analyses were conducted using voter data from a local congressional election, the script has the potential to be modified for use with any election. For example, to modify for state elections with multiple party candidates, a series of if/for statements structurally identical to those for the candidate and county analyses could be added to analyze the split of voters across party lines. Another example might be for elections for where more than one candidate can when an election (e.g. a school board with 10 candidates and 3 open positions). In this case, one could add the following code to the end of the script to obtain the top 3 candidates:
- #Add additional dependency at top of script
- import heapq
- #Add statement after "Print winning candidate summary" at end of code to obtain the top 3 candidate names
- print(heapq.nlargest(3, candidate_votes, key=candidate_votes.get))

## Resources
- Data Source: [election_results.csv](Resources\election_results.csv).
- Software: Python 3.6.1, Visual Studio Code, 1.38.1


The following parameters are included in the election_results.csv:

- **Ballot ID**: unique number for each ballot
- **County**: county ballot was cast in
- **Candidate**: candidate selected by voter
