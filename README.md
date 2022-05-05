# UnsupervisedCryptoChallenge

## Integrate dependencies
- Matplotlib
- Pandas
- Numpy
- sklearn
    - Kmeans
    - StandardScaler
    - PCA
    - TSNE
- pathlib

## Data diagnosits
- Use read_csv file to convert csv into dataframe
- Use head function to evaluate data
- Look at the unique values of the IsTrading column
- Filter on the original dataframe and select on those records with column IsTrading equal to True
- Use drop function to remove both CoinName and IsTrading columns
- Evaluate columns to confirm the intended columns were dropped
- Filter the new dataframe where TotalCoinsMined has a value > 0
- Sort the new dataframe by TotalCoinsMined and print out values to ensure filter applied properly

## Apply dummy variables to categorical variables
- Us the get_dummies function to convert the Algorithm and ProofType columns to dummy variables
- Use head function for dataframe with dummy variables to ensure conversion performed accurately

## Scale data using standard approach
- Apply the StandardScaler function to the dataframe with dummy variables
- Evaluate the shape to understand how the data looks
- Apply PCA to reduce the dimensions (increased to 98 with get_dummies application)
- Create a def function to run multiple n_component benchmarks: .99. .95, .90
- Look at the shape of each n_component benchmark to understand how changing the value impacts the dimensions output
- Final benchmark is to be .90
- Add up the variances to determine how much variance is explained with PCA

## Utilize TSNE on the pca output
- Use learning rate 35 and perplexity 50
- Fit_transform the pca output (post scaling) to understand how TSNE impacts the dimensionality and whether it is a viable option
- Take TSNE output and calculate inertia for range of KMeans clusters

## Outome/Observations
- Curve is a linear line, showing no concavity/inflection points
- Based on this, it does not appear the cryptocurrencies can be clustered together

