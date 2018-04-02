# Sample Dockerfile

# Indicates that the windowsservercore image will be used as the base image.
FROM thomasmaurer/azurestackpowershell

# Metadata indicating an image maintainer.
LABEL maintainer Thomas Maurer 

SHELL ["powershell", "-Command", "$ErrorActionPreference = 'Stop'; $ProgressPreference = 'SilentlyContinue';"]

WORKDIR /

RUN Cd / ; \
[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12 ; \
invoke-webrequest https://github.com/Azure/AzureStack-Tools/archive/master.zip -OutFile C:\master.zip ; \
expand-archive C:\master.zip -DestinationPath . -Force

ENTRYPOINT [ "powershell.exe" ]