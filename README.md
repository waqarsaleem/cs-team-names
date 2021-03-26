# CS Team Name Generator

Generate names of activity, homework, or project teams in your computer science course.

There are many team name generators that generate random team names as _adjective-noun_. They typically use animals as nouns or have other themes, e.g. sports. These are great!

For my CS course, I wanted more CS themed names. [names.txt](names.txt) contains 2 columns, one each for adjectives and nouns, all CS-themed. Each column has a heading and its entries are sorted alphabetically. All entries are in lower case. The columns are separated by a _tab_ character for easy copy-pasting into a Google sheet.

If have read this far, you are probably a CS instructor looking for team names for your course. You are smart and know how to take it forward from here. But you are probably also exhausted. Some explanation is provided below just in case.

## How to use

To generate a team name, pick a random entry from each column in [names.txt](names.txt) and pair them, e.g. "circular" and "exponents" leading to "circular exponents". You can do this manually but if you want to generate multiple names, you probably need some programmatic help!

### Google Sheets

Suppose that the Adjectives and Nouns columns are in columns A and B in your sheet. Pasting the following formula in any cell outside those columns will yield a random name.
```
=join("-", index($A$2:$A,RANDBETWEEN(1,counta($A$2:$A))), index($B$2:$B,RANDBETWEEN(1,counta($B$2:$B))))
```
You can paste this formula in as many cells as desired. You should get a new name each time but because selection is random, some names may repeat. You can check for repetition using the `COUNTUNIQUE` formula in Google Sheets.

### Python program

The accompanying python script, `TODO.py`, will generate the desired number of names for you.

## Issues
It is important to be aware of some issues with the generated names and how to work around them. Some of the issues arise from our choice of adjectives and nouns, and some spring from the algorithm.

- Some words appear in both lists, e.g. "data". "data" can be thought of as an adjective when use in phrases like "data structures". Also using "data" as an adjective can lead to cool names, like "data pointers". However, it can also lead to strange names as "data data" or "recursive recursion". Always review the generated names and tweak them as necessary.
- Most nouns appear in the list in the plural form, e.g. "exponents" but some are singular, e.g. "recursion" or "pseudocode". This arises from the typical use of the noun. Always review the generated names and tweak them as necessary.
- Because you may be discarding some generated names, it is recommended to generate more names than required so that you are good even after throwing some out.
- The [product rule](https://en.wikipedia.org/wiki/Rule_of_product) gives us an upper limit on the number of unique names that can be generated with this list (above 2500 at the moment!). However, the [birthday paradox](https://en.wikipedia.org/wiki/Birthday_problem) tells us that we can start expecting repetitions with a far fewer number of names. I have not gotten around to working that number out just yet.

## Contribute
Contributions are welcome. You can contribute to the list of adjectives and nouns, or to other aspects, e.g. the documentation and code.
