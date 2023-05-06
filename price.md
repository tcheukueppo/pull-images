# GET POSSIBLE PRICES OF AN ARTICLE FROM AN HTML CONTENT

## ALGORITHMN

### DATA OUTPUT

### OVERALL PROCEDURE

#### OBVIOUS WAY WITH <article>

#### DEALING WITHOUT THE <article>

1. Iterate over tag having contents and try to match each tag's content against a regular expression
describing the price in your unit of interest (XAF, EURO, DOLLAR, ... etc.) and if its matches then
marked it.

2. For each marked tag, attempt to locate the most closest article name by executing
**in order** the following steps.

NOTE: Avoid the next steps if you successfully found your targeting article.

- Check the content of the tag itself to see if the name of your targeting article exists(Naive?) and
if so then we fill-in the record for the price found in the marked tag:

> 1. The extracted article name in the tag's content.
> 2. The precision of the extracted article name.
> 3. The distance between the extracted article's tag and the marked tags which is zero in this case.

- Without crossing marked tags, check the contents of its upper siblings followed by that of its lower
siblings. For each sense, starting from the closest to the farthest slibing and if you encounter your
targeting article, then stop there and fill-in the record for the price found in the marked tag:

> 1. The extracted article name in the content.
> 2. The precision of the extracted article name.
> 3. The number of tags separating the marked tag and the slibing whose content matches the targeting article.

- Well, if you've arrived here then that means the page in question might be for that of
an ecommerce website, so this is my logic(Makes sense?):

Note: Give up if you encounter another marked tag.

> 1. Go up to the parent tag
> 2. 

### GENERATING A REGULAR EXPRESSION FOR MATCHING ARTICLE NAMES

### MEASURE PRECISION OF THE EXTRACTED ARTICLE MATCHED BY THE REGEX

### PERL CODE

### EXAMPLES

### ANALYSIS

### CONCLUSION
