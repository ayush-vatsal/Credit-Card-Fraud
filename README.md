# Credit-Card-Fraud
A prediction service for flagging credit card fraud by checking for chain attacks and geographic attacks.
There are three different parquet files containing all details related to credit card transactions, we conceptualise them as coming from three different sources and join them with a natural key, "Transaction Id".
I have built three pipelines, Feature pipeline, training pipeline and a batch predictions pipeline. All but the training pipeline run on a cron schedule and save the predictions in an S3 instance provided by the Hopsworks feature store. The training pipeline is run on demand, it is versioned and saved in the same feature store for model serving.
