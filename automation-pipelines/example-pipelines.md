# Example Pipelines

```text
$schema: https://schemas.stemn.com/pipeline+v1

label: Matches a file to each trigger type

triggers:
- files: revision.txt
  type: revision
- files: commit.txt
  type: commit
- files: release.txt
  type: release

stages:
- label: write trigger type to trigger file
  steps:
  - label: write
    image: alpine
    command: ['/bin/sh', '-c', 'printf $STEMN_PIPELINE_EVENT > /pipeline/$STEMN_PIPELINE_EVENT.txt']
- label: check output
  steps:
  - label: cat
    image: alpine
    command: 
      - env
  - label: print some pretty things
    image: wernight/funbox
    command: ['sh -c "figlet funbox | boxes | toilet --gay -f term"']
- label: upload
  steps:
  - label: stemn
    image: stemn/upload:latest
    inputFiles:
    - '*.txt'
```

