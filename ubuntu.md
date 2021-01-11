# [2일차] 우분투 리눅스 20.04 LTS 설치

## 1. 설치파일 다운로드

### 1.1. 우분투 리눅스 iso 파일 다운로드

[Ubuntu 20.04 LTS](https://ubuntu.com/download/desktop/thank-you?version=20.04.1&architecture=amd64)

### 1.2. 가상화 소프트웨어 다운로드

[VMware Fusion](https://www.vmware.com/kr/products/fusion/fusion-evaluation.html)

[VirtualBox](https://www.virtualbox.org/wiki/Downloads)

## 2. 유튜브 동영상 설명자료

[VMware에 Ubuntu 설치하기](https://www.youtube.com/watch?v=3AoSIIXUaM8)

### 유튜브 동영상을 참고하여 우분투 리눅스 20.04 LTS를 설치한다.

## 3. 이더리움 설치

```bash
$ sudo apt-get install software-properties-common
# 소프트웨어 필수 프로그램 설치
$ sudo add-apt-repository -y ppa:ethereum/ethereum
$ sudo apt-get update
# 이더리움 저장소 추가 및 패키지 업데이트
$ sudo apt-get install ethereum
# 이더리움 설치
```

## 4. 제니시스 설정 파일 작성

```bash
$ nano ./genesis.json
```

### 최초 블록 생성을 위한 설청파일 작성

```bash
{
    "config": {
        "chainId" : 15,
        "homesteadBlock" : 0,
        "eip155Block" : 0,
        "eip158Block" : 0
    },
    {
        "difficulty" : "200000000",
        "gasLimit" : "3100000",
        "alloc":{

        }
    }

}
```

## 5. 이더리움 프라이빗 네트워크 접속

```bash
$ mkdir private-data
$ geth --datadir "private-data" init genesis.json
$ geth --datadir "private-data" --networkid 15 console
```
