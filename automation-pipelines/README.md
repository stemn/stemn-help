# Automation Pipelines

## What is an Automation Pipeline?

A pipeline is a series of tasks you configure to run in cloud on Stemn's pipeline servers. For example:

* Convert a file from one format to another
* Render a CAD model and save the output images
* Generate Gerber files whenever a PCB design is modified
* Run a computational fluid dynamics analysis and generate a report
* Compile and test code
* Send an email with file changes to a client or stakeholder
* Run a shell or batch script

These types of tasks \(and many more\) can be chained together in various 'stages' of the pipeline. You can also define triggers so the pipeline only runs when a particular file is being [revised ](../files-and-syncing/revisions.md)or [committed](../files-and-syncing/commits.md).

![After a pipeline is triggered, the status of the pipeline and output files will be visible on the &apos;piplines&apos; tab of your project.](../.gitbook/assets/2018-04-08-13_08_47-gear-changes_.png)

## Pipeline Configuration

You can configure any number of different automation pipelines for your project. Learn how:

{% page-ref page="pipeline-configuration/" %}

## Example Pipelines

Once you understand how a exactly how a pipeline is configured, continue on to the examples:

{% page-ref page="example-pipelines.md" %}



