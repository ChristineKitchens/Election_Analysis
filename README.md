# Election Analysis

## Overview of Election Audit
A Colorado Board of Elections employee issued the following tasks to complete the election audit of a recent local congressional election:

1. Calculate the total number of votes cast.
2. Calculate the voter turnout for each county.
3. Calculate the percentage of votes from each county out of the total count.
4. Determine the county with the highest turnout.
5. Get a complete list of the candidates who received votes.
6. Calculate the total number of votes each candidate received.
7. Calculate the percentage of votes each candidate won.
8. Determine the winner of the election based on the popular vote.

The [deliverable script](PyPoll_Challenge.py) prints the requested information to the command line as well as to a [separate text file](Resources\election_results.csv).

## Election-Audit Results

### Total Voter Turnout
- There were 369,711 votes cast in the election

### County Turnout
- Largest County Turnout: ***Denver***
- Summary data for voter turnout by county are listed below:

| County  | Percentage of Votes | Total Votes |
| ------------- | ------------- | ------------- |
| Jefferson | 10.5% | 38,855 |
| Denver | 82.8% | 306,055 |
| Arapahoe | 6.7% | 24,801 |


### Candidate Results  
- Candidates that received votes included:
  - Charles Casper Stockham
  - Diana DeGette
  - Raymon Anthony Doane
- The winner of the election is ***Diana DeGette***, who received 73.8% of the vote and 272,892 number of votes
- A summary of candidate results are listed below:

| Candidate  | Percentage of Votes | Total Votes |
| ------------- | ------------- | ------------- |
| Charles Casper Stockham  | 23.0%  | 85,213 |
| Diana DeGette  | 73.8%  | 272,892 |
| Raymon Anthony Doane  | 3.1%  | 11,606 |

## Election-Audit Summary
- While analyses were conducted using voter data from a local congressional election, the script has the potential to be modified for use with any election. 
- For example, to modify for state elections with multiple party candidates, a series of if/for statements structurally identical to those for the candidate and county analyses could be added to analyze the split of voters across party lines. Below are examples of existing script that has only had the candidate variable names updated to reflect party names instead:
```
# Create a party list and party votes dictionary.
party_options = []
party_votes = {}
```
```
# Read the csv and convert it into a list of dictionaries
with open(file_to_load) as election_data:
    reader = csv.reader(election_data)

    # Read the header
    header = next(reader)

    # For each row in the CSV file.
    for row in reader:
              
        # Extract the party name from each row.
        party_name = row[4]

        # If the party does not match any existing party, add it to
        # the party list
        if party_name not in party_options:

            # Add the candidate name to the candidate list.
            party_options.append(party_name)

            # And begin tracking that candidate's voter count.
            candidate_votes[candidate_name] = 0

        # Add a vote to that party's count
        party_votes[party_name] += 1
```
- Another example might be for elections for where more than one candidate can when an election (e.g. a school board with 10 candidates and 3 open positions). In this case, one could add the following code to the end of the script to obtain the top 3 candidates:
```
#Add additional dependency at top of script
import heapq
```
```
#Add statement after "Print winning candidate summary" at end of script to obtain the top 3 candidate names
print(heapq.nlargest(3, candidate_votes, key=candidate_votes.get))
```

## Resources
- Data Source: [election_results.csv](Resources\election_results.csv)
- Script: [PyPoll_Challenge](PyPoll_Challenge.py)
- Software: Python 3.6.1, Visual Studio Code, 1.38.1


- The following parameters are included in the election_results.csv:

  - **Ballot ID**: unique number for each ballot
  - **County**: county ballot was cast in
  - **Candidate**: candidate selected by voter
