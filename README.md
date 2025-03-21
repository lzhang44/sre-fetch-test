
# SRE Fetch Take Home Exercise 

The README for SRE Fetch take home exercise. Instructions on how to run and what changes were made/why are provided as well as other notes.

### How to install and run

1) Make sure you have python (v3.9.13 or higher) installed. If you don't, you can follow this guide: https://wiki.python.org/moin/BeginnersGuide/Download   
2) In your directory of choice, clone this repo into your folder:
```git clone <repo>```
3) Navigate into this repo:
```cd <path>/sre-fetch-test```

```Shell
$ python main.py <input_file.yaml>
#or
$ python main.py sample1.yaml
```

## Changelog 
Went through each requirement and made updates to the provided main.py accordingly
1) Line 14: Set default to 'GET' if method is not specified
- Why: Received AttributeError: 'NoneType' object has no attribute 'upper'
- Process: Ran initial starter code to see what happened. Recieved this error so I followed the stack trace. [TODO: EXPLAIN PROCESS]

2) Line 20, 21: Added latency variable and conditional
- Why: To meet the availibility requirements of endpoint responding with a latency of < 500ms (in addition to the status code)
- Process: I had added some print logs to monitor the availabiliy. I noticed they stayed very consistent so I checked whether the math to calculate availability was correct (it was), and then realized the conditions for an endpoint to be considered UP was not met. I added the latency variable using a request module (total_seconds) and converted to ms. I also updated the condition to make sure the response takes less than 500ms to be considered available.

3) Line 35: Updated domain variable [RE-EXAMINE THIS?? 'ignore port nubmers when determining domain]
- Why: To ignore ports when determining domain
- Process: Usually ports take on the syntax of <IP>:<port> so I just added a split with a ":" delimiter, grabbing 

## Assumptions
- All input files are in correct yaml format
- 
