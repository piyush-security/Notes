## PHP  
```php
php -S 127.0.0.1:8080
```

```php
php -S 0:8000
```


## Python 

```python
python -m SimpleHTTPServer 8000  # python 2
```

```python
python -m http.server 8000    # python 3
```

## Ruby 

```ruby
ruby -rwebrick -e'WEBrick::HTTPServer.new(:Port => 8000, :DocumentRoot => Dir.pwd).start'
```

```ruby
ruby -run -ehttpd . -p8080
```


