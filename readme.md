# PeachPie Timezones Testcase

## Running

The included Dockerfile builds a linux docker image on the Microsoft image `mcr.microsoft.com/dotnet/core/aspnet:3.1-bionic`.

From the root of this repository run:

	docker build -f ./build/WebApplication1/Dockerfile . -t php_timezones
	docker run -p 5004:5000 php_timezones

Open up your web-browser and navigate to `http://localhost:5000` to see a dump of timezones from the `timezone_identifiers_list` PHP function. 

## Output

Running this project inside Visual Studio on Windows produces output like:

```
array(433) {
[0]=>
string(14) "Africa/Abidjan"
[1]=>
string(12) "Africa/Accra"
[2]=>
string(18) "Africa/Addis_Ababa"
[3]=>
string(14) "Africa/Algiers"
...snip...
```

Running the produced docker image produces the following output:

```
array(1) {
[0]=>
string(3) "UTC"
}
```