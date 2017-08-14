# sslvalidity
a check plugin (nagios, icinga, centreon and so on) to gather information about the end date of a web certificate

## Usage

Check plugins are better used inside monitoring applications, like icinga or nagios.

### Icinga

Copy the check plugin inside your monitoring plugin directory. Optionaly with icinga, you can use the command conf file to use the script nativly.

### Script

The plugin is a simple sh script that gather information about a web certificate, extract the date and compare it to today and two dates in the future.

The critical and warning arg must be set as integer representing days before the plugin goes invalid. Obviously, the warning one should be further in time than the critical one (if so the plugin will act unexpectedly).

A simple exemple would be :

```
./check_sslvalidity -s github.com -w 10 -c 5
OK : SSL validity goes beyond 1 month (expire May 17 12:00:00 2018 GMT)
```
