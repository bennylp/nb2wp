# nb2wp

This little utility converts Jupyter notebook to HTML suitable for Wordpress.com. Note the difference between **Wordpress.com** service and Wordpress.org platform. The Wordpress.com service is a lot more strict, for example:
- you cannot install arbitrary plugins on Wordpress.com.
- your HTML will be heavily sanitized. No script execution. CSS support is very limited (there is some CSS support in the new Block editor). Your output will be converted to themed, and thus some display will be broken (for example dataframe table).
- image with `data:` URI is not supported (the `data:` URI will be removed). This breaks all matplotlib graphics.

Therefore many existing solutions for displaying or converting notebook to Wordpress will not work:
- solutions that require installing Wordpress plugin (such as nbconvert) will not work
- solutions that puts raw HTML most likely will not work because of its dependencies to CSS and scripts.

The only thing that works is to duplicate your notebook to Gist and embed the gist page in Wordpress.com. The output is not ideal though, since you only have your notebook inside a small frame, and also it requires you to duplicate your notebook in gist (there is a solution though to automate this gist-ing thing from your Jupyter). But overall, the user experience is not as good as reading a blog.
