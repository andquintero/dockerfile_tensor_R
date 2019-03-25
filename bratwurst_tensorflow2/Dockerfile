FROM andresquintero/r_tensorflow2

LABEL maintainer="Andres Quintero a.quintero@dkfz-heidelberg.de"


RUN R -e "devtools::install_github('andquintero/bratwurst',  ref='dev_hdsu') "

    
#updated convergence in NMF
#docker build -t bratwurst_tensor2 .
#docker run -e PASSWORD=bratwurst -p 8787:8787 bratwurst_tensor2
