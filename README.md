# CS Team Name Generator

Generate names of activity, homework, or project teams in your computer science course.

There are many team name generators that generate random team names as _adjective-noun_. They typically use animals as nouns or have other themes, e.g. sports. These are great!

For my CS course, I wanted more CS themed names. `names.txt` contains 2 columns, one each for adjectives and nouns, all CS-themed. Each column has a heading and its entries are sorted alphabetically. All entries are in lower case. The columns are separated by a _tab_ character for easy copy-pasting into a Google sheet.

If have read this far, you are probably a CS instructor looking for team names for your course. You are smart and know how to take it forward from here. But you are probably also exhausted. Some explanation is provided below just in case.

## How to use

To generate a team name, pick a random entry from each column in `names.txt` and pair them, e.g. "circular" and "exponents" leading to "circular exponents". You can do this manually but if you want to generate multiple names, you probably need some programmatic help!

### Google Sheets

Suppose that the Adjectives and Nouns columns are in columns A and B in your sheet. Pasting the following formula in any cell outside those columns will yield a random name.
```
=join("-", index($A$2:$A,RANDBETWEEN(1,counta($A$2:$A))), index($B$2:$B,RANDBETWEEN(1,counta($B$2:$B))))
```
You can paste this formula in as many cells as desired. You should get a new name each time but because selection is random, some names may repeat. You can check for repetition using the `COUNTUNIQUE` formula in Google Sheets.

### Python program

The accompanying python script, `TODO.py`, will generate the desired number of names for you.

## Issues
It is important to understand some issues with the generated names. Some of these arise from our choice of adjectives and nouns, and some spring from the algorithm.

- noun or adjective, e.g. data
- singular or plural
- strange names, data-data
- repetition and birthday paradox

## Contribute
