### **Dataset**

To download the [dataset](https://www.kaggle.com/competitions/birdsong-recognition/data), use Kaggle API command:
```console
kaggle competitions download -c birdsong-recognition
```

### **Files**

**train_audio** The train data consists of short recordings of individual bird calls generously uploaded by users of xenocanto.org.

**test_audio** The hidden ```test_audio``` directory contains approximately 150 recordings in mp3 format, each roughly 10 minutes long. They will not all fit in a notebook's memory at the same time. The recordings were taken at three separate remote locations in North America. Sites 1 and 2 were labeled in 5 second increments and need matching predictions, but due to the time consuming nature of the labeling process the site 3 files are only labeled at the file level. Accordingly, site 3 has relatively few rows in the test set and needs lower time resolution predictions.

Two example soundscapes from another data source are also provided to illustrate how the soundscapes are labeled and the hidden dataset folder structure. The two example audio files are ```BLKFR-10-CPL_20190611_093000.pt540.mp3``` and ```ORANGE-7-CAP_20190606_093000.pt623.mp3```. These soundscapes were kindly provided by Jack Dumbacher of the California Academy of Science's Department of Ornithology and Mammology.

**test.csv** Only the first three rows are available for download; the full test.csv is in the hidden test set.

- ```site```: Site ID.
- ```row_id```: ID code for the row.
- ```seconds```: the second ending the time window, if any. Site 3 time windows cover the entire audio file and have null entries for seconds.
- ```audio_id```: ID code for the audio file.

**example_test_audio_metadata.csv** Complete metadata for the example test audio. These labels have higher time precision than is used for the hidden test set.

**example_test_audio_summary.csv** Metadata for the example test audio, converted to the same format as used in the hidden test set.

- ```filename_seconds```: a row identifier.
- ```birds```: all ebird codes present in the time window.
- ```filename```
- ```seconds```: the second ending the time window.

**train.csv** A wide range of metadata is provided for the training data. The most directly relevant fields are:

- ```ebird_code```: a code for the bird species. You can review detailed information about the bird codes by appending the code to https://ebird.org/species/, such as https://ebird.org/species/amecro for the American Crow.
- ```recodist```: the user who provided the recording.
- ```location```: where the recording was taken. Some bird species may have local call 'dialects', so you may want to seek geographic diversity in your training data.
- ```date```: while some bird calls can be made year round, such as an alarm call, some are restricted to a specific season. You may want to seek temporal diversity in your training data.
- ```filename```: the name of the associated audio file.
