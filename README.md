# Release
릴리즈 히스토리는 [RELEASE.md](RELEASE.md) 파일을 참고하세요

# 운영 패키지 다운로드

| Platform                                                                                                 | URL                                                                                           |
|----------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------|
| [linux-arm64](https://github.com/fatima-go/fatima-download/raw/main/fatima-package.linux-arm64.tar.gz)   | wget https://github.com/fatima-go/fatima-download/raw/main/fatima-package.linux-arm64.tar.gz  |
| [linux-amd64](https://github.com/fatima-go/fatima-download/raw/main/fatima-package.linux-amd64.tar.gz)   | wget https://github.com/fatima-go/fatima-download/raw/main/fatima-package.linux-amd64.tar.gz  |
| [darwin-arm64](https://github.com/fatima-go/fatima-download/raw/main/fatima-package.darwin-arm64.tar.gz) | wget https://github.com/fatima-go/fatima-download/raw/main/fatima-package.darwin-arm64.tar.gz |
| [darwin-amd64](https://github.com/fatima-go/fatima-download/raw/main/fatima-package.darwin-amd64.tar.gz) | wget https://github.com/fatima-go/fatima-download/raw/main/fatima-package.darwin-amd64.tar.gz |

자신의 플랫폼에 맞는 패키지를 다운로드 후 적당한 폴더에 압축 해제

```shell
$ wget https://github.com/fatima-go/fatima-download/raw/main/fatima-package.darwin-arm64.tar.gz
--2023-06-23 12:14:05--  https://github.com/fatima-go/fatima-download/raw/main/fatima-package.darwin-arm64.tar.gz
Resolving github.com (github.com)... 20.200.245.247
Connecting to github.com (github.com)|20.200.245.247|:443... connected.
HTTP request sent, awaiting response... 302 Found
Location: https://raw.githubusercontent.com/fatima-go/fatima-download/main/fatima-package.darwin-arm64.tar.gz [following]
--2023-06-23 12:14:05--  https://raw.githubusercontent.com/fatima-go/fatima-download/main/fatima-package.darwin-arm64.tar.gz
Resolving raw.githubusercontent.com (raw.githubusercontent.com)... 185.199.108.133, 185.199.109.133, 185.199.110.133, ...
Connecting to raw.githubusercontent.com (raw.githubusercontent.com)|185.199.108.133|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 49513244 (47M) [application/octet-stream]
Saving to: ‘fatima-package.darwin-arm64.tar.gz’

fatima-package.darwin-arm64.tar.gz        100%[===================================================================================>]  47.22M  23.3MB/s    in 2.0s

2023-06-23 12:14:10 (23.3 MB/s) - ‘fatima-package.darwin-arm64.tar.gz’ saved [49513244/49513244]

$ gzip -cd fatima-package.darwin-arm64.tar.gz | tar xvf -
x fatima-package/
x fatima-package/app/
x fatima-package/bin/
... 
```
