# Example Pipelines

Here are a few examples of full pipeline configurations. They should help you get your head around the sorts of things you can do and how they are achieved.

## Convert a CAD file and save it to your project

```yaml
$schema: https://schemas.stemn.com/pipeline+v1

label: Matches a file to each trigger type...

triggers:
- files: commit.txt
  type: commit

stages:
- label: write trigger type to trigger file
  steps:
  - label: write
    image: alpine
    command: ['/bin/sh', '-c', 'printf $STEMN_PIPELINE_EVENT > /pipeline/$STEMN_PIPELINE_EVENT.txt']
- label: Print some pretty things
  steps:
  - label: cat
    image: alpine
    command: 
      - env
  - label: Rainbow
    image: wernight/funbox
    command: ['/bin/sh', '-c', 'figlet funbox | boxes | toilet --gay -f term']
  - label: Nyan Cat
    image: wernight/funbox
    command: ['/bin/sh', '-c', 'nyancat']
  - label: Aquarium
    image: wernight/funbox
    command: ['/bin/sh', '-c', 'asciiquarium']
- label: Upload output to stemn
  steps:
  - label: stemn
    image: stemn/upload:latest
    inputFiles:
    - '*.txt'
```

## Convert a CadQuery script, save and email the output 

```yaml
$schema: https://schemas.stemn.com/pipeline+v1

label: Matches a file to each trigger type...

triggers:
- files: commit.txt
  type: commit

stages:
- label: write trigger type to trigger file
  steps:
  - label: write
    image: alpine
    command: ['/bin/sh', '-c', 'printf $STEMN_PIPELINE_EVENT > /pipeline/$STEMN_PIPELINE_EVENT.txt']
- label: Print some pretty things
  steps:
  - label: cat
    image: alpine
    command: 
      - env
  - label: Rainbow
    image: wernight/funbox
    command: ['/bin/sh', '-c', 'figlet funbox | boxes | toilet --gay -f term']
  - label: Nyan Cat
    image: wernight/funbox
    command: ['/bin/sh', '-c', 'nyancat']
  - label: Aquarium
    image: wernight/funbox
    command: ['/bin/sh', '-c', 'asciiquarium']
- label: Upload output to stemn
  steps:
  - label: stemn
    image: stemn/upload:latest
    inputFiles:
    - '*.txt'
```

## Run a bash script that prints some ascii art



## Send a notification to your slack channel

