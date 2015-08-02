# viewerjs
This is the Javascript application **github.com/kogmbh/ViewerJS**, packaged as a *Django application*.

I've reorganized the directory structure of ViewerJS in order to be able to integrate it in a Django project as an application.
I had to change only the content of index.html: did so by adding as first line

    {% load staticfiles %}

and by using the following 2 regular expressions in the Eclypse editor:

    search:  images\/([\w\-]+)\.png
    replace: {% static "viewerjs/images/$1\.png" %}

    search:  \.\/([\w\-]+)\.js
    replace: {% static "viewerjs/$1\.js" %}

in the same file, I had to make this other change, manually:

    - PDFJS.workerSrc="viewerjs/pdf.worker.js"
    + PDFJS.workerSrc="{% static "viewerjs/pdf.worker.js" %}"

In future I will try to understand how to keep this repository aligned with the original one.
