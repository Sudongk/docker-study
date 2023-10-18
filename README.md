﻿# docker-study

## env
    ec2 ubuntu

## install
  #### 도커와 관련된 패키지들을 제거
    for pkg in docker.io docker-doc docker-compose docker-compose-v2 podman-docker containerd runc; do sudo apt-get remove $pkg; done
    
  #### Ubuntu 리눅스 시스템에 도커 설치를 설치하기 위한 선행 명령어
    sudo apt-get update
    sudo apt-get install ca-certificates curl gnupg
    sudo install -m 0755 -d /etc/apt/keyrings
    curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
    sudo chmod a+r /etc/apt/keyrings/docker.gpg
    
    echo \
      "deb [arch="$(dpkg --print-architecture)" signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
      "$(. /etc/os-release && echo "$VERSION_CODENAME")" stable" | \
      sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
      
    sudo apt-get update

  #### 도커 최신 버전 설
    sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin


## command
  #### 컨테이너 실행(이미지 없을 경우 이미지 다운로드 후 컨테이너 실행, 태그가 없는 경우 디폴트로 latest로 다운로드)
    docker run {이미지 이름}    
