Bug Reports - Text to Speech Converter

Bug ID BUG01
Summary: empty text is accepted for conversion instead of showing an error

Steps to reproduce: open the app, leave the text box empty, click convert

Expected result: the button should be disabled or show an error message

Actual result: the request went through and an almost silent audio file got created

Severity: high

Priority: high

Status: fixed and re-tested in TC14

Bug ID BUG02
Summary

emoji in the text causes a glitchy sound in the audio
Steps to reproduce, type a sentence with an emoji in it and convert
Expected result, emoji should be skipped or rejected with a message
Actual result, audio plays fine until it hits the emoji then makes a weird noise
Severity, medium
Priority, medium
Status, open

Bug ID BUG03
Summary

audio stops playing after 2 seconds when pitch is set to max
Steps to reproduce, set pitch slider to maximum, convert, then play the audio
Expected result, full audio should play regardless of pitch setting
Actual result, playback cuts off after around 2 seconds, happens in browser and in the downloaded file
Severity, high
Priority, medium
Status, open

Bug ID BUG04
Summary

download button works even before converting anything
Steps to reproduce, open the app fresh, click download without typing or converting
Expected result, download button should stay disabled until a conversion is done
Actual result, an empty file gets downloaded
Severity, low
Priority, low
Status, open

Bug ID BUG05
Summary,

wrong language code causes a server error instead of a normal error message
Steps to reproduce, send an API request with a made up language code
Expected result, should return a 400 error with a clear message
Actual result, returns a 500 server error with no useful message
Severity, medium
Priority, medium
Status, open

Bug ID BUG06
Summary,

failed conversions are marked as successful in the database
Steps to reproduce, cause a conversion to fail then check the conversion history table
Expected result, row should be marked as failed
Actual result, row was marked as success even though it failed
Severity, high
Priority, high
Status, fixed and re-tested in TC15
