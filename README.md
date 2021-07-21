# ThumbNailList

This is a reactJS component meant for listing documents either in a vertical or horizontal manner.

It comes in two sub-classes:
1. a `VerticalThumbNailList`
2. a `HorizontalThumbNailList` component as desired.


**DO NOT** call the component --as appears in the title-- directly because it renders nothing. The subclasses are responsible for this!
## ThumbNailList props (or arguments)

```
  thumbnailcallback - this property is used to explain to the desired listing component
                      of the intended actions to take when a thumbnail is (single) clicked.
                      
  documents - this property is used to pass the documents to view as thumbnails.
```
## documents props format
Documents passed to a thumbnail are passed as a array of JSON objects, with each json object being of exactly one element.
Passing multiple elements in one JSON object will lead to subsequent elements (except the first one) being ignored.
The maximum list of documents supported is undefined at this time. Feel free to experiment with this.

```
    [
      {a_document_identifier: document_string_blob_or_path},
      {another_document_identifier: another_string_blob_or_path},
      ...
    ]
```
## how to call the thumbnail list component
This method applies to both the `VerticalThumbNailList` as well as the `HorizontalThumbNailList` components.
```
  const documentsList = [{doc1: doc_object_1}, {doc2:doc_object_2},...];
  
  const thumbnailCallback = (targetThumbNail <= Object>) => {
    //some logic to process the target thumbnail
  };
  
  ...
  //your desired logic above...
  //calling the Vertical thumbnail list. this format applies also to the Horizontal thumbnail list component.
  
  <VerticalThumbNailList documents = {documentsList} thumbnailcallback = {thumbnailCallback} />
  
```
### Notes on the above code
To distinguish javascript's `spreader` operator (that is, `...`), the referred `...` notation on the above example
is meant to hint at the continuity of the list supplied by the developer with regards to documents intended for view
in these list components.
