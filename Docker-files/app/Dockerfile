FROM openjdk:11 AS build_Image
# Since open jdk based on debian, apt is used below
RUN apt update && apt install maven -y
RUN git clone https://github.com/sharathsb17/vprofile-project.git
RUN cd vprofile-project && git checkout docker && mvn install
# this will build artifact inside dir> Target

FROM tomcat:9-jre11
# Remove default artifact
LABEL "project"="Vprofile"
LABEL "Author"="ssb"
RUN rm -rf /usr/local/tomcat/webapps/*
COPY --from=build_Image vprofile-project/target/vprofile-v2.war /usr/local/tomcat/webapps/ROOT.war

EXPOSE 8080
CMD ["catalina.sh", "run"]