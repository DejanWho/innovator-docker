FROM microsoft/aspnet

COPY ./content C:/inetpub/wwwroot/

RUN icacls 'C:\inetpub\wwwroot' /t /grant 'IIS_IUSRS:(OI)(CI)(F)'

RUN New-WebAppPool 'Aras Innovator AppPool ASP.NET 4.0'
RUN New-WebApplication -Name 'InnovatorServer' -Site 'Default Web Site' -PhysicalPath 'C:\inetpub\wwwroot\Innovator' -ApplicationPool 'Aras Innovator AppPool ASP.NET 4.0'
RUN New-WebApplication -Name 'InnovatorServer/Server' -Site 'Default Web Site' -PhysicalPath 'C:\inetpub\wwwroot\Innovator\Server' -ApplicationPool 'Aras Innovator AppPool ASP.NET 4.0'
RUN New-WebApplication -Name 'InnovatorServer/Client' -Site 'Default Web Site' -PhysicalPath 'C:\inetpub\wwwroot\Innovator\Client' -ApplicationPool 'Aras Innovator AppPool ASP.NET 4.0'
