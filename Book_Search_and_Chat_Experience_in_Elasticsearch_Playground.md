# Step 2: Add Data to Elasticsearch
Click “Add data sources” in the Playground interface.

Select Elasticsearch as the data source.

Follow these steps to upload a sample dataset:

Open the Kibana > Dev Tools (found in your Elastic Cloud deployment).
Copy the following dataset into the console to create an index and populate data.
Command to Create the Index and Add Data:

`json`
PUT /books
{
  "mappings": {
    "properties": {
      "title": { "type": "text" },
      "author": { "type": "text" },
      "genre": { "type": "keyword" },
      "rating": { "type": "float" },
      "description": { "type": "text" }
    }
  }
}

# output
<img width="775" alt="image" src="https://github.com/user-attachments/assets/94a0775c-92d3-4eb7-8873-cd6e6a6dda88" />

2. Insert Documents One by One (no bulk):
For "The Catcher in the Rye":
`json`

POST /books/_doc
{
  "title": "The Catcher in the Rye",
  "author": "J.D. Salinger",
  "genre": "Classic Fiction",
  "rating": 4.1,
  "description": "A story about teenage angst and rebellion."
}

**OUTPUT**
<img width="772" alt="image" src="https://github.com/user-attachments/assets/39d019f2-fa07-4331-9077-696d39b60bca" />

For "1984":
`json`

POST /books/_doc
{
  "title": "1984",
  "author": "George Orwell",
  "genre": "Dystopian",
  "rating": 4.7,
  "description": "A chilling depiction of a totalitarian society."
}

**OUTPUT**
<img width="775" alt="image" src="https://github.com/user-attachments/assets/7ad7d525-72f0-4207-aa89-bd06394a344d" />


For "The Great Gatsby":
`json`

POST /books/_doc
{
  "title": "The Great Gatsby",
  "author": "F. Scott Fitzgerald",
  "genre": "Classic Fiction",
  "rating": 4.4,
  "description": "A critique of the American Dream in the 1920s."
}

**OUTPUT**
<img width="775" alt="image" src="https://github.com/user-attachments/assets/9e657331-d239-4a9f-b0bb-61b1a98ae2b8" />


For "Dune":
`json`

POST /books/_doc
{
  "title": "Dune",
  "author": "Frank Herbert",
  "genre": "Science Fiction",
  "rating": 4.5,
  "description": "An epic story of politics, religion, and survival on a desert planet."
}
**OUTPUT**
<img width="774" alt="image" src="https://github.com/user-attachments/assets/7b4f90d6-2155-49ea-b29b-8975e5f94d05" />


For "To Kill a Mockingbird":
`json`

POST /books/_doc
{
  "title": "To Kill a Mockingbird",
  "author": "Harper Lee",
  "genre": "Classic Fiction",
  "rating": 4.9,
  "description": "A powerful story of race and justice in the Deep South."
}
**OUTPUT**
<img width="774" alt="image" src="https://github.com/user-attachments/assets/161a2d66-5dc6-4090-9e9a-173124226e34" />

3. Verify Data Upload:

Go back to the Playground interface.
<img width="188" alt="image" src="https://github.com/user-attachments/assets/1ed8a64f-ac98-4879-8213-e9be3a52ce70" />

Add data sources
<img width="770" alt="image" src="https://github.com/user-attachments/assets/c7fc87bc-7083-4e75-af77-64d2149b6734" />

select book index -> save and continue
<img width="774" alt="image" src="https://github.com/user-attachments/assets/e80c0ba6-2d50-4ca4-8377-2e4e1a972017" />

go to this link and create API key
https://platform.openai.com/account/api-keys

click create secrate key
<img width="956" alt="image" src="https://github.com/user-attachments/assets/701c4429-92d6-461d-b534-08a851a8a1ee" />

give key name and click create secrate key
<img width="815" alt="image" src="https://github.com/user-attachments/assets/4720e776-f43b-455c-abed-68e4ecf999d0" />

copy and keep your secrate key safe
<img width="669" alt="image" src="https://github.com/user-attachments/assets/82f53b00-64ed-4dd6-86d3-4ed62e3e727d" />

create API key
<img width="774" alt="image" src="https://github.com/user-attachments/assets/5931ea69-e595-470c-b4f6-7aefabb22d1c" />
<img width="450" alt="image" src="https://github.com/user-attachments/assets/223a3bc3-1150-49b7-b3b6-563999818a6a" />

copy API key and keep it safe to use it in LLM
<img width="775" alt="image" src="https://github.com/user-attachments/assets/4b249cc5-2d01-4c79-84dd-74aad821f09b" />
<img width="477" alt="image" src="https://github.com/user-attachments/assets/00d48bb3-3aec-43ef-9d15-8ab793d45d33" />
<img width="475" alt="image" src="https://github.com/user-attachments/assets/1000530f-02dc-471b-86a8-e4e860aa5f0b" />

Add API Key of open AI and click save
<img width="480" alt="image" src="https://github.com/user-attachments/assets/86c96c28-1b4f-4c41-8db8-62d7f44de358" />


run the connector
<img width="766" alt="image" src="https://github.com/user-attachments/assets/17580eae-ce33-41fc-8b6f-50a9f73cafaf" />
<img width="475" alt="image" src="https://github.com/user-attachments/assets/492728ef-93a7-4be4-a055-ff7b13482e35" />


endpoint
https://f79cc72a0d5f419591ae98a4423a7bee.us-central1.gcp.cloud.es.io:443

API key value
VGR1alFaUUJ1YWRnNVhGWjlMZVQ6SkpKZnJaUFhRMGlrSFNRZ3VIY3FWQQ==

Click on the Query tab.

Type the following query to verify the data:

`json`
{
  "query": {
    "match_all": {}
  }
}
