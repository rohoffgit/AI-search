# AI - Search 

Sample code to index (pull/push) and search, etc.

### Requirements
pip install -r requirements.txt

### Create index

See index_create.ipynb notebook to create an index with integrated chunking and vector embedding. 
Note that the index will be recreated every time which may be useful during development.

### Adding documents to the index

There are two basic approaches, see https://learn.microsoft.com/en-us/azure/search/search-what-is-data-import

In a nutshell:
- Pull is the PaaS approach where the managed index will run regularly to pick up new files and put them to the indexing pipeline. The indexing pipeline executes the defined skills (like chunking, embedding, custom function, other cognitive skill, etc.) on the document, which will then be added to the index.

- Push is the DIY approach, where documents get added directly to the index. In this approach your code is responsible to chunk, emmbed and otherwise prepare the document to be added.

### Helper functions

pull_reindex.ipynb - Trigger reindex of certain documents (blobs) in the pull approach.
