- - -
**Useful Link :** **[https://man7.org/linux/man-pages/man7/capabilities.7.html](https://man7.org/linux/man-pages/man7/capabilities.7.html)**
- - -

## Theory :
Starting with kernel **2.2**, Linux divides the privileges traditionally associated with superuser into distinct units, known as capabilities, which can be independently enabled and disabled.
Capabilities are a per-thread attribute.

### How To Hunt : 
we can use automated tools like linpeas, linenum, etc.
or can do manualy :

```sh
getcap -r / 2>/dev/null
```

### Thing to Note :
When you run the above command then note the result.

• Is there any “**setuid**” is set.
• Is there any **“+ep**” is set which means permit everything.

- - -

