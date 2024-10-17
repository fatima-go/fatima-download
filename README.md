# Release
릴리즈 히스토리는 [RELEASE.md](RELEASE.md) 파일을 참고하세요

# LFS 설정
## Mac OSX
You may need to brew update to get all the new formulas
```shell
brew install git-lfs
```

## 사용법
해당 레포로 이동 후 아래와 같이 lfs 를 적용한다
```shell
$ git lfs install
```

파일을 관리하려면 track 을 사용하면 된다.<br>
먼저 기존에 git add 되어 버전관리되는 파일이 대상이라면 unstaging 을 진행한다
```shell
$ git rm --cached my_previous_large_file
```

다음으로 track 을 더해준다
```shell
$ git lfs track my_previous_large_file
```

다음으로 lfs 트래킹 정보는 .gitattributes 파일을 통해서 관리되므로 반드시 해당 파일을 add 해 주어야 한다
```shell
$ git add .gitattributes
```

마지막으로 다시 add 해 주도록 한다
```shell
$ git add my_previous_large_file
```

모든 정리가 끝났다. 적절한 코멘트와 함께 push를 진행한다

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
