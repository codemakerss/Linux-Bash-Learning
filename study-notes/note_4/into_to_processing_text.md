# Introduction to Processing Text in Linux
  
- Benefits of Processing Text in Linux
  
Linux + Text is everywhere, simple, fast and intuitive
  
- Using grep, cut, sort and unique in Linux
  
Amazon orders example
```bash
# count number of negative reviews from orders
grep -C NEGATIVE amazon_reviews_appliances_5k_with_sentiment.txt

# difference between two files
diff fruit1.txt fruit2.txt
diff fruit*

# only show unique data in a file 
uniq fruit1.txt
uniq -c fruit1.txt

# sort
sort fruit1.txt

# truncate files
cat amazon_reviews_appliances_5k_with_sentiment.txt | rev | cut -d, -f1 | re
# print file data | reverse order for everything inside | use delimiter to call the first column out
```
  
- Editing with Truncation, awk and sed in Linux
  
```bash
echo "lower" | tr a-z A-Z # make upperclass

LOWER

# swap method (replace occurrence of MIXED with NEGATIVE)
echo "MIXED" | sed 's/MIXED/NEGATIVE/'

shuf -n 200 amazon_reviews_appliances_5k_with_sentiment.txt | sed 's/MIXED/NEGATIVE/'
```
  
Using AWK
```bash
# only show entries with 10 or fewer fields
shuf -n 200 amazon_reviews_appliances_5k_with_sentiment.txt | sed 's/MIXED/NEGATIVE/' | awk 'NF < 10'

# show entries that have large reviews
shuf -n 200 amazon_reviews_appliances_5k_with_sentiment.txt | sed 's/MIXED/NEGATIVE/' | awk 'NF > 300'
```
  
- Using Regular Expressions (regex) in Linux
  
Check phone number valid example
```bash
echo 415-444-2132 | grep '\(([0-9]\{3\})\|[0-9]\{3\}\)[ -]\?[0-9]\{3\}[ -]\?[0-9]\{4\}'

# only output correct phone numbers with correct formats 
cat phone-numbers | grep '\(([0-9]\{3\})\|[0-9]\{3\}\)[ -]\?[0-9]\{3\}[ -]\?[0-9]\{4\}'

# give me files that matched with words searched with
ls | grep -Eh 'phone|fruit'

grep -Eh 'phone|fruit' amazon_reviews_appliances_5k_with_sentiment.txt | wc -l
```

