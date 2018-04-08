# Pipeline Step Image

## Wait... What do you mean 'image'?

When we say 'image' we are referring to a [docker image](https://docs.docker.com/glossary/?term=image). Think of this a snapshot of an operating system with various programs installed and configured to run a specific task. Creating your own custom docker images can be a pretty technical task, thankfully, there are thousands of open-source images that allow you to complete most common tasks. 

## Step Images

There are 3 types of step images. Most simple tasks can be achieved using a Stemn or 3rd party image from dockerhub. Browse these first. If you can't find what you are looking for, you should read about creating your own [custom step image](custom-steps.md) \(you'll need to write some code and learn more about docker images for this\).

{% page-ref page="stemn-steps.md" %}

{% page-ref page="3rd-party-steps.md" %}

{% page-ref page="custom-steps.md" %}

## Usage

After you know the name of the image you want to use. Just paste the string or url path into the step's image section:

```yaml
...
stages:
- label: An example stage
  steps:
  - label: An example step
    image: wernight/funbox # <--- url or name
    command: asciiquarium
...
```

or

```yaml
...
stages:
- label: An example stage
  steps:
  - label: An example step
    image: https://hub.docker.com/r/wernight/funbox/ # <--- url or name
    command: asciiquarium
...
```

