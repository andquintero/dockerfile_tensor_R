FROM andresquintero/bratwurst_tensorflow2

LABEL maintainer="Andres Quintero a.quintero@dkfz-heidelberg.de"


#RUN R -e "devtools::install_github('andquintero/bratwurst', ref='dev_hdsu')"

    
RUN R -e "BiocManager::install('DESeq2', version = '3.8', update = FALSE)"
RUN R -e "BiocManager::install('gage', version = '3.8', update = FALSE)"
RUN R -e "install.packages('DT')"




#RUN useradd newuser
#USER newuser
#WORKDIR /home/newuser

#COPY --chown=rstudio data /home/rstudio/Corces_NMF/data
#COPY --chown=rstudio src /home/rstudio/Corces_NMF/src

RUN useradd -ms /bin/bash hdsu

RUN echo "uiPrefs={\"theme\" : \"Vibrant Ink\"}" >> \
  /home/rstudio/.rstudio/monitored/user-settings/user-settings

RUN mkdir -p /home/hdsu/.rstudio/monitored/user-settings/ && echo "uiPrefs={\"theme\" : \"Vibrant Ink\"}" >> \
  /home/hdsu/.rstudio/monitored/user-settings/user-settings


COPY --chown=hdsu /test_bratwurst/data /home/hdsu/Corces_NMF/data
COPY --chown=hdsu /test_bratwurst/src /home/hdsu/Corces_NMF/src
COPY --chown=hdsu /test_bratwurst/db /home/hdsu/Corces_NMF/db





#USER newuser
#WORKDIR /home/newuser


#install DESeq2

#docker build -t bratwurst_example .
#docker run -e PASSWORD=bratwurst -p 8787:8787 bratwurst_example
