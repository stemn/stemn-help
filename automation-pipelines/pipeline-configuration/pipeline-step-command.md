# Pipeline Step Command

## Usage

Commands can be entered as either an array of sequential commands or a single line. These commands will be executed as soon as the image has loaded. They can be used to either configure your image or to outline a series of sub-steps.

{% hint style="info" %}
Make sure you read about the commands your custom image accepts or expects.
{% endhint %}

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
These 2 examples are using the [wernight/funbox](https://hub.docker.com/r/wernight/funbox/) image from docker hub. You can run these in your pipline and you should get some pretty ascii art in your pipeline's terminal output. Note, these commands are documented on the docker hub page above.
{% endhint %}

### Scripting

You can also use standard linux commands along with a linux image such as [alpine](https://hub.docker.com/_/alpine/):

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

Or, you can also install packages and run script files.

```yaml
...
stages:
- label: Example Stage
  steps:
  - label: Example Step
    image: python # Note, this is a python image from dockerhub
    command: 
      - pip install --no-cache-dir -r requirements.txt
      - python some-program.py
...
```



