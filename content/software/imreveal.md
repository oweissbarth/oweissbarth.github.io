---
title: "ImReveal"
version: "1.0.1"
license: "MIT License"
author: "Oliver Weissbarth"
platform: "Browser/Javascript"
language: "-"
description: "A bit of Javascript to show the before and after of two images"
repository: "https://github.com/oweissbarth/imReveal"
tagline: "Show the difference!"
icon: "images/software/imreveal/imreveal_icon.png"
download_id: "22a46970-fc15-427b-b75f-4a97af814dc8"
weight: 2
---

A bit of js to show the “before and after” of two images
{{< includeimreveal >}}
{{< imreveal uid="demo" imgLeft="images/software/imreveal/imreveal_demo_left.jpg" imgRight="images/software/imreveal/imreveal_demo_right.jpg" >}}
## Usage

Simply include the imReveal js and css files into your page. Your two image should be wrapped by a container. Then simply create a new imReveal object by passing it the wrapper HTMLElement.

{{< highlight html >}}
<script src="imReveal.min.js"></script>
<link rel="stylesheet" href="imReveal.css"/>
...
<div id="myCustomId">
  <img src="path/to/left/image.jpg"/>
  <img src="path/to/right/image.jpg"/>
</div>
<script> document.onload.addEventListener(()=>{
  var ir = new imReveal(window.myCustomId);
  });
</script>
{{< /highlight >}}


## Troubleshooting

imReveal should pick up layout changes on the page and update accordingly. However if it doesn’t you can manually refresh it by calling reinit() on the imReveal object.
License

imReveal is licensed under the MIT license.