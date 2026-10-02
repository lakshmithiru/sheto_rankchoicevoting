# Ranked Choice Voting

Ranked choice voting (RCV) lets each voter order candidates by preference. A single-winner count uses those rankings to elect the candidate who holds a majority of the ballots that are still active.

## How a ballot works

A voter ranks as many candidates as they want. A lower number is a stronger preference.

| Rank | Candidate |
| ---- | --------- |
| 1    | Avery     |
| 2    | Blake     |
| 3    | Casey     |

Later ranks may be left blank. A ballot drops out of the count when every candidate it ranks has been eliminated.

## How the count works

A single-winner election uses instant-runoff voting:

1. Count each ballot for the highest-ranked candidate who is still in the race.
2. If one candidate has more than half of the continuing ballots, that candidate wins.
3. Otherwise, eliminate the candidate with the fewest votes.
4. Move each ballot from the eliminated candidate to the next ranked candidate who is still in the race.
5. Repeat until a candidate has a majority, or only one candidate remains.

A ballot is **exhausted** when it has no ranked candidate left in the race. Exhausted ballots leave the active total. The majority is more than half of the ballots that are still continuing.

When two or more candidates tie for last place, the election needs a published tie-break, such as a predetermined order or a draw.

## Example

Five voters and three candidates. A majority of five continuing ballots is three votes.

| Ballots | 1st    | 2nd    | 3rd    |
| ------- | ------ | ------ | ------ |
| 2       | Avery  | Blake  | Casey  |
| 2       | Blake  | Avery  | Casey  |
| 1       | Casey  | Avery  | Blake  |

**Round 1.** Avery 2, Blake 2, Casey 1. Nobody has a majority, so Casey is eliminated.

**Round 2.** Casey's ballot moves to Avery. Avery 3, Blake 2. Avery has a majority and wins.

## What the rankings change

- A winner must reach a majority of continuing ballots, so a first-place plurality is not enough on its own.
- A voter can rank a first choice and still have a later choice count if that first choice is eliminated.
- The result answers who survives elimination with majority support, which can differ from who led on first-place votes alone.

## Related names

| Name                         | Usual meaning                                                                                                      |
| ---------------------------- | ------------------------------------------------------------------------------------------------------------------ |
| Ranked choice voting (RCV)   | Methods that elect from ranked ballots                                                                             |
| Instant-runoff voting (IRV)  | The single-winner procedure above                                                                                  |
| Single transferable vote     | A multi-winner count that also transfers surplus votes from candidates who have already won a seat                 |
| Preferential voting          | A broader name, used in some countries, for elections that take a ranked ballot                                   |

## Multi-winner elections

Electing several seats at once usually uses the single transferable vote. Each winner needs a quota, often the Droop quota:

```text
floor(ballots / (seats + 1)) + 1
```

Votes above that quota transfer onward at a reduced value. Candidates who fall short are eliminated, and their ballots transfer, until every seat is filled. The walkthrough in this README is the single-winner case.
