FAQ app with Sentence embeddings with ES
-----------------------------------------

- Sentence Embedding Technique used: Googe's Universal Sentence Encoder
- ES 7.3 or higher to use the vector functions and cluster must be running the default (not OSS) distribution

Install requirements in virtual environment
```
python3 -m venv venv
source venv/bin/activate
pip install -r requirements.txt
```

Run ES version 7.3.1 docker
```i
# https://www.elastic.co/guide/en/elasticsearch/reference/current/vm-max-map-count.html
$ sudo sysctl -w vm.max_map_count=262144

$ docker run --rm --name es7 -p 9200:9200 --env discovery.type=single-node  docker.elastic.co/elasticsearch/elasticsearch:7.3.1

```

Start Script
```
python run.py
```

How does it work?
-----------------
1. Create an ES index with field type `dense_vector` to store. It is required to specify the number of dimensions the vectors will contain.
2. Run the `question_title` through the embedding model (use Google's Universal Sentence Encoder) to obtain a numeric array and store as `title_vector`
3. WHen user enters a query, the text is first run through the same embedding model and stored in the parameter `query_vector`. Use `script_score` query with `cosineSimilarity` function.


Reference: https://www.elastic.co/blog/text-similarity-search-with-vectors-in-elasticsearch

