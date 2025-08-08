# Assignment

## Brief

Write the Python codes for the following questions.

## Instructions

Paste the answer as Python in the answer code section below each question.

### Question 1

Question: How would you create a new hash in Redis to store information about a person, with `john_doe` as the key and include the name (`John Doe`), age (`35`), and email address (`john@email.com`)?

```python
import redis

r = redis.Redis(
  host='redis-10908.c252.ap-southeast-1-1.ec2.cloud.redislabs.com',
  port=10908,
  password='EgIvxgDuiuk2Sh5VnJzUGXDMtLrtK5Hk')
```

Answer:

```python
r.hset(
    'john_doe',
    mapping={
        "name": 'John Doe',
        "age": 35,
        "email": "john@email.com"
    },
)
```

### Question 2

Question: Write Python code to list the first 10 objects (blob name) in the "gcp-public-data-landsat" bucket, along with their sizes.

```python
from google.cloud import storage

client = storage.Client()
bucket = client.get_bucket("gcp-public-data-landsat")
```

Answer:

```python
blobs = bucket.list_blobs()
print("10 Blobs in {}:".format(bucket.name))
for ix, item in enumerate(blobs):
    print("\t" + item.name + "\t size: " + str(item.size) + " bytes")
    if ix == 9:
        break
```

## Submission

- Submit the URL of the GitHub Repository that contains your work to NTU black board.
- Should you reference the work of your classmate(s) or online resources, give them credit by adding either the name of your classmate or URL.
