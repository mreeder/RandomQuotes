FROM mcr.microsoft.com/dotnet/sdk:5.0

RUN mkdir /src
WORKDIR /src
ADD . /src
RUN dotnet restore
RUN ["dotnet", "build", "--configuration", "release"]

EXPOSE 5000
EXPOSE 5001

ENV ASPNETCORE_URLS="http://+:5000;https://+:5001"
ENV ASPNETCORE_ENVIRONMENT="Production"
ENV AppVersion="0.0.0"
ENV EnvironmentName="DEV"
ENV DefaultConnection="Server=(local)\\SQLEXPRESS;Database=RandomQuotes_Local;User Id=svcRandomQuotes_Local;Password=Password01!;MultipleActiveResultSets=true"

ENTRYPOINT [ "dotnet", "run", "--no-launch-profile" ]

