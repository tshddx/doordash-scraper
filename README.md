# DoorDash Scraper

Have you ever wanted to download your entire order history from [DoorDash](https://www.doordash.com)? We wanted to do this at [my office](https://www.golden.com) but were unable to find anywhere on their website to do so. So here's my quick solution. Feel free to modify it to fit your desires⁠—there are a lot more data available that this script is not ingesting.

## Instructions

### Obtain a DoorDash.com sessionid

1. Sign in to your account at https://www.doordash.com/consumer/login/.
2. Find your `sessionid` cookie. You can use the Application tab of the Chrome DevTools. It will probably be a 32-character string of letters and numbers.

### Run the scraper

Now just run the scraper with your sessionid. It will output two CSV files containing all your DoorDash orders.

**Note:** In addition to the `doordash.csv` and `doordash-pivot.csv` files, this script will generate a lot of JSON files in your current directory (roughly one per order). These are the raw responses from each network request. This allows the script to resume where it left off if something goes wrong.

```bash
> python doordash_scraper.py 6ess7lab6uzx9xq8c3rey5yzzjn6c6cat
Fri Aug 16 15:27:02 2019   Fetching all order summaries in batches of 20
Fri Aug 16 15:27:02 2019   Got an empty batch, so we're done fetching order summaries!
Fri Aug 16 15:27:02 2019   Writing normal CSV doordash.csv
Fri Aug 16 15:27:02 2019   Writing pivoted CSV doordash-pivot.csv
```
