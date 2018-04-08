# Step Images

## Wait... What do you mean 'image'?

When we say 'image' we are referring to a [docker image](https://docs.docker.com/glossary/?term=image). Think of this a snapshot of an operating system with various programs installed and configured to run a specific task. There are thousands of free images available, typically for tasks that can be achieved with open-source operating systems or code.

## Step Images

There are 3 types of step images. Most simple tasks can be achieved using an image provided by us or a 3rd party images from dockerhub. Browse these first. If you can't find what you are looking for, you should read about creating your own [custom step image](custom.md) \(you'll need to write some code and learn more about docker images for this\).

### Browse images:

{% page-ref page="stemn.md" %}

{% page-ref page="3rd-party.md" %}

{% page-ref page="custom.md" %}

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

