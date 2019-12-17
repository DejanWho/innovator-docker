FROM microsoft/aspnet

LABEL maintainer="dejan.siedle@software-vision.com"
LABEL version="0.1"

COPY ./content C:/inetpub/wwwroot/

RUN icacls 'C:\inetpub\wwwroot' /t /grant 'IIS_IUSRS:(OI)(CI)(F)'

RUN New-WebAppPool 'Aras Vault AppPool ASP.NET 4.0'
RUN New-WebApplication -Name 'Vault' -Site 'Default Web Site' -PhysicalPath 'C:\inetpub\wwwroot\vault' -ApplicationPool 'Aras Vault AppPool ASP.NET 4.0'
