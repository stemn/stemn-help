# Custom Images

## When to create a custom image?

First, you should browse through the catalog of [stemn ](stemn.md)and [3rd party images](3rd-party.md). If what you need to do is not there or is very niche/proprietary, you'll probably need to create your own image.

Keep in mind, if you just want to execute a few simple scripts, you can use a base operating system image such as [alpine ](https://hub.docker.com/r/_/alpine/)or [ubuntu](https://hub.docker.com/_/ubuntu/) and then use the [step command](../../commands.md#scripting) field to execute your script. If you find yourself doing lots of configuration, installing lots of packages and programs, it could be a good idea to create your own image.

## How to create a custom image

Things are gonna get pretty technical here. In order to create an image you'll need to get pretty familiar with exactly what an image is. 

{% hint style="info" %}
Remember, you can configure your custom images with [commands](../../commands.md). Keep that in mind when created your own image.
{% endhint %}

## Other images

{% page-ref page="3rd-party.md" %}

