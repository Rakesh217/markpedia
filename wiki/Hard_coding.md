
**Hard coding** (also **hard-coding** or **hardcoding**) is the software
development practice of embedding data directly into the [source
code](source_code "wikilink") of a
[program](computer_program "wikilink") or other executable object, as
opposed to obtaining the data from external sources or generating it at
[run-time](Run_time_(program_lifecycle_phase) "wikilink"). Hard-coded
data typically can only be modified by editing the source code and
[recompiling](Compiling "wikilink") the executable, although it can be
changed in [memory](Volatile_memory "wikilink") or on disk using a
[debugger](debugger "wikilink") or [hex editor](hex_editor "wikilink").
Data that are hard-coded usually represent unchanging pieces of
information, such as [physical constants](physical_constant "wikilink"),
[version numbers](Version_number "wikilink") and static text elements.
[Softcoded data](Softcoding "wikilink"), on the other hand, encode
arbitrary information like [user input](user_input "wikilink"), HTTP
server responses, or configuration files, and are determined at runtime.

Overview
--------

Hard coding requires the program's source code to be changed any time
the input data or desired format changes, when it might be more
convenient to the end user to change the detail by some means outside
the program.

Hard coding is often required, but can also be considered an
[anti-pattern](anti-pattern "wikilink"). Programmers may not have a
dynamic user interface solution for the end user worked out but must
still deliver the feature or release the program. This is usually
temporary but does resolve, in a short term sense, the pressure to
deliver the code. Later, softcoding is done to allow a user to pass on
parameters that give the end user a way to modify the results or
outcome.

The term “hard-coded” was initially used as an analogy to hardwiring
circuits - and was meant to convey the inflexibility which results from
its usage within software design and implementation. In the context of
run-time extensible [collaborative development
environments](collaborative_development_environment "wikilink") such as
[MUDs](MUD "wikilink"), **hardcoding** also refers to developing the
core engine of the system responsible for low-level tasks and executing
scripts, as opposed to **softcoding** which is developing the high-level
scripts that get interpreted by the system at runtime. In this case, the
term is not pejorative and refers to general development, rather than
specifically embedding output data.

Hardcoding and backdoors
------------------------

Hardcoding credentials is a popular way of creating a backdoor.
Hardcoded credentials are usually not visible in configuration files and
output of account-enumeration commands and cannot be changed easily
(without rebuilding from source, [if source is
available](FLOSS "wikilink") or
[reverse-engineering](reverse-engineering "wikilink"), [binary
modification](hex-editor "wikilink"), and integrity-check (digital
signatures, anti-tamper, and [anti-cheat](anti-cheat "wikilink")))
bypass (which can be prohibited with [EULA](EULA "wikilink")) by users.

Hardcoding and DRM
------------------

As a [digital rights management](digital_rights_management "wikilink")
measure, software developers may hardcode a unique [serial
number](serial_number "wikilink") directly into a program. Or it is
common to hardcode a [public key](public_key "wikilink"), creating the
DRM for which it is infeasible to create a keygen.

On the opposite case, a software [cracker](Software_cracking "wikilink")
may hard-code a valid serial number to the program or even prevent the
executable from asking the user for it, allowing unauthorized copies to
be redistributed without the need of entering a valid number, thus
sharing the same key for every copy, if one has been hard-coded.

Fixed installation path
-----------------------

