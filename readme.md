
# Introduction
This repo houses a three-notebook project on the [Melbourne Housing Market](https://www.kaggle.com/anthonypino/melbourne-housing-market) dataset created by Tony Pino. In this project, I create a ridge regression model to predict house values and gain insight into the effect of each feature. [Part 1](https://github.com/michellekli/melbourne-housing/blob/master/melbourne-housing-part1.ipynb) covers the initial exploratory data analysis. [Part 2](https://github.com/michellekli/melbourne-housing/blob/master/melbourne-housing-part2.ipynb) covers more in-depth exploratory data analysis and data cleaning. [Part 3](https://github.com/michellekli/melbourne-housing/blob/master/melbourne-housing-part3.ipynb) covers feature selection, model evaluation, and finally model interpretation.

# Results
![An increase in building area in predicted to increase price.](https://github.com/michellekli/melbourne-housing/blob/master/plots/melbourne-housing-part3-pager-building-area-coef.png)

![An increase in distance from Hawthorn East is predicted to decrease price.](https://github.com/michellekli/melbourne-housing/blob/master/plots/melbourne-housing-part3-pager-hawthorn-distance-coef.png)

![Moving to Middle Park, Albert Park, Hampton, Brighton, Brighton East, Malvern, Malvern East, Balwyn North, Kew, or Ashburton is predicted to increase price. Moving to Camberwell, Surrey Hills, Glen Iris, Balwyn, or Canterbury is predicted to decrease price.](https://github.com/michellekli/melbourne-housing/blob/master/plots/melbourne-housing-part3-pager-suburb-coef.png)

# Error Analysis (Adjusted R-Squared = 0.695)
![Histogram of residual values. The residuals seem normally distributed.](https://github.com/michellekli/melbourne-housing/blob/master/plots/melbourne-housing-part3-pager-final-model-residuals-distribution.png)

![Scatter plot of predicted values versus residuals. The distribution of residuals seems consistent.](https://github.com/michellekli/melbourne-housing/blob/master/plots/melbourne-housing-part3-pager-final-model-residuals-scatter.png)

![Scatter plot of predicted values versus actual values. The adjusted r-squared is 0.695.](https://github.com/michellekli/melbourne-housing/blob/master/plots/melbourne-housing-part3-pager-holdout-predictions.png)

# Data Set
## Features
> Suburb: Suburb
>
> Address: Address
>
> Rooms: Number of rooms
>
> Price: Price in Australian dollars
>
> Method: S - property sold; SP - property sold prior; PI - property passed in; PN - sold prior not disclosed; SN - sold not disclosed; NB - no bid; VB - vendor bid; W - withdrawn prior to auction; SA - sold after auction; SS - sold after auction price not disclosed. N/A - price or highest bid not available.
>
> Type: br - bedroom(s); h - house,cottage,villa, semi,terrace; u - unit, duplex; t - townhouse; dev site - development site; o res - other residential.
>
> SellerG: Real Estate Agent
>
> Date: Date sold
>
> Distance: Distance from CBD in Kilometres
>
> Regionname: General Region (West, North West, North, North east ...etc)
>
> Propertycount: Number of properties that exist in the suburb.
>
> Bedroom2 : Scraped # of Bedrooms (from different source)
>
> Bathroom: Number of Bathrooms
>
> Car: Number of carspots
>
> Landsize: Land Size in Metres
>
> BuildingArea: Building Size in Metres
>
> YearBuilt: Year the house was built
>
> CouncilArea: Governing council for the area
>
> Lattitude: Self explanitory
>
> Longtitude: Self explanitory
> 
> [Source: Tony Pino, Dataset Creator](https://www.kaggle.com/anthonypino/melbourne-housing-market)

There is one feature not mentioned on the Kaggle page for this dataset, Postcode, which we can reasonably assume is the Postcode the property is located in.

## How the data was gathered
> 1. Grab the weeks domain pdf file from domain.com (python script cron job)
> 2. Save as text file (manual) 
> 3. Process (with python script) to get csv format
> 4. Using CSV run python script to get extra data from realestate.com
> 5. Using another excel file with melbourne postcodes/distances and other extras, vlookup.
> 
> You can miss step 4 sometimes as it's involved and takes some time to run (and I'm not sure how meaningful the extra data is, but it was something I wanted to do. [Source: Tony Pino, Dataset Creator](https://www.kaggle.com/anthonypino/melbourne-housing-market/discussion/53664)
