# Penn State ACM Check-in

### Shane Tully (shane@shanetully.com)
### shanetully.com & acm.psu.edu

## Setup

The Penn State ACM Check-in application is built on Python. 
There are two dependencies:
   1.) PyQt - Python bindings for QT   (Package for Ubuntu-based systems: "python-qt4")
   2.) MySQLdb - Python MySQL library  (Package for Ubuntu-based systems: "python-mysqldb")

It has been reported that this application runs on Windows with the Windows versions of the two libraries listed above,
but Windows support is not taken into consideration during development. Thus, no guarentees for Windows support are made.
Please don't bug me with requests for Windows support. Use a real OS like Linux.

Once the dependencies are met, run it with "./Check-in.py".

To actaully use it, however, you will need a database server (either a remote server or hosted locally).
The default host, database, table, and host are configurable in the Constants.py file or are able to
be entered in the login screen of the application.

For the database, this application expects a table with four columns:
   1.) card ID        - card ID from ID card (varchar, primary key)
   2.) access ID      - human-readable owner of card (varchar)
   3.) points         - the number of points (int)
   4.) last check-in  - the time of last check-in (timestamp)

You'll probably want to change the default database information for your database in Constants.py.

Finally, the whole script is pointless without a card reader. This application was built for a card read that 
uses keyboard emulation. Hence, you could just type the card info in, but without a card reader you have no way of 
knowing what that info is!


## Usage

Usage is very straightforward. Simply run "./Check-in.py" to start the GUI.

There is also a text-only mode. This can be started by using the "--nogui" argument.
In text mode, enter "back" at any time to go up a menu level or exit the check-in loop.

To populate your database, select the check-in option and if a card doesn't exist in the database 
you will be prompted to add it.

After your database is populated you can use the "Show Points" option to show a single user's points or view a pretty
table of all users in descending order from most to least points.

Note that, by default, a card is only allowed to check-in once per hour to prevent abuse. This can
be disabled by setting "ALLOW_CHECKIN_WITHIN_HOUR" to 0 in Constants.py.


## Support
This program is a little side project and carries no warranty or support
from its author. However, bugs and feature requests may be submitted to the GitHub repo
linked to above.


### License

Copyright (C) 2013 Shane Tully

This program is free software: you can redistribute it and/or modify
it under the terms of the GNU Lesser General Public License as published by
the Free Software Foundation, either version 3 of the License, or
(at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU Lesser General Public License for more details.

You should have received a copy of the GNU Lesser General Public License
along with this program.  If not, see <http://www.gnu.org/licenses/>.
