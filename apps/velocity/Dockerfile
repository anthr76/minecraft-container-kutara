FROM ghcr.io/anthr76/minecraft/base-image:latest

ENV \
  VELOCITY_VERSION=3.1.1 \
  LUCKPERMS_VERSION=5.4.6 \
  SKINSRESTORER_VERSION=14.1.15

RUN \
    mkdir -p /app/plugins/

RUN curl -fsSL -o /app/velocity.jar \
        "https://papermc.io/api/v2/projects/velocity/versions/3.1.2-SNAPSHOT/builds/138/downloads/velocity-3.1.2-SNAPSHOT-138.jar" 
RUN curl -fsSL -o /app/plugins/luckperms.jar \
        "https://ci.lucko.me/job/LuckPerms/1429/artifact/velocity/build/libs/LuckPerms-Velocity-5.4.21.jar"
RUN curl -fsSL -o /app/plugins/SkinsRestorer.jar \
        "https://github.com/SkinsRestorer/SkinsRestorerX/releases/download/$SKINSRESTORER_VERSION/SkinsRestorer.jar"

RUN \
    bash -c "cd /app && java -jar ./velocity.jar </dev/null &>/dev/null &" \
    && sleep 30s

RUN \
    chown -R kutara:kutara /app

EXPOSE 25565 25575

VOLUME [ "/app" ]
WORKDIR /app
USER kutara

CMD ["/app/velocity.jar"]
