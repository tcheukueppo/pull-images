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

- Without crossing marked tags, check the content of each of its upper siblings from the closest
to the farthest one and if you encounter your targeting article, then stop there and fill-in
the record for the price found in the marked tag:

> 1. The extracted article name in the content.
> 2. The precision of the extracted article name.
> 3. A distance of zero between price and the extracted article.

- Well, if you've arrived here then that means the page in question might be for that of
an ecommerce website, so this is my logic(Makes sense?):

Note: Give up if you encounter another marked tag.

> 1. Move to the parent tag and check same as in - for it content.
> 2. If the previous step fails, do the same for the content of its upper slibing
> 3. 

### GENERATING A REGULAR EXPRESSION FOR MATCHING ARTICLE NAMES

### MEASURE PRECISION OF THE EXTRACTED ARTICLE MATCHED BY THE REGEX

### PERL CODE

### EXAMPLES

### ANALYSIS

### CONCLUSION
