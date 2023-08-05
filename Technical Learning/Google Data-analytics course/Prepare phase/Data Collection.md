#data-analytics 
#process-dataAnalytics 

next :- [[good-bad-data practices]]

---
- How data will be collected
	Data collection methods :-
	1. Forms
	2. Surveys
	3. Questionnaire 
	4. Observations
	5. Cookies - browser


- Choose Data sources  :
	- First party data -  Data collected by an individual or group using their own resources.
	- Second party data - Data collected by a group directly from its audience and then sold.
	- Third party data - Data collected from outside sources who did not collected it directly. has to be checked for accuracy , credibility and bias.

- Decide what data to use
- How much data to collect ( sample of a large population)
- Select right data type
- Determine the time frame

![[Pasted image 20230420181424.png | 500]]

## Transforming data

**Long data** is data where **each row contains a single data point** for a particular item. In the long data example below, individual stock prices (data points) have been collected for Apple (AAPL), Amazon (AMZN), and Google (GOOGL) (particular items) on the given dates.

![[Pasted image 20230420182944.png | 400]]

**Wide data** is data where **each row contains multiple data points** for the particular items identified in the columns. 

![[Pasted image 20230420183010.png|400]]

With data transformed to wide data, you can create a chart comparing how each company's stock changed over the same period of time.

![[Screenshot 2023-04-20 at 6.30.39 PM.png]]

You might notice that all the data included in the long format is also in the wide format. But wide data is easier to read and understand. That is why data analysts typically transform long data to wide data more often than they transform wide data to long data.


## Data biases

- Sampling bias - is when a sample isn't representative of the population as a whole
- Observer bias - it's the tendency for different people to observe things differently
- Interpretation bias -  The tendency to always interpret ambiguous situations in a positive, or negative way. Interpretation bias, can lead to two people seeing or hearing the exact same thing, and interpreting it in a variety of different ways  because they have different backgrounds, and experiences.
- Confirmation bias - Confirmation bias, is the tendency to search for, or interpret information in a way that confirms preexisting beliefs. 
- 