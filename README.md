# Election_Analysis

## Overview of Election Audit 
The purpose of this project is to analyze election data for the Colorado Board of Elections. During this process, I aimed to use the election data provided to breakdown votes by candidate, the winning candidate, and voter turnout based on county. In order to do so, I first had to organize the large amount of election data so that I could discern the number of individual candidates and counties. Then I was able to tally up votes per candidate and county, presenting the final data in overall count and by percentage. 

## Election-Audit Results
•	There were 369,711 total votes in the election, tallied up by a for statement that iterated through each row to count the votes.
'''
for row in reader:

        # Add to the total vote count
        total_votes = total_votes + 1
'''
•	County votes were broken down by for and if statements to tally up the votes by each of the three counties. 
'''
    for county_name in county_votes:
        cvotes = county_votes[county_name]
        cvote_percentage = float(cvotes) / float(total_votes) * 100
        county_results = (
            f"{county_name}: {cvote_percentage:.1f}% ({cvotes:,})\n")
  '''
  o	Jefferson County had 10.5% of the votes for a total of 38,855 votes
  o	Denver County had 82.8% of the votes for a total of 306,055 votes
  o	Arapahoe County had 6.7% of the votes for a total of 24,801 votes
  o	Denver had the largest voter turnout, taking a high majority of the votes 
•	Candidate votes were broken down in the same way, using for and if statements to tally up votes per candidate.
'''
for candidate_name in candidate_votes:
        votes = candidate_votes.get(candidate_name)
        vote_percentage = float(votes) / float(total_votes) * 100
        candidate_results = (
            f"{candidate_name}: {vote_percentage:.1f}% ({votes:,})\n")
'''
  o	Candidate Charles Casper Stockham received 23% of the votes (85,213 votes)
  o	Candidate Diana DeGette received 73.8% of the votes (272,892 votes)
  o	Candidate Raymon Anthony Doane received 3.1% of the votes (11,606 votes)
  o	These numbers put Diana Degette as the clear winner of the election with 73.8% of the total votes cast 
  
## Election-Audit Summary
The election script used for this project can be conveniently applied to any future election. The code used to tally up county votes and candidate votes can be generalized to other categories of data, such as party votes, state votes, or even country votes. Additional loops can be added to the code to tally up more than just two categories at a time. Rather than only counting votes by county and votes by candidate, we could easily add another loop to count votes by party or any other category as well. Using this simple code can make election auditing and analysis much quicker and more efficient by quickly sorting through large amounts of data to return the information needed. 
