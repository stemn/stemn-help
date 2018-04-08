# Pipeline Triggers

## How to use triggers

Your Automation Pipeline will only run when the conditions defined by your triggers are met. Typically, you'll want to trigger your pipeline when there are either [revisions ](../../untitled/file-revisions-and-commits.md)or [commits ](../../untitled/commits.md)made to a specific file or file type. This type of logic is easily achieved with triggers.

You may also want to trigger your Pipeline to run according to a cron schedule. For example, every day at 5pm. This functionality is not yet supported \(but it is planned\).

## How to define triggers

The triggers section contains a list of `file` and `type` triggers. For example:

```yaml
...
triggers:
- files: ./*.stl # Any stl files in the folder (relative the the .pipeline file)
  type: revision
- files: documentation.txt # Relative to the root of the project
  type: commit
- files: ** # Every file in the project
  type: commit
...
```

This config contains 2 triggers. The pipeline will run if either of the 2 conditions are met:

* There is a revision to any `stl `file in the same folder as the `.pipeline` file
* There is a commit to the `documentation.txt` file

More specifically, the supported options are:

| **Key** | **Description** |
| --- | --- | --- |
| files | File selector.  Full [glob matching](https://github.com/isaacs/minimatch) support. Let the internet be your guide |
| type | Event type. eg\) `commit `or `revision` |

{% hint style="info" %}
The full schema with all possibilities is available at [schemas.stemn.com/pipline/triggers+v1](http://schemas.stemn.com/pipeline/triggers+v1)
{% endhint %}





