# The Guardian Corpus
The corpus includes 42 articles from the first 5 pages under the 'World' section, spanning from November 1, 2023, to December 15, 2023. It can be utilized by scholars to analyze sentiment and political standpoints from the newspaper.

## Text selection criteria
1. Relevance:
Titles and main body contents containing the majority of textual information are essential for analysis.
2. Representation and Volume:
This serves as a pilot experiment for the group project, with the collection of only 42 articles. For the eventual project, the plan is to focus on specific topics like healthcare and a particular time span. Therefore, exploring larger datasets under a specific domain would be better to thoroughly investigate our research questions.
3. Annotation and Labeling:
Dates can be used as filters or classifiers in further network analysis. URLs are also included so that, in case of character encoding issues or loss of metadata, we can trace back to the original link.

## The data collection process
1. Get All Data:
The Guardian provides an open API to query the content it creates. First, I sign up for an API key, and then I use the Explore function from the [Guardian Open Platform](https://open-platform.theguardian.com/explore/) to filter and obtain the API link.
2. Extract Data I Need:
The response from the request contains many pieces of information that I am not interested in, such as sectionID. By parsing the format, I write a function to extract title, section, date, URL, and contents.
3. Save Data into Files:
Save the extracted data into files.

## Preprocessing
- To maintain the readability of files, the filename is the same as the title, with special characters removed.
- Before annotating, we need to load the data into a dataframe so that Pandas can batch-process text files. Therefore we get two basic columns of the dataset: Filename and Document.

## Annotations
Annotations contain 3 columns, processed using Spacy:
1. Tokens (tokenized text of this document).
2. Lemmas (lemmatized text of this document).
3. Parts-of-speech (parts of speech of all the tokens in this document).

## Output
There are two formate of the corpus. One is 42 [txt files](https://github.com/Gmin-test/RUG_DH_CD_LAB_Week5/tree/main/guardian_corpus) for metadata and another is a [csv file](https://github.com/Gmin-test/RUG_DH_CD_LAB_Week5/blob/main/Guardian_corpus_annotated.csv)that contain annotation.
| Header   | Description                                     |
|----------|-------------------------------------------------|
| Filename | The name of the file corresponding to the document. |
| Document | The content of the document.                     |
| Token    | Tokenized text of the document.                  |
| Pos      | Parts of speech of all the tokens in the document.|
| Lemma    | Lemmatized text of the document.                 |
