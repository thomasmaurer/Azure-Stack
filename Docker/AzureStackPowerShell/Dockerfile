# Sample Dockerfile

# Indicates that the windowsservercore image will be used as the base image.
FROM microsoft/windowsservercore

# Metadata indicating an image maintainer.
LABEL maintainer Thomas Maurer 

SHELL ["powershell", "-Command", "$ErrorActionPreference = 'Stop'; $ProgressPreference = 'SilentlyContinue';"]

WORKDIR /

RUN Install-PackageProvider -Name NuGet -MinimumVersion 2.8.5.201 -Force ; \
Set-PSRepository -Name "PSGallery" -InstallationPolicy Trusted ; \
Install-Module -Name AzureRm.BootStrapper ; \
Use-AzureRmProfile -Profile 2017-03-09-profile -Force ; \
Install-Module -Name AzureStack -RequiredVersion 1.2.11

ENTRYPOINT [ "powershell.exe" ]