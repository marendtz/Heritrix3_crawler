# Heritrix3_crawler

# info for creating the above repository

# github: https://github.com/internetarchive/heritrix3

# docu: https://heritrix.readthedocs.io/en/latest/index.html

# Heritrix is primarily used on Linux. It may run on other platforms but is not regularly tested or supported on them.

# therefor usage with docker

# before git clone set handling of file endings accordingly: https://stackoverflow.com/questions/10418975/how-to-change-line-ending-settings

``git config --global core.autocrlf false``

``git clone https://github.com/internetarchive/heritrix3.git``

# move to docker directory that containes the Dockerfile

# build image

``docker build --build-arg version=3.4.0-20210923 -t iipc/heritrix .``

# run container
``docker run --init --rm -d --name heritrix_container -p 8443:8443 -e "USERNAME=admin" -e "PASSWORD=admin" -v $(pwd)/jobs:/opt/heritrix/jobs iipc/heritrix``

# go to
https://localhost:8443/engine 