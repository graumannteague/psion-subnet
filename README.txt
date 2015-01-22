BUILD NOTES
-----------

* send all .opl files EXCEPT tocidr.opl - this is a (now outdated) copy of
  tocidr_norems.opl, but it contains valuable comments on how the finite
  state machine for verifying the netmask was implemented.
* you can send via XMODEM in Minicom - first send in Minicom, then go to
  COMMS -> RECEIVE -> PROCEDURE on the Organiser.
* the filename on the Organiser should match the PROCEDURE name on the
  first line of the source file (one procedure per file), WITHOUT the trailing
  colon and any parameters, e.g. tonw$:(cidr%) should have a filename of
  tonw$ on the Organiser.  The filename has a maximum of 8 characters, which
  INCLUDES the trailing return type specifier (if present)
* when transfer is complete, press EXE on the Organiser to save the SOURCE
  file.  If you get a BAD PROCEDURE error, make sure file is in DOS (CR+LF
  line delimiters) format (use unix2dos), has all tab characters translated
  to spaces with "tr '\t' ' '", and has no long lines.
* repeat this for each source file.
* TRANSLATE each file on the Organiser by selecting PROG -> EDIT on each file,
  pressing MODE when in edit mode, and selecting TRAN.
* insert SUBNET on the main menu in a convenient location with MODE button

USAGE NOTES
-----------

* Each quad is in a three-character field, separated by dots, and padded with
  leading zeroes when necessary, e.g. 010.000.023.020
* Netmask (e.g. 255.255.255.252) or CIDR (e.g. 30) are both valid input
  formats - select the appropriate one when prompted
* If using netmask, this is validated by the program
* If using CIDR, must be no greater than 30 (or else there is no room for
  hosts available in the subnet!)
* When done, program displays network address with CIDR, broadcast address,
  host range, and number of hosts per subnet
