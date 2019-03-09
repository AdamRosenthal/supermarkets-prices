# supermarkets
Israel supermarket's prices data


Notebook contains an exploration for a database containing supermarket prices.
The data was scraped and parsed from 20/5/2015 untl approximately 7/1/2017.

### Main Issues:

* Items do not have a unique id between chains, only between stores within the same chain.
Identification of a product is do done for each chain. For vegetables, is is done by using the assumption that the item that contains the letters "עגבניות", with the most price updates in the chain, is the standard tomato item (and not, for example, tomato sauce or an organic tomatoes)

* There are long periods of time in which the item prices were not updated or were updated with the same price value. Stores that were suspected their price wasn't updated due to an error (long periods, out of context prices), were taken out of the sample and put in a panel called "bad_stores" (there's an example plotted in the notebook)


* There is only one valid online store data. One of the objectives was to explain the connection between online stores prices and physical stores prices. due to the fact there is only one online store with valid prices (mega's store number 153) it will be difficult to estimate this connection (but not impossible). 

* The DB does not contain promo data for some of the items that were checked.

* The data is noisy. Inaccuracies were found, values that don't make sense, missing important information about stores characteristics and more. There are long periods in which the scrapers did not update the DB or that the data that was given by the chain was false.

### Simple Data analysis
from the obtained prices panel data, created a data set of Mega branches such that each row is a store, each column is representing the price of a product in a certain date. additionally, there is a label column that holds the type of the store (Mega Ba'air or Mega Big). Trained a simple sklearn KNeighborsClassifier for the hack of it. It predicts the type of the store on the test data with high accuracy rate.

Contact me to get an update on scraping status.
