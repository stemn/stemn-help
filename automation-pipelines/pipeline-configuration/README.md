# Pipeline configuration

## Meet the `*.pipeline` file

All of the configuration for your Automation Pipeline is contained within the `*.pipeline` file which is stored along side your other project files. There are 3 main concepts you need to understand before you can get going with your first `.pipeline` file.

{% page-ref page="pipeline-triggers.md" %}

If you understand these 3 concepts, you're ready to write your first pipeline configuration. FYI, you can have multiple `.pipeline` files in your project and even multiple in a single folder. Just call them different things such as `render.pipeline` or `document.pipeline`

{% hint style="info" %}
 The full pipeline schema is available at [schemas.stemn.com/pipeline+v1](https://schemas.stemn.com/pipeline+v1)
{% endhint %}

## Example Pipeline Configuration

For example. Add the following configuration to your project and save to a file called `stemn.pipeline`

```yaml
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

