#### docker 명령어

- docker build -t ljk1112/hello .

docker build 를 할껀데, -t 로 naming 을 할 것이며 이름은 jklee/hello 로 docker image 를 만들것이다.

> 주의사항
>
> - / 앞은 docker hub repository 명칭이기 때문에 docker hub 에 올려서 pod 을 생성 할 경우 주의해서 사용해야 한다.
> - docker pull 이 안될 경우 login 해서 사용하자.
>

또한 .은 현재 이 위치에 `Dockerfile` 이 있다 는 의미이고, 이름을 붙일 경우 해당 이름으로 DockerConfig 가 설정되어 있다는 의미이다.

- docker run -d -p 8100:8000 ljk1112/hello

-d : background 에서 실행
-p : xxxx(외부포트):xxxx(도커 내부 선언 포트)

- docker exec -it DOCKER_IMAGE_ID /bin/bash

도커를 실행하면서 내부 shell script 로 들어간다. DOCKER_CONTAINER_ID 는 해당 docker image 의 id 이고 /bin/bash 는 처음 시작하는 path 이다.

- docker push ljk1112/hello

docker hub 에 등록하는 것으로 docker login 을 통해 계정정보를 가져오고 해당 repository 에 등록한다.

