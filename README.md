# Test nginx relative path lookup of include directives

1. Clone repo in a folder of your choice which we call `$parent_dir`, e.g.
   `/home/ur5us/dev/`
2. Run the following command (from anywhere):
   `nginx -T -c $parent_dir/nginx_config_test/nginx/nginx.conf -p $parent_dir/nginx_config_test/prefix_dir/`

This will test and echo the entire configuration. The last line shows that
`include` is relative to parent folder of `nginx.conf`:

```
# configuration file /home/ur5us/dev/nginx_config_test/nginx/sites-enabled/test.localhost.conf:
server {
  listen 8080;
  server_name test.localhost;

  include relative_file.conf;
}

# configuration file /home/ur5us/dev/nginx_config_test/nginx/relative_file.conf:
```
