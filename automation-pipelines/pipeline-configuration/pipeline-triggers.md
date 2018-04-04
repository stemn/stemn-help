---
description: These will control when your pipeline runs
---

# Pipeline Triggers

## How to use triggers

Your Automation Pipeline will only run when the conditions defined by your triggers are met. Typically, you'll want to trigger your pipeline when there are either revisions or commits made a specific file \(or files of a special file type\). This sort of logic is easily achieved with triggers.

You may also want to trigger your Pipeline to run according to a cron schedule. For example, every day at 5pm. This functionality is not yet supported \(but it is planned\).

## How to define triggers

The triggers section contains a list of `file` and `type` triggers. For example:

```yaml
...
triggers:
- files: *.stl
  type: revision
- files: documentation.txt
  type: commit
...
```

More specifically, the supported options are:

| **Key** | **Description** |
| --- | --- | --- |
| files | Wildcard selector. eg\) `*.txt` or  `wheel_hub.stl`or `docs/summary.docx` |
| type | Event type. eg\) `commit `or `revision` |

{% hint style="info" %}
The full schema with all possibilities is available at [schemas.stemn.com/pipline/triggers+v1](http://schemas.stemn.com/pipeline/triggers+v1)
{% endhint %}





