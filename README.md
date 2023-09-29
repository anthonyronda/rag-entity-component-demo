# rag-entity-component-demo
retrieval augmented generation of entities and components as applied to video games and VTT modules

## Fork this repo

All rights reserved to this research! However you are always allowed to create forks and experiment with new types

## What does it do

1. Given a source (examples: wiki site, PDF), break it down into chunks based off some simple rules, and
   create vector embeddings of all the source material. Store this in a vector datastore (examples: csv, ChromaDB)
2. Create a batch of queries (example: article titles in the source wiki), and using a template, generate
   new entities for each query containing

### Example

1. First, use the MediaWiki API to get the contents of every page in the "Generation I Pokemon" category on Bulbapedia.
   Vector embeddings are created for each chunk of each article and saved in a csv file.
2. Write a template of some JSON you want the LLM to generate. Use the example provided in `pokemon_example`
   directory for inspiration.
3. Finally, use the OpenAI API to generate a query for every Gen I Pokemon, feeding both the template and chunks from the
   vector db. The LLM API response should contain perfectly formatted JSON for all 151 Pokemon containing exactly the data
   you requested.
