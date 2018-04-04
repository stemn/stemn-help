---
description: These will control when your pipeline runs
---

# Pipeline Triggers

## How to use triggers

Your Automation Pipeline will only run when the conditions defined by your triggers are met. Typically, you'll want to trigger your pipeline when there are either revisions or commits made a specific file \(or files of a special file type\). This sort of logic is easily achieved with triggers.

You may also want to trigger your Pipeline to run according to a cron schedule. For example, every day at 5pm. This functionality is not yet supported \(but it is planned\).

## How to define triggers

The triggers section contains a list of `file` and `type` triggers. The full JSON schema with all possibilities is available [here](http://schemas.stemn.com/pipeline/triggers+v1).

```text
triggers:
- files: *.stl
  type: revision
- files: documentation.txt
  type: commit
```

Becoming a super hero is a fairly straight forward process:

```
$ give me super-powers
```

{% hint style="info" %}
 Super-powers are granted randomly so please submit an issue if you're not happy with yours.
{% endhint %}

Once you're strong enough, save the world:

```
// Ain't no code for that yet, sorry
echo 'You got to trust me on this, I saved the world'
```



