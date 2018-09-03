## Introduction
This is a build of gcc 6.3.0 .so library file to fix the error below.

## How to fix error "/lib64/libstdc++.so.6: version 'GLIBCXX_3.4.20' not found"
```bash
wget https://raw.githubusercontent.com/leomoon-studios/libstdc-.so.6.0.22/master/libstdc%2B%2B.so.6.0.22_centos.tar.gz -O /tmp/libstdc.tar.gz #download this build
tar -xzf /tmp/libstdc.tar.gz #extract it
mv /tmp/libstdc++.so.6.0.22 /usr/lib64/libstdc++.so.6.0.22 #move it to /usr/lib64
rm -rf /tmp/libstdc.tar.gz #remove the downloaded file
ls -alF libstdc++.so.6* #list all libstdc++
rm libstdc++.so.6 #remove the old symlink
ln -s libstdc++.so.6.0.22 libstdc++.so.6 #make a new symlink to the new build
ls -alF /usr/lib64/libstdc++.so.6* #check that the new sylink
strings /usr/lib64/libstdc++.so.6 | grep GLIB #check if GLIBCXX_3.4.20 exists now
```
## Compatibility
Tested with CentOS 7.5