# Dockerfile
# OpenJDK 17 기반의 가벼운 이미지 사용 (보안 및 경량화를 위해)
FROM eclipse-temurin:17-jre-alpine

# 애플리케이션의 JAR 파일 경로 (Maven 빌드 결과물)
# Maven 빌드는 일반적으로 target 디렉토리에 JAR 파일을 생성합니다.
ARG JAR_FILE=target/*.jar

# 애플리케이션 JAR 파일을 컨테이너의 app.jar로 복사
COPY ${JAR_FILE} app.jar

# 컨테이너 실행 명령어
# java -jar 명령어로 애플리케이션 실행
ENTRYPOINT ["java", "-jar", "/app.jar"]
