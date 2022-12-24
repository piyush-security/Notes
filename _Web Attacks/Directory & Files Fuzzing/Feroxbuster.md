- - - 
```rust
sudo feroxbuster -u http://jeff.thm/admin/ -x pdf -x js,html -x php,txt,zip,html
```

```ruby
feroxbuster -u $URL  -g -w /usr/share/seclists/Discovery/Web-Content/raft-large-words-lowercase.txt --force-recursion  -x pdf -x js html -x php txt json  -x zip
```

