```
cd parent
skaffold run
```

h2. Expected
```
❯ skaffold run                                            
Generating tags...
 - foobar -> localhost:32000/foobar:latest
Checking cache...
 - foobar: Found Remotely
Starting test...
Tags used in deployment:
 - foobar -> localhost:32000/foobar:latest@sha256:45474bc62d867e8e1ed5a4f65d8ebdadd6390351831780a78e7814bbb0e3a1e1
Starting deploy...
 - configmap/dependency created
 - configmap/parent created
Waiting for deployments to stabilize...
Deployments stabilized in 46.856264ms
You can also run [skaffold run --tail] to get the logs
```

h2. Actual

```
❯ skaffold run
Generating tags...
 - foobar -> localhost:32000/foobar:latest
Checking cache...
 - foobar: Error checking cache.
getting hash for artifact "foobar": getting dependencies for "foobar": getting dependencies from command: "./test.sh": starting command ./test.sh: fork/exec ./test.sh: no such file or directory
```