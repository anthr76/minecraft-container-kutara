from registry.fedoraproject.org/fedora-minimal:35

RUN \
  microdnf install -y --setopt=install_weak_deps=0 --setopt=keepcache=0 \
  catatonit \
  java-latest-openjdk-headless \
  shadow

RUN \
  useradd \
  --no-create-home \
  --uid 1000 \
  kutara

ENTRYPOINT [ "/usr/libexec/catatonit/catatonit", "--", "java", "-XX:+UseContainerSupport", "-XX:MaxRAMPercentage=75.0", "-jar" ]
