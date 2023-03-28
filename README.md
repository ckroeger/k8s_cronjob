# k8s_cronjob
Kubernetes Cronjob examples

# Echo every minute

## install job
```shell
$ kubectl create -n <NAMESPACE> -f echo_every_minute.yaml

cronjob.batch/echo-job created
```

# watch jobs
````shell
$ kubectl -n <NAMESPACE> get jobs --watch
NAME                COMPLETIONS   DURATION   AGE
echo-job-28000125   0/1                      0s
echo-job-28000125   0/1           0s         0s
echo-job-28000125   0/1           5s         5s
echo-job-28000125   1/1           5s         5s
echo-job-28000126   0/1                      0s
echo-job-28000126   0/1           0s         0s
echo-job-28000126   0/1           2s         2s
echo-job-28000126   1/1           2s         2s
echo-job-28000127   0/1                      0s
echo-job-28000127   0/1           0s         0s
echo-job-28000127   0/1           2s         2s
echo-job-28000127   1/1           2s         2s
````

# show log of job
````shell
$ kubectl -n <NAMESPACE> log job/echo-job-XXXXXXX 
----------- d=Tue Mar 28 12:46:01 UTC 2023 echo echo at  echo  -----------
````
