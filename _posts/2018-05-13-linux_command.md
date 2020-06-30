---
title: 리눅스 알아두면 좋은 커맨드
tags: linux
key: page-linux_basic
cover: /assets/cover/linux.png
---
## 정렬하지 않고 유니크한 부분만 출력하기
```console
$ awk '!x[$0]++ {print $0}' my_file.txt
$ cat my_file.txt | awk '!x[$0]++'
```

## 정렬하면서 유니크한 부분 출력하기
```console
$ cat my_file.txt | sort -u
```

