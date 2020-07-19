---
description: Docker + Maria DB Tutorials for Windows 10 user
---

# Docker + Maria DB Tutorial

### Maria DB 이미지 사용법

```text
$ docker pull mariadb
```

```text
$ docker run --name some-mariadb -e MYSQL_ROOT_PASSWORD=my-secret-pw -d mariadb:tag
```

* [`10.5.4-focal`, `10.5-focal`, `10-focal`, `focal`, `10.5.4`, `10.5`, `10`, `latest`](https://github.com/docker-library/mariadb/blob/8ec795570021bdcf933a60d13b4631912634a5cc/10.5/Dockerfile)
* [`10.4.13-focal`, `10.4-focal`, `10.4.13`, `10.4`](https://github.com/docker-library/mariadb/blob/8ec795570021bdcf933a60d13b4631912634a5cc/10.4/Dockerfile)
* [`10.3.23-focal`, `10.3-focal`, `10.3.23`, `10.3`](https://github.com/docker-library/mariadb/blob/8ec795570021bdcf933a60d13b4631912634a5cc/10.3/Dockerfile)
* [`10.2.32-bionic`, `10.2-bionic`, `10.2.32`, `10.2`](https://github.com/docker-library/mariadb/blob/8ec795570021bdcf933a60d13b4631912634a5cc/10.2/Dockerfile)
* [`10.1.45-bionic`, `10.1-bionic`, `10.1.45`, `10.1`](https://github.com/docker-library/mariadb/blob/8ec795570021bdcf933a60d13b4631912634a5cc/10.1/Dockerfile)

[실행 중인 컨테이너에 직접 접근하기 위해 Container ID를 확인한다.](https://github.com/docker-library/mariadb/blob/8ec795570021bdcf933a60d13b4631912634a5cc/10.1/Dockerfile)

```text
$ docker ps
```

```text
$ docker exec -it CONTAINER_ID bash
```

```text
$ mysql -u root -p
```

[관리자 아이디, 비밀번호를 입력해서 관리자 페이지에 접속한다.](https://github.com/docker-library/mariadb/blob/8ec795570021bdcf933a60d13b4631912634a5cc/10.1/Dockerfile)

[먼저 포트포워드 설정을 위해 공유기 설정 페이지로 들어간다. ipTIME의 기본 공유기 설정 페이지는 192.168.0.1이다.](https://github.com/docker-library/mariadb/blob/8ec795570021bdcf933a60d13b4631912634a5cc/10.1/Dockerfile)

[이 글에서는 ipTIME 공유기를 기준으로 포트포워드, DDNS 설정 방법을 설명한다.](https://github.com/docker-library/mariadb/blob/8ec795570021bdcf933a60d13b4631912634a5cc/10.1/Dockerfile)

[공유기를 사용한 네트워크 환경의 서버에서 외부 접속을 허용하기 위해서는 몇 가지 설정이 필요하다. 포트포워드 설정은 필수이고, DDNS 설정을 해주면 외우기 힘든 IP를 사용하지 않고 서버에 접근하는 것이 가능하기 때문에 권장한다. 서버로 사용할 PC는 고정아이피를 할당해 주어야 한다. 물론 고정아이피를 할당하지 않더라도 제대로 동작하는 것 처럼 보일 수 있지만, IP가 갱신되며 서버에 접근이 어려워질 수 있다.](https://github.com/docker-library/mariadb/blob/8ec795570021bdcf933a60d13b4631912634a5cc/10.1/Dockerfile)

\*\*\*\*[**외부 접속을 위한 공유기 설정**](https://github.com/docker-library/mariadb/blob/8ec795570021bdcf933a60d13b4631912634a5cc/10.1/Dockerfile)\*\*\*\*

[![Datagrip02](https://github.com/kusakina0608/Gitbook/blob/master/.gitbook/assets/datagrip02.png?raw=true)](https://github.com/docker-library/mariadb/blob/8ec795570021bdcf933a60d13b4631912634a5cc/10.1/Dockerfile)

[드라이버가 없어서 실패한 경우에는 자동으로 드라이버를 설치하겠다는 안내 창이 나오는데, 수락한 뒤 다시 Test Connection을 누르면 서버에 정상적으로 접속되는 것을 확인할 수 있다.](https://github.com/docker-library/mariadb/blob/8ec795570021bdcf933a60d13b4631912634a5cc/10.1/Dockerfile)

[실패한 경우는 Host/ID/PW를 잘못 입력했거나 드라이버가 없기 때문이다.](https://github.com/docker-library/mariadb/blob/8ec795570021bdcf933a60d13b4631912634a5cc/10.1/Dockerfile)

[User/Password에 알맞은 ID/PW를 입력한 뒤 Test Connection을 누르면 연결이 성공하거나 실패하는데,](https://github.com/docker-library/mariadb/blob/8ec795570021bdcf933a60d13b4631912634a5cc/10.1/Dockerfile)

[Name에 DB의 별칭을, Comment에 설명을 입력한 뒤, Host에 서버의 IP또는 주소를 입력하면 URL이 자동으로 생성된다.](https://github.com/docker-library/mariadb/blob/8ec795570021bdcf933a60d13b4631912634a5cc/10.1/Dockerfile)

[![Datagrip01](https://github.com/kusakina0608/Gitbook/blob/master/.gitbook/assets/datagrip01.png?raw=true)](https://github.com/docker-library/mariadb/blob/8ec795570021bdcf933a60d13b4631912634a5cc/10.1/Dockerfile)

[+ 아이콘을 클릭하여 Data Source -&gt; MariaDB를 선택한다.](https://github.com/docker-library/mariadb/blob/8ec795570021bdcf933a60d13b4631912634a5cc/10.1/Dockerfile)

\*\*\*\*[**Datagrip을 사용한 Maria DB원격 접속**](https://github.com/docker-library/mariadb/blob/8ec795570021bdcf933a60d13b4631912634a5cc/10.1/Dockerfile)\*\*\*\*

 [컨테이너를 생성할 때 입력했던 root 패스워드를 입력하면 Maria DB에 접속할 수 있다.](https://github.com/docker-library/mariadb/blob/8ec795570021bdcf933a60d13b4631912634a5cc/10.1/Dockerfile)

[실행된 bash shell에서 command line으로 mariaDB에 접속한다.](https://github.com/docker-library/mariadb/blob/8ec795570021bdcf933a60d13b4631912634a5cc/10.1/Dockerfile)

[정상적으로 실행한 경우 bash shell이 실행된다.](https://github.com/docker-library/mariadb/blob/8ec795570021bdcf933a60d13b4631912634a5cc/10.1/Dockerfile)

[CONTAINER\_ID는 docker\_ps 명령어로 확인한 컨테이너의 ID를 입력해주면 된다.](https://github.com/docker-library/mariadb/blob/8ec795570021bdcf933a60d13b4631912634a5cc/10.1/Dockerfile)

[컨테이너의 ID를 확인한 뒤 아래 명령어를 실행하여 컨테이너에 직접 접근한다.](https://github.com/docker-library/mariadb/blob/8ec795570021bdcf933a60d13b4631912634a5cc/10.1/Dockerfile)

**Supported tags and respective Dockerfile links**

some-mariadb는 컨테이너에 할당할 이름이고, my-secret-pw는 Maria DB 루트 사용자의 암호이다. tag는 원하는 Maria DB 버전을 지정하는 태그이다. 지원하는 태그는 아래와 같다.

Maria DB를 실행하기 위해서 명령 프롬프트에서 아래 커맨드를 입력한다.

