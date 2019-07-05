---
title: 파이썬 설치 및 2.7 3.6 차이 설명
tags: python
key: page-python_install
cover: /assets/cover/python.png
---

```console
# yum install -y https://centos7.iuscommunity.org/ius-release.rpm
# yum update
# yum search python36
# yum install -y python36u python36u-devel python36u-libs python36u-pip
# rm -i /usr/bin/python 
# ln -s /usr/bin/python3.6 /usr/bin/python
```

* 위의 방법으로 할 시 yum 실행시 python2.4로 인지되었던게 사라져서 작동이 안 되니 5번째 명령어부터는 안 쓰는게 좋을 수 있다.

[참고 사이트](https://pentestlab.tistory.com/57)