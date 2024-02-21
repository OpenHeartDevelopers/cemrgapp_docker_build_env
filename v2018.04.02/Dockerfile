FROM cemrg/build:18.04

RUN pip3 install --upgrade setuptools &&  \
    pip3 install aqtinstall && \ 
    aqt install --outputdir /Qt 5.12.10 linux desktop -m qtcharts qtnetworkauth qtpurchasing qtdatavis3d qtscript qtvirtualkeyboard qtwebengine qtwebglplugin

RUN git clone --branch v2018.04.2 https://phabricator.mitk.org/source/mitk.git /MITK && \ 
    rm -rf /MITK/.git* 

RUN find /MITK/ -exec touch -a -m -d 20210615 {} \; 
    
WORKDIR /Build

