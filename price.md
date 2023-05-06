# GET POSSIBLE PRICES OF AN ARTICLE FROM A SET OF WEB PAGES

## TECHNIQUE

1. Iterate over tags with contents and try to match each tag's content against a regular expression
describing the price in your unit of interest (XAF, EURO, DOLLAR, ... etc.) and if its matches
then marked it.

2. For each marked tag, attempt to locate the most closest article name by executing
**in order** the following steps. Avoid the next steps if you successfully found your targeting
article.

- Check the content of the tag itself to see if the name of your targeting article exists(Naive?) and
if so then we fill in the record for this price:

> * The extracted article name in the tag's content.
> * The precision of the extracted article name.
> * A distance of zero between price and the extracted article.

- Without crossing marked tags, check the content of each of its upper siblings from the closest
to the farthest one and if you found your targeting article name, then stop there and fill in
the record for this price.

> * The extracted article name in the content.
> * The precision of the extracted article name.
> * The distance between the extracted article and the marked tags(Both from the same tag).

- Well, if you've arrived here then that means the page in question might be for that of
an ecommerce website, so this is my logic:


