FROM seiiti/jdk-oracle


# 1. Install Git, Subversion and Maven

RUN set -x \
    && apt-get update \
    && apt-get install --yes \
                            git \
                            subversion \
                            maven


# 2. Set locale (required for SVN files in Unicode)

RUN set -x \
    && sed -i -e 's/# en_US.UTF-8 UTF-8/en_US.UTF-8 UTF-8/' /etc/locale.gen \
    && dpkg-reconfigure --frontend=noninteractive locales \
    && update-locale LANG=en_US.UTF-8

ENV LC_CTYPE en_US.UTF-8


# 3. Delete apt list files

RUN set -x \
    && rm -rf /var/lib/apt/lists/*
