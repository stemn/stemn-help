# Input Files

## Usage

Often you will want to use a step to operate on some files in your project. This is particularly true if your step is describing a file conversion or a report to generate from other files. By default, none of your project files will be accessible unless you say they should be. This is where the `inputFiles` property comes into play.

{% hint style="warning" %}
Only make the files you need accessible. Using wildcards when not required can make running your pipeline much slower \(particularly when there are very large files in your project\).
{% endhint %}

### Single:

```yaml
...
steps:
- label: List the available files
  image: alpine
  command: ls
  inputFiles: ./somefile.txt # A file with this name (relative to the .pipeline file)
...
```

### Multiple \(relative and absolute paths\):

```yaml
...
steps:
- label: List the available files
  image: alpine
  command: ls
  inputFiles: 
  - somefile.txt # A file with this name (relative to the root of the project)
  - output/someotherfile.md # This one also (relative to the root of the project)
...
```

{% hint style="info" %}
By adding `./` we are looking for files relative to the `.pipeline` file. Otherwise, it is relative to the `root` of the project folder.
{% endhint %}

### Wildcards:

```yaml
...
steps:
- label: List the available files
  image: alpine
  command: ls
  inputFiles: 
  - ./*.pdf  # All pdfs in the folder (relative to the .pipeline file)
  - ./**.pdf # All pdfs in child folders also (relative to the .pipeline file)
  - ./*      # All files in the folder (relative to the .pipeline file)
  - **       # All files in the project (relative to the project root)
...
```

### Advanced glob matching:

We actually support all forms of [glob matching](https://github.com/isaacs/minimatch) \(brace expansion,  extended glob matching and globstar matching\). Let the internet be your guide.

