# Pipeline Steps

## How to use steps

This is where the real meat \(or tofu\) of your pipeline config starts. Remember the image of a pipeline from the [stages ](../pipeline-stages.md)page? Each stage contains steps such as `Convert .sldprt to .stl` or `Email changes.pdf`. 

![](../../../.gitbook/assets/steps-stages%20%281%29.png)

These types of tasks are easily achieved with just a few lines of configuration in your `.pipeline`.

For example:

* Convert a file from 1 format to another
* Generate renders or reports
* Upload generated files to your project folder
* Email files to people or send
* Send a custom HTTP request to an API

Or even more complicated things such as:

* Run a CFD analysis for a CAD model
* Compile and test code
* Diff some files and add it to a changelog report
* Produce a Gerber file and email it to a PCB manufacturer 

You can actually achieve almost anything in a step. Some of these will be just a couple lines of configuration, others will need you to write some custom code.

## How it works

All pipeline steps are executed in the cloud on Stemn's automation pipeline servers. Each step actually spins up a Virtual Machine \(VM\) which runs some code along with any command you define in your step configuration. 

There are thousands of different VM 'images' that can be used to do common tasks with just 1 or 2 lines of configuration. You can also deploy your own [custom code](image/custom-images.md) as an 'image' \(using the website [hub.docker.com](https://hub.docker.com)\) and run that as part of your pipeline. We'll get into the details of this later on...

## How to define steps

Each step should contains a `label`, `image`and optionally a `command` and/or `inputFiles`. For example, to create the steps in **Stage 2** of the above example: 

```yaml
steps:
- label: Render .stl as .jpg
  inputFiles: *.stl
  image: stemn/cad-render
  command: convert -i *.sldstl -o output/*.jpg
- label: Generate changes.pdf
  inputFiles: *
  image: some-custom-docker/a-custom-docker-image-goes-here
  command: generate report.pdf
```

More specifically, the supported options are:

| **Key** | **Description** |
| --- | --- | --- | --- | --- |
| label | A string describing the stage. |
| image | The name of or url to a step image. [Learn more.](image/) |
| command \(optional\) | The command to run in the terminal after the image boots. [Learn more.](../command.md) |
| inputFiles \(optional\) | A wildcard selector for the files in your project you want to operate on. |

## Further Reading

{% page-ref page="image/" %}

{% page-ref page="../command.md" %}



