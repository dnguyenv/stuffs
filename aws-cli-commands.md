# Some helpful AWS cli commands

## Batch deleting Glue jobs based on jobs names

```bash
$ aws glue get-jobs | jq '.Jobs | .[].Name' | grep '<part-of-job-name>' | xargs -n1 aws glue delete-job --job-name > output.txt
```

Example: Delete all Glue jobs with `duyhard` as part of their names

```bash
$ aws glue get-jobs | jq '.Jobs | .[].Name' | grep 'duyhard' | xargs -n1 aws glue delete-job --job-name > ouput.txt
```