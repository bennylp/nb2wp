# nb2wp - Convert Jupyter Notebook to Wordpress.com HTML

This `np2wp` utility converts Jupyter notebooks to plain HTML suitable for Wordpress.com. Note the difference between **Wordpress.com** service and Wordpress.org platform. The Wordpress.com is much stricter (no arbitrary plugins, no scripts, no CSS, no data: URI, etc.).

This utility does the following:
- convert .ipynb to HTML using [nbconvert](https://nbconvert.readthedocs.io/en/latest/) using selected template (full, basic, or custom)
- convert the CSS to inline style using [pynliner](https://pythonhosted.org/pynliner/) so that the style will be honoured by Wordpress. By default it replaces the CSS given by nbconvert with custom and simpler `style.css` that can be inlined by pynliner.
- extract embedded images (such as ones produced by Matplotlib) and local images to `img` directory. You need to upload this `img` directory somewhere and provide URL prefix for the images.
- convert Latex directives to Wordpress.com Latex directives.

Then you need to do some manual works:
- copy-paste the HTML inside the `<body>` to Wordpress HTML editor
- upload the image directory.

Open the **[Readme.ipynb](Readme.ipynb)** for more info. And see [how that notebook looks like in Wordpress blog](https://indoml.com/2019/09/24/converting-jupyter-notebook-to-wordpress-com-html/)
