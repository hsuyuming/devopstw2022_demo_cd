### cloudbuild cmd example
```cmd
gcloud builds submit --config="./cloudbuild.yaml" --worker-pool=xxxxx --gcs-log-dir=gs://xxxxx/build-logs --region us-west1 
```

### gcloud deploy cmd example
```cmd
export random_str=`echo $RANDOM | md5sum | head -c 10; echo;`
gcloud deploy releases create devopstw22-release-$random_str --build-artifacts=./tags.json --project=xxxxx--region=us-west1 --delivery-pipeline=devopstw22-clouddeploy
```

### promote release
```cmd
gcloud deploy releases promote --delivery-pipeline devopstw22-clouddeploy2 --region us-west1 --release=devopstw22-release-571bf2796a-20220915-0241
```