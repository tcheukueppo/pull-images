# GET POSSIBLE PRICES OF AN ARTICLE FROM A SET OF WEB PAGES

## TECHNIQUE

1. Iterate over tags having contents and try to match each content with a regular expression
describing the price in your unit of interest(xaf, euro, dollar, ... etc.).

```
(?<i> (?&FLOAT) ) (?<u> (?&UNITS) )?
(?&PAD) (?<r> (?&RANGE) ) (?&PAD)
(?(<r>)
  (?<ii> (?&FLOAT) )?
  (?(<ii>)
     (?<u> (?&UNITS) )?
  )
)
(?(DEFINE)
  (?<FLOAT> \d+ (?: [.,] \d+ )? )
  (?<PAD> \s* )
  (?<RANGE> [-] )

  (?<DOLLAR> $ | &dollar; | (?i: dollar(?:s)? ) )
  (?<EURO> € | &euro; | (?i: euro(?:s)? ) )
  # define units here ...

  (?<UNITS>
       (?&DOLLAR) 
     | (?&EURO)
     # more units ...
  )
)
```

2. For a given tag, if this defined regex matches a substring of its content, then attempt to
locate the most closest targeting article name by executing **in order** the following
steps. If you succeed in either one of them then don't follow the next steps.

- Check the content of the tag itself to see if the name of your targeting article exists(Naive?).

If exists then we fill in the record for this price:

* The precision of the article name.
* The found article name.
* 

- 
