FROM ghcr.io/anthr76/minecraft/base-image:0.0.0

ENV \
  VELOCITY_VERSION=3.1.1 \
  LUCKPERMS_VERSION=5.4.6 \
  SKINSRESTORER_VERSION=14.1.10

RUN \
    mkdir -p /app/plugins/

RUN curl -fsSL -o /app/velocity.jar \
        "https://papermc.io/api/v2/projects/velocity/versions/3.1.2-SNAPSHOT/builds/114/downloads/velocity-3.1.2-SNAPSHOT-114.jar" 
RUN curl -fsSL -o /app/plugins/luckperms.jar \
        "https://ci.lucko.me/view/LuckPerms/job/LuckPerms/lastSuccessfulBuild/artifact/velocity/build/libs/LuckPerms-Velocity-$LUCKPERMS_VERSION.jar"
RUN curl -fsSL -o /app/plugins/SkinsRestorer.jar \
        "https://github.com/SkinsRestorer/SkinsRestorerX/releases/download/$SKINSRESTORER_VERSION/SkinsRestorer.jar"

RUN chown -R kutara /app

EXPOSE 25565 25575

VOLUME [ "/app" ]
WORKDIR /app
USER kutara

CMD ["/app/velocity.jar"]
