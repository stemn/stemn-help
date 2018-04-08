# Pipeline Step Command

## a

a

## Usage

Commands can be entered as either an array of sequential commands or a single line. 

For example:

```yaml
...
stages:
- label: Example Stage
  steps:
  - label: Example Step
    image: wernight/funbox
    command: asciiquarium
...
```

Sequential commands:

{% code-tabs %}
{% code-tabs-item title="stemn.pipline" %}
```yaml
...
stages:
- label: Example Stage
  steps:
  - label: Example Step
    image: wernight/funbox
    command: asciiquarium
...
```
{% endcode-tabs-item %}
{% endcode-tabs %}

