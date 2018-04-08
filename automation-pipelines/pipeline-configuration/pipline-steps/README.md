# Pipline Steps

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

## How to define steps

a

```yaml
stages:
- label: Build CAD Files
  steps:
  - label: Convert .sldprt to .stl
    inputFiles: *.sldprt
    image: stemn/cad-convert
    command: convert -i *.sldprt -o *.stl
```

## Examples



