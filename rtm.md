Requirement Traceability Matrix - Text to Speech Converter

REQ01, user can type text to convert, covered by TC01, no bugs
REQ02, user can pick a language, covered by TC05, no bugs
REQ03, user can pick a voice type, covered by TC06, no bugs
REQ04, user can adjust speed, covered by TC01 general flow, no bugs
REQ05, user can adjust pitch, covered by TC07, bug found BUG03, still open
REQ06, app converts text into audio, covered by TC01, no bugs
REQ07, user can play the audio, covered by TC01, no bugs
REQ08, user can download the audio, covered by TC08, bug found BUG04, still open
REQ09, app validates the text input, covered by TC02 TC03 TC04 TC10, bugs found BUG01 fixed and BUG02 still open
REQ10, app saves conversion history in database, covered by TC12 TC13 TC15, bug found BUG06, fixed
REQ11, convert API accepts requests and returns audio, covered by TC09 TC10 TC11, bugs found BUG01 and BUG05
REQ12, app handles errors properly, covered by TC11, bug found BUG05, still open
