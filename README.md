# Hadoop

# To clone:

git clone https://github.com/laxmipolam/Hadoop.git

# To get data:
hadoop fs -get /user/tatavag/nyc.data ~/nyc


hadoop fs -get /user/tatavag/nyc.data ~/Hadoop/nyc.csv

hadoop fs -put nyc.csv /user/polamli/nyc.csv ( Already Exists)

# To give persmissions:

chmod +x mapper.py && chmod +x reducer.py

# To Execute:

(summaryname can be replaced with any other name)

hadoop jar /usr/hdp/current/hadoop-mapreduce-client/hadoop-streaming.jar -file ~/mapper.py -mapper ~/mapper.py -file ~/reducer.py -reducer ~/reducer.py -input /user/polamli/nyc.csv -output /user/polamli/summaryname

# Downloading file from hdfs to local machine:

hadoop fs -get /user/polamli/summaryname/part-00000 ~/summaryname.txt

# To See the output:

hadoop fs -cat /user/polamli/summaryname/*
