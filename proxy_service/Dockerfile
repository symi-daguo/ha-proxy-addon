ARG BUILD_FROM
FROM ${BUILD_FROM}

# 设置工作目录
WORKDIR /app

# 安装必要的工具
RUN \
    apk add --no-cache \
        curl \
        jq \
        unzip \
        ca-certificates \
        wget

# 安装 Clash
RUN \
    ARCH=$(if [ "$(uname -m)" = "armv7l" ]; then echo "armv7"; \
           elif [ "$(uname -m)" = "aarch64" ]; then echo "arm64"; \
           elif [ "$(uname -m)" = "x86_64" ]; then echo "amd64"; \
           else echo "386"; fi) && \
    wget -O clash.gz https://github.com/Dreamacro/clash/releases/download/v1.18.0/clash-linux-${ARCH}-v1.18.0.gz && \
    gunzip clash.gz && \
    mv clash /usr/local/bin/ && \
    chmod +x /usr/local/bin/clash

# 创建必要的目录
RUN mkdir -p /root/.config/clash

# 下载 Country.mmdb 文件
RUN curl -L -o /root/.config/clash/Country.mmdb https://github.com/Dreamacro/maxmind-geoip/releases/latest/download/Country.mmdb

# 复制配置文件和启动脚本
COPY rootfs /

# 设置权限
RUN chmod a+x /etc/services.d/clash/run

# 暴露端口
EXPOSE 7890 7891

# 入口点
ENTRYPOINT ["/init"] 