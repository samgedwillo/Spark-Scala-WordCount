# Spark-Scala-WordCount

## My Links
- [Webpage](https://samgedwillo.github.io/Spark-Scala-WordCount/ "My Webpage")
- [Source](https://github.com/samgedwillo/Spark-Scala-WordCount  "My Source")

## About Me 
Hello, my name is Sam Gedwillo and I am a senior in Computer Science at Northwest Missouri State University. This repository shows how to use Scala to count the words of a text file. I chose to use Bob Marley's "Redemption Song" as an example.

## Scala
```
> val inputFile = sc.textFile("C:/44564/Spark-Scala-WordCount/data/redemptionsong.txt")
> val topWordCount = inputFile.
  flatMap(str=>str.split(" ")).
  filter(!_.isEmpty).
  map(word=>(word,1)).
  reduceByKey(_+_).
  map{case (word, count) => (count, word)}.
  sortByKey(false)
> topWordCount.
  take(10).
  foreach(x=>println(x))
```

## Results Graphs
These are the top ten most frequent words in the example song.
| word       | count |
|------------|-------|
| songs      | 12    |
| redemption | 7     |
| freedom    | 5     |
| cause      | 5     |
| ever       | 4     |
| none       | 4     |
| won't      | 3     |
| help       | 3     |
| sing       | 3     |
| ah         | 3     |
The chorus says both "songs" and "redemption" the most, so this result is what I was expecting.

![frequencychart](https://github.com/samgedwillo/Spark-Scala-WordCount/blob/master/images/frequencychart.png "frequencychart")