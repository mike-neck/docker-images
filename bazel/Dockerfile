FROM mikeneck/jdk8

RUN \
  apt-get update && \
  apt-get install -y \
    pkg-config \
    g++ \
    zlib1g-dev && \
  apt-get clean && \
  rm -rf /var/lib/apt/lists/* && \
  groupadd -r build && \
  useradd -m -g build bazel

USER bazel
WORKDIR /home/bazel

RUN \
  curl -L \
    https://github.com/bazelbuild/bazel/releases/download/0.1.1/bazel-0.1.1-installer-linux-x86_64.sh \
    -o bazel-install.sh
RUN chmod 700 bazel-install.sh
RUN ./bazel-install.sh --user && \
  rm bazel-install.sh

ENV BAZEL_BIN=/home/bazel/bin
ENV PATH=$PATH:$BAZEL_BIN

CMD ["/bin/bash"]
