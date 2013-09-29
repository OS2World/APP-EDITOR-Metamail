Archive Name: metamail.zip
Description: Binaries/lisp files to allow MIME encoding/decoding under GNU EMACS
Program Source: Richard Stanton
email address: stanton@haas.berkeley.edu
Suggested directory: ....emacs/contrib (or equivalent) 

This file should replace previous metamail.zip.

This archive contains binaries (metamail.exe, mmencode.exe) which are just 
the standard metamail distribution compiled under emx (with a correction to 
mmencode.c, which was not correctly setting binary mode) , plus three lisp files
mime.el, metamail.el and rmailmime.el. Install the binaries in your path,
install the lisp files (instructions for editing your .emacs are in the lisp
files), and you can now add MIME attachments to mail sent using sendmail, or 
decode MIME attachments under RMAIL.

2/1/95   Updated version of mime.el - now correctly encodes/decodes
         binary files without converting all LF characters to CRLF.

9/20/95  Updated lisp files
         Corrected bug in mmencode.exe
         Now includes source code

11/6/95  New version of mmencode.c, mmencode.exe, with binary mode
         patch by Hiroshi Ueno <zodiac@ibm.net>

6/13/96  New version of mmencode.c, mmencode.exe, correcting binary mode
         problem when decoding from stdin.