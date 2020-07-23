FROM mcr.microsoft.com/dotnet/core/sdk:3.1-bionic as builder

RUN mkdir /root/src
WORKDIR /root/src
COPY ./src .

WORKDIR /root/src/WebApplication1

RUN dotnet publish -c Release -o published

FROM mcr.microsoft.com/dotnet/core/aspnet:3.1-bionic

WORKDIR /root/
COPY --from=builder /root/src/WebApplication1/published .
ENV ASPNETCORE_URLS=http://+:5000
EXPOSE 5000/tcp
CMD ["dotnet", "./WebApplication1.dll"]