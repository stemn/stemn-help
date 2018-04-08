# Pipeline Step Command

## Usage

Commands can be entered as either an array of sequential commands or a single line. 

For example:

```yaml
...
stages:
- label: Example Stage
  steps:
  - label: Will print some ascii art to the terminal
    image: wernight/funbox
    command: asciiquarium
...
```

Sequential commands:

```yaml
...
stages:
- label: Example Stage
  steps:
  - label: Will print 2 lots of ascii art to the terminal
    image: wernight/funbox
    command: 
      - asciiquarium
      - nyancat
...
```

{% hint style="info" %}
These 2 examples are using the [wernight/funbox](https://hub.docker.com/r/wernight/funbox/) image from docker hub. You can run these in your pipline and you should get some pretty ascii art in your pipeline's terminal output.
{% endhint %}

You can use standard linux commands along with a linux image such as [alpine](https://hub.docker.com/_/alpine/):

```yaml
...
stages:
- label: Example Stage
  steps:
  - label: Example Step
    image: alpine
    command: 
      - ls
      - cp file.txt output/file.txt
      - curl 'http://stemn.com/api/v1/version' -H --compressed
...
```

