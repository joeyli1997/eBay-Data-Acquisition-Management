# eBay-Data-Acquisition-Management

### Data Source
eBay website content.

### Methodology
- Search for buy-it-now listings of keyword and limit the number of items to 100 per page. For the first 10 pages of 100 items/page, save all the URLs of sponsored items' pages to the file "sponsored.txt" and all the URLs of non-sponsored items' pages to the file "non-sponsored.txt" in the same directory as the code.
- Create two folders in the same directory as the code and name them "sponsored" and "non-sponsored". Write a program that opens the two files and downloads each of the pages (URLs) into the folders "sponsored" and "non- sponsored". Each file should be named as "item-id.htm" where you replace "item-id" with the ID of the item you are saving. E.g., "264616053293.htm" for the item with ID "264616053293". Note it is always good to put a 2-second pause between queries. Make sure to catch an error and continue if your query runs into problems connecting to eBay.
- Loops through the pages downloaded and opens and parses them into a Python Beautifulsoup-object. Identify and select: seller name, seller score, item price, # items sold, best offer available, title, returns allowed, shipping price, condition (e.g., used, new, like new, seller refurbished, ...)

### Database
- Connect to SQL. Create a database and name it "eBay". Save the information of items in into a single table named "eBay_items" (You are allowed to use only one table). This table should contain both sponsored and non-sponsored information and have a column that specifies which item is sponsored/non-sponsored. If an item misses ANY of the information in (d), you should insert that missing value as NULL into the table. Convert any price (item price and shipping price) into a "dollar-cent" format (e.g., convert 12.34 into 1234 and 12 into 1200. Make sure the two least significant digits are cents. If an item does not include cents in the price, insert zeros.) and insert the price as INT into the table.
- Use the code script to run summary stats on each item. Print to the screen the mean, min, max, and mean for each column, grouped by "sponsor/non-sponsor" and "condition" (group by at the same time, not separately). For binary categorical columns, use 0-1 conversion. For e.g., for the "returns allowed" convert YES to 1 and NO to 0 and then calculate the stats. If it is NOT a numerical/binary categorical column, print to the screen the count of each category level. You will need to ignore NULL values in your statistic calculations.

### Analysis
- Use the stats in above and tell how sponsored and non-sponsored items appear to be different.
