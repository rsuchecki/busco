FROM comics/centos
MAINTAINER Ian Merrick <MerrickI@Cardiff.ac.uk>

##############################################################
# Dockerfile Version:   0.1
# Software:             busco
# Software Version:     3.0.2
# Software Website:     http://busco.ezlab.org/ 
# Description:          Assessing genome assembly and annotation completeness with Benchmarking Universal Single-Copy Orthologs
##############################################################

ENV APP_NAME=busco
ENV VERSION=3.0.2
ENV GIT=https://gitlab.com/ezlab/busco.git
ENV APPS=/software/applications
ENV DEST=$APPS/$APP_NAME/
ENV PATH=$APPS/$APP_NAME/$VERSION/bin:$APPS/bcftools/$VERSION/bin:$PATH

RUN \
    yum clean all ; \
    git clone ${GIT} ; \
    cd ${APP_NAME} ; \
    git checkout tags/${VERSION} ; \
   

    make prefix=$APPS/bcftools/$VERSION install ; \
    cd .. ; \
    cd samtools-$VERSION ; \
    make -j HTSDIR=../htslib ; \
    make prefix=$APPS/$APP_NAME/$VERSION install ; \
    cd ../ ; \
    rm -rf htslib samtools-$VERSION bcftools-$VERSION

CMD ["/bin/bash"]

