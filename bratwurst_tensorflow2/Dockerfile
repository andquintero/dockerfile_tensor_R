FROM andresquintero/r_tensorflow2

LABEL maintainer="Andres Quintero a.quintero@dkfz-heidelberg.de"


RUN R -e "devtools::install_github('andquintero/bratwurst', ref='dev_hdsu')"

    
#updated convergence in NMF
#2019.03.27 integrative NMF first commit 
#2019.03.30 integrative NMF lambda bug fix 
#docker build -t bratwurst_tensor2 .
#docker run -e PASSWORD=bratwurst -p 8787:8787 bratwurst_tensor2
