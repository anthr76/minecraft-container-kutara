from registry.fedoraproject.org/fedora-minimal:35

ENV \
  VELOCITY_VERSION=3.0.1
  LUCKPERMS_VERSION=5.3.77

RUN microdnf install -y \
  catatonit \
  java-latest-openjdk-headless \
  && \
  mkdir /server \
  && curl -fsSL -o /server/velocity.jar \
    "https://versions.velocitypowered.com/download/${VELOCITY_VERSION}.jar"
  && curl -fsSL -o /server/plugins/luckperms.jar \
    "https://ci.lucko.me/job/LuckPerms/1376/artifact/bukkit/loader/build/libs/LuckPerms-Bukkit-${LUCKPERMS_VERSION}.jar"

EXPOSE 25565 25575

ENTRYPOINT [ "/usr/libexec/catatonit/catatonit", "--" ]
CMD ["java","-jar", "/app/velocity.jar"]
