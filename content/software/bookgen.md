---
title: "BookGen"
version: "1.0.2"
license: "GPLv3"
author: "Oliver Weissbarth"
platform: "Blender"
language: "english"
description: "A free Blender-Addon to generate books. It makes it easy to generate large amount of books using randomization without loosing control."
repository: "https://github.com/oweissbarth/bookGen"
tagline: "Generate Books. Quick and easy."
icon: "images/software/bookgen/bookgen_icon.png"
images: ["images/software/bookgen/render2.jpg", "images/software/bookgen/blender.png", "images/software/bookgen/render_close.jpg", "images/software/bookgen/panel.png"]
download_id: "22a46970-fc15-427b-b75f-4a97af814dc8"
weight: 1
---

BookGen is a free book-generation addon for the open-source 3D-package Blender. It allows you to fill shelves or create stacks of books – fast and easily.

BookGen 1.0.0 is only compatible with Blender versions higher than 2.80. An older version that is compatible with Blender 2.7x can be downloaded here: [bookGen Blender 2.7x]({{< staticsitecompanion >}}/download/{{< param "download_id" >}}?version=0.6)
## Features:
- Fill shelves or create stacks of books
- control width, height, depth, cover thickness and more parameters of the books
- use randomization to generate a variety of different books
- parametric UV-Map for texturing

## Installation:
- Download the .zip
- Open Blender, click on “Edit” and open the “Preferences”
- Switch to the addons-tab and click on “install from File”
- Choose the .zip and click “install”
- Now Activate it by clicking on the checkbox next to it. Done.

## Tutorial:
{{< youtube E8BwTPQRqO0 >}}

## Getting started:

After you installed the Blender addon as described above you will find a new tab in the right hand sidebar of the 3D-Viewport.

You can define a new shelf by clicking on “Add shelf”. Now left click inside the 3D-View where you want your shelf to start, left click again to set the end point.

Books will automatically be generated to fill the selected shelf.

At any time the parameters of all shelfs can be adjusted by using the panels: “Properties”, “Leaning”, “Proportions” and “Details”.
## Options:
### Properties

At the top of the “Properties” panel you will find settings affecting all books:

    Scale: Allows to change the overall size of the books
    Seed: Allows to generate different variations from the same settings
    Alignment: Allows to align the books at the spine, fore edge or center
    Material: Allows to assign a existing material to all books

### Leaning

In the “Leaning” panel you find settings to add books that have fallen over:

    Lean Amount: Defines the overall number of leaning books. 1 means all books are leaning.
    Lean Direction: Defines the direction in which books are leaning. 0 mean equally left and right.
    Lean Angle: Define the average angle at which books are leaning.

### Proportions

The “Proportions” panels contains settings to change the overall shape of your books:

    height: changes the height of your books.
    depth: changes the depth of your books.
    width: changes the width of your individual books.

### Details

The “Details” panel changes the smaller features of the generated books:

    textblock-offset: changes the offset between cover size and textblock size
    cover-thickness: changes the thickness of the books covers
    spline-curl: changes how bulgy the back of the books are.
    hinge-inset: changes the inset at the hinge
    hinge-width: changes the width of the hinge
    Add Subsurf-Modifier: adds a subdivision surface modifier to your books.

## License:

© Copyright Oliver Weissbarth 2014-2021. This addon is licensed under GPLv3.
Issues:

If you do find any bugs please use the issue tracker, email me at mail@oweissbarth.de or use the contact form at www.oweissbarth.de/contact.