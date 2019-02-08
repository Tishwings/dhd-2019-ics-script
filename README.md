# dhd-2019-ics-script (unofficial)
Converts the DHd2019 schedule into an ics-file. This script was written independent from the DHd2019 and is unofficial. DHd2019 does not provide any support for the script. Same goes for the reliabilty and up-to-dateness of the output ics-file.

This script parses the https://dhd2019.org/programm/ pages and returns all found events that are "valid" in one .ICS file that can be imported e.g. in Google Calendar.

Please feel free to use and improve!

Known Issues:
* Since not every div with class="programmblock" is build up in the same way, the ICS only contains events that could be made up of 1 title 1 url and 1 place. E.g. the break events are not catched with this and some titles are missing.
* the regular expression to get the titles is not precise enough, e.g. a very long title could lead to not be recognized
* the uids of the events are current time generated, processing the script again will lead to new uids although most (all) of the events will be the same. Improving this would be very helpful, e.g. Google Calendar would only import new/updated events when the ICS is importted several times
* Timezone ist not specified, times will only be correct for visitors from german timezone
* the for loop that composes VEVENT string is not very efficient
* all \n should be appended as \r\n right from the beginning
* current date is hard coded, could also be parsed from website
* maybe google calendar has an api that allows the script to directly push events into a calendar?
* URLs in VEVENTS still contain spaces and " at beginning and end, but they are functional
