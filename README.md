Custom Package 
--------------

How to build
#Open Terminal

```
echo >> feeds.conf.default
echo 'src-git custompackage https://github.com/faiz007t/custom-package.git' >> feeds.conf.default
```

#Update Feeds
```
./scripts/feeds update -a
./scripts/feeds install -a
```
----------
