FROM mcr.microsoft.com/dotnet/sdk:6.0
WORKDIR /source
RUN apt-get update \
    && apt-get install -y --no-install-recommends \
        tini \
    && rm -rf /var/lib/apt/lists/*
ENTRYPOINT ["/usr/bin/tini", "--"]
CMD ["tail", "-f", "/dev/null"]
