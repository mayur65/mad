Steps
1. Open Eclipse> File > New > Java Project >( Name it – MRProgramsDemo) > Finish.

2. Right Click > New > Package ( Name it - PackageDemo) > Finish.

3. Right Click on Package > New > Class (Name it - WordCount).

4. Add Following Reference Libraries:

5. Right Click on Project > Build Path> Add External

/usr/lib/hadoop-0.20/hadoop-core.jar

Usr/lib/hadoop-0.20/lib/Commons-cli-1.2.jar

WRITE YOUR CODE

6. Make  a jar file

Right Click on Project> Export> Select export destination as Jar File  > next> Finish.

7. Take a text file (wordcountFile.txt) and move it into HDFS format: 
To move this into Hadoop directly, open the terminal and enter the following commands:

$ hadoop fs -put wordcountFile wordCountFile

8. Run the jar file, use command:

$ hadoop jar jarfilename.jar packageName.ClassName PathToInputTextFile PathToOutputFolder
$ hadoop jar MRProgramsDemo.jar PackageDemo.WordCount wordCountFile MRDir1

9. Open the result:
$ hadoop fs -ls OutputFolderName
$ hadoop fs -ls MRDir1


Found 3 items
-rw-r--r--   1 training supergroup          0 2016-02-23 03:36 /user/training/MRDir1/_SUCCESS
drwxr-xr-x   - training supergroup          0 2016-02-23 03:36 /user/training/MRDir1/_logs
-rw-r--r--   1 training supergroup         20 2016-02-23 03:36 /user/training/MRDir1/part-r-00000


10. $ hadoop fs -cat OutputFolderName/part-r-00000
	$ hadoop fs -cat MRDir1/part-r-00000








