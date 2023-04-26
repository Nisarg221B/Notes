

next :- [[Sample population]]

--- 

Data Integrity is accuracy , consistency , completeness and trustworthiness of data throughout data lifecycle. 

Here are some other things to watch out for which might let to compromising of data integrity:

-   **Data replication compromising data integrity:** Continuing with the example, imagine you ask your international counterparts to verify dates and stick to one format. One analyst copies a large dataset to check the dates. But because of memory issues, only part of the dataset is actually copied. The analyst would be verifying and standardising incomplete data. That partial dataset would be certified as compliant but the full dataset would still contain dates that weren't verified. Two versions of a dataset can introduce inconsistent results. A final audit of results would be essential to reveal what happened and correct all dates.
-   **Data transfer compromising data integrity:** Another analyst checks the dates in a spreadsheet and chooses to import the validated and standardised data back to the database. But suppose the date field from the spreadsheet was incorrectly classified as a text field during the data import (transfer) process. Now some of the dates in the database are stored as text strings. At this point, the data needs to be cleaned to restore its integrity. 
-   **Data manipulation compromising data integrity:** When checking dates, another analyst notices what appears to be a duplicate record in the database and removes it. But it turns out that the analyst removed a unique record for a company’s subsidiary and not a duplicate record for the company. Your dataset is now missing data and the data must be restored for completeness.

## Dataset

**think that dataset like a picture**

![[Screenshot 2023-04-25 at 5.09.13 PM.png | 400]]

from the above picture you won't be able to get the whole point

![[Screenshot 2023-04-25 at 5.10.09 PM.png | 400]]

when you get the complete picture you realise that you are in London. 

Therefore with incomplete data its hard to see the complete picture to get the real sense of what is going on. 


