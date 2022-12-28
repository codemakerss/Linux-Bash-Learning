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
  


