# Pipeline Step Image

## Step Images

There are 3 types of step images. Many simple tasks can be achieved using a Stemn or 3rd party image. Browse these first. If you can't find what you are looking for, you should read about creating your own [custom step image](custom-steps.md) \(you'll need to write some code for this\).

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
    image: stemn/upload # <--- url or name
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

