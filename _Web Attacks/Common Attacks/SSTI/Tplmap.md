- - -
#### **Installation :**

```sh
git clone https://github.com/epinna/tplmap.git ; cd tplmap/ ; pip install -r requirements.txt
```

- - -

#### **Usage** **:**

**<u>GET Request</u> :**
```sh
./tplmap.py -u 'http://10.10.51.119/login?username=users&password=99999999'
```

**<u>POST Request</u> :**
```sh
./tplmap.py -X POST -d 'username=users&password=99999999' -u 'http://10.10.51.119/login'
``` 

