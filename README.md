## 설명 
### 해당 프로젝트는 gradlew build 명령 대신 github action에 제공되는 gradle/gradle-build-action 툴을 사용하여 빌드 함 


### Docker 이미지 빌드
   docker build -t {docker hub 계정명}/devops_step1:{tag명} .

### Docker Hub 이미지 푸시
   docker push {docker hub 계정명}/devops_step1:{tag명} 

### docker compose 
1. docker-compose.yml 단독 서버실행 
2. docker-compose-nginx.yml 여러 서버실행 
   1. 배포서버에  nginx 폴더 생성 한다
   2. nginx.conf 파일을 nginx 폴더에 복사한다
   3. docker-compose -f docker-compose-nginx.yml 실행 한다
   4. nginx 뒤에 was 두개가 동작 하는 것을 확인 할 수 있다
   5. 실행 docker 컨테이너 이름 확인 (docker ps -a)
   6. 수동으로 컨테이너 이름으로 종료 해본다(docker stop 컨테이너 이름)
   7. 수동으로 컨테이너 이름으로 제거 해본다(docker rm 컨테이너 이름)
   8. 수동으로 이미지 이름으로 제거 해본다(docker rmi 이미지이름)
      

 ### 배포서버 등록하기 
 1. actions -> runner에 배포 서버 추가
 2. 배포 서버 스크립트의 runs-on 레이블 맟추어야 한다 -> 위 배포 서버 스크립트 실행시 
 3. 배포 서버에 runner 백드라운드에서 프로그램 실행 (nohup ./run.sh &)
