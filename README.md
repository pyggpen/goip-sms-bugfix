# goip-sms-bugfix
A bugfixed (haha) php script to send sms on a GoIP VOIP box
A php script to send SMS from a GOIP VOIP box, built on previous works.

This script is derived from the stackoverflow answer provided by paisapimp, and I take no credit for the original script beyond squashing some minor bugs and adding the ability to pass some things from the command line. See https://stackoverflow.com/questions/28941059/how-to-send-retrieve-sms-from-goip for the original Q&A

Dependencies of this script:

At least: php5-cgi php5 php5-curl php5-cli

If you have apache2 installed, this may satisfy some of these dependencies. The php5-cgi dependency may also be satisfied by php5-fpm.

How to use:

Change the IP address, username, and password to that of your GOIP box. If desired, the arguments retrieved from the command line may be changed to be static (telephone number and message) in the script.

Assuming you are using the command line: /path/to/php /path/to/sendsms.php telnumber 'Message'

Optionally, direct the output of this script to a location for further analysis.

Returned information:

This script will return the html code of the GOIP's webpage, followed by the http return code. 200 indicates that everything was accessed without issue, but not necessarily that the box was able to send anything properly.

Bugs squashed:

php complained about $fields_string being appended without being initialized. Initialized this value to ''

curl_getinfo complained about not having anything to return, CURLINFO_HTTP_CODE was chosen as it seemed the most useful.

This was originally posted by me under by full username, but that account had issues and was deleted. You can see the
original repository here: https://github.com/phanthom2o4o/goip-sms

I wanted to put this here mostly for historical record, as these GoIP boxes are pretty much worthless these days (2G is limited) and
the devices themselves were about as unstable as you could get. They'd lock up and need a reboot every few hours, which is a shame because
they were one of the more reasonably priced SMS-capable boxes available at the time.

They were also very noisy with their lights, a friend of mine said "Wow, that's a busy little box!"
