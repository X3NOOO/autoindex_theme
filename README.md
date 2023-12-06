# autoindex_theme

Custom themes for nginx autoindex

## Live preview

Live preview is avaliable [here](https://files.ksenon.net).

## Installation

1. `git clone https://github.com/X3NO/autoindex_theme /path_to_your_website/.autoindex_theme`
2. Add the following lines to your nginx configuration file:

```nginx
autoindex on;
add_before_body /.autoindex_theme/before.html;
sub_filter '<html>' '';
sub_filter '<body>' '';
sub_filter '<hr>' '';
sub_filter '</pre><hr></body>' '</pre></body>';
sub_filter_once on;
location / {
        try_files $uri $uri/ =404;
}
error_page 404 /.autoindex_theme/404.html;
```
