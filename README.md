# Extend BigQuery NLP armory with Transliteration

## How to reproduce

*If you want to just test or use stemming functionality in BigQuery, without implementing it,
go to — 7. Stemmers Demo.

### 1. Clone the repository

    git clone https://github.com/justdataplease/bigquery-transliteration.git

### 2. Install necessary packages defined in package.json.

    npm install

### 3. Run webpack.config.js to create our package using webpack.

    npm run-script build

### 4. Create a bucket in GCS. Make sure to change "yourproject" with your GCP project id and "yourbucket" with your desired bucket name (has to be universally unique).

    gsutil mb -c nearline -l europe-west3 -p yourproject gs://yourbucket

### 5. Copy webpack output or nlp.js to GCS.

    gsutil cp dist/transliteration.js gs://yourbucket

### 6. Implement Transliteration

As an example, we will translate the following English sentence into Greek and Spanish.

"Natural language processing is a subfield of linguistics computer science and artificial intelligence concerned with
the interactions between computers and human language"
