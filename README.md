# The Guardian Corpus
The corpus includes 50 articles from the first five pages of December 2023. It can be utilized by scholars to analyze sentiment and political standpoints from the newspaper.

## Text selection criteria
1. Relevance:
Titles and main body contents containing the majority of textual information are essential for analysis.
2. Representation and Volume:
This serves as a pilot experiment for the group project, with the collection of only 50 articles. For the eventual project, the plan is to focus on specific topics like healthcare and a particular time span. Therefore, exploring larger datasets under a specific domain would be better to thoroughly investigate our research questions.
3. Annotation and Labeling:
Dates can be used as filters or classifiers in further network analysis. URLs are also included so that, in case of character encoding issues or loss of metadata, we can trace back to the original link.

## The data collection process
1. Get All Data:
The Guardian provides an open API to query the content it creates. First, I sign up for an API key, and then I use the Explore function from the [Guardian Open Platform](https://open-platform.theguardian.com/explore/) to filter and obtain the API link.
2. Extract Data I Need:
The response from the request contains many pieces of information that I am not interested in, such as sectionID. By parsing the format, I write a function to extract title, date, URL, and contents.
3. Save Data into Files:
Save the extracted data into files.

## Preprocessing
- To maintain the readability of files, the filename is the same as the title, with special characters removed. I only keep 'bodyTextSummary' as the contents of each file, so it will be useful for corpus analysis.
- Before annotating, we need to load the data into a dataframe so that Pandas can batch-process text files. 

## Annotations
Annotations contain 3 columns, processed using Spacy:
1. Tokens (tokenized text of this document).
2. Lemmas (lemmatized text of this document).
3. Parts-of-speech (parts of speech of all the tokens in this document).

## Output
There are two formate of the corpus. One is 50 [txt files](https://github.com/Gmin-test/RUG_DH_CD_LAB_Week5/tree/main/guardian_corpus_spacy_improved) for metadata and another is a [csv file](https://github.com/Gmin-test/RUG_DH_CD_LAB_Week5/blob/main/Guardian_corpus_annotated.csv)that contain annotation.
| Header   | Description                                     |
|----------|-------------------------------------------------|
| webTitle | The title of the news. |
| webUrl   | The link of the news. |
| bodyTextSummary| The content of the news.|
| Token    | Tokenized text of the news.|
| Pos      | Parts of speech of all the tokens in the news.|
| Lemma    | Lemmatized text of the news.|