If a Windows program is programmed to assume it is always installed to
C:\\Program Files\\Appname and someone tries to install it to a
different drive for space or organizational reasons, it may fail to
install or to run after installation. This problem might not be
identified in the testing process, since the average user installs to
the default drive and directory and testing might not include the option
of changing the installation directory. However it is advisable for
programmers and developers not to fix the installation path of a
program, since the default installation path depends on the operating
system, OS version, and [sysadmin](sysadmin "wikilink") decisions. For
example, many installations of [Microsoft
Windows](Microsoft_Windows "wikilink") use [drive
C:](Drive_letter_assignment#Common_assignments "wikilink") as their
primary [hard disk](hard_disk "wikilink"), but this is not guaranteed.

There was a similar issue with
[microprocessors](microprocessor "wikilink") in early computers, which
[started execution](reset_(computing) "wikilink") at a fixed
[address](address_space "wikilink") in memory.

Startup disk
------------

Some “copy-protected” programs look for a particular file on a floppy
disk or flash drive on startup to verify that they are not unauthorized
copies. If the computer is replaced by a newer machine, which doesn't
have a floppy drive, the program that requires it now can't be run,
since the floppy disk can't be inserted.

This last example shows why hard-coding may turn out to be impractical
even when it seems at the time that it would work completely. In the
1980s and 1990s the great majority of PCs were fitted with at least one
floppy drive, but floppy drives later fell out of use. A program
hard-coded in that manner 15 years ago could face problems if not
updated.

Special folders
---------------

Some Windows operating systems have so called *[Special
Folders](Special_Folders "wikilink")* which organize files logically on
the hard disk. There are problems that can arise involving hard coding:

### Profile path

Some Windows programs hard code the profile path to developer-defined
locations such as `C:\Documents and Settings\`*`Username`*. This is the
path for the vast majority of [Windows 2000](Windows_2000 "wikilink") or
above, but this would cause an error if the profile is stored on a
network or otherwise relocated. The proper way to get it is to call the
`GetUserProfileDirectory` function or to resolve the `%userprofile%`
environment variable. Another assumption that developers often make is
assuming that the profile is located on a local hard disk.

### My Documents folder path

Some Windows programs hardcode the path to
[`My Documents`](My_Documents "wikilink") as
*`ProfilePath`*`\My Documents`. These programs would work on machines
running the English version, but on
[localized](internationalization_and_localization "wikilink") versions
of Windows this folder normally has a different name. For example, in
Italian versions the `My Documents` folder is named *Documenti*.
`My Documents` may also have been relocated using Folder Redirection in
Group Policy in Windows 2000 or above. The proper way to get it is to
call the `SHGetFolderPath` function.

Solution
--------

An indirect reference, such as a variable inside the program called
“FileName”, could be expanded by accessing a “browse for file” dialogue
window, and the program code would not have to be changed if the file
moved.

Hard coding is especially problematic in preparing the software for
translation to other languages.

In many cases, a single hard-coded value, such as an array size, may
appear several times within the source code of a program. This would be
a [magic number](Magic_number_(programming) "wikilink"). This may
commonly cause a program bug if some of the appearances of the value are
modified, but not all of them. Such a bug is hard to find and may remain
in the program for a long time. A similar problem may occur if the same
hard-coded value is used for more than one parameter value, e.g. an
array of 6 elements and a minimum input string length of 6. A programmer
may mistakenly change all instances of the value (often using an
editor's search-and-replace facility) without checking the code to see
how each instance is used. Both situations are avoided by defining
[constants](constant_(programming) "wikilink"), which associate names
with the values, and using the names of the constants for each
appearance within the code.

One important case of hard coding is when strings are placed directly
into the file, which forces translators to edit the source code to
translate a program. (There is a tool called
[`gettext`](gettext "wikilink") that permits strings to be left in
files, but lets translators translate them without changing the source
code; it effectively de-hard codes the strings.)

Hard coding in competitions
---------------------------

In computing competitions such as the [International Olympiad in
Informatics](International_Olympiad_in_Informatics "wikilink"),
contestants are required to write a program with specific input-output
pattern according to the requirement of the questions.

In rare cases where the possible number of inputs is small enough, a
contestant might consider using an approach that maps all possible
inputs to their correct outputs. This program would be considered a
hard-coded solution as opposed to an [algorithmic](algorithm "wikilink")
one (even though the hard-coded program might be the output of an
algorithmic program).

----

[Wikipedia](https://en.wikipedia.org/wiki/Hard_coding) in [Markdown](https://github.com/rognoni/markpedia) format under the [CC BY-SA 3.0](https://creativecommons.org/licenses/by-sa/3.0/) license
