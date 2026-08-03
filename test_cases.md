Test Cases - Text to Speech Converter


TC01 - Convert a normal sentence

Requirement: user can input text

Steps: open the app, type a sentence, click convert

Expected: audio gets created and plays fine

Actual: worked fine

Status: pass


TC02 - Convert with empty text box

Requirement: input validation

Steps: leave text box empty, click convert

Expected: should show an error or the button should be disabled

Actual: nothing happened, button was still clickable and it sent the request anyway

Status: fail, logged as BUG01


TC03 - Text longer than the limit

Requirement: input validation

Steps: type more than 500 characters, click convert

Expected: error message about text being too long

Actual: error showed correctly

Status: pass


TC04 - Text with emojis

Requirement: input validation

Steps: type a sentence with an emoji in the middle, click convert

Expected: emoji should be skipped or an error should show

Actual: audio played fine until the emoji, then made a weird glitchy sound

Status: fail, logged as BUG02


TC05 - Change language mid session

Requirement: language selection

Steps: convert once in English, then switch to Hindi and convert the same text again

Expected: new audio should use the new language

Actual: worked as expected

Status: pass


TC06 - Change voice type

Requirement: voice selection

Steps: switch between male and female voice and convert each time

Expected: audio should sound clearly different

Actual: worked fine

Status: pass


TC07 - Set pitch to maximum

Requirement: pitch control

Steps: move pitch slider all the way up, convert

Expected: audio should play fully with a higher pitch

Actual: audio stopped playing after about 2 seconds

Status: fail, logged as BUG03


TC08 - Download without converting first

Requirement: download feature

Steps: open the app fresh, click download without typing anything

Expected: download button should be disabled since nothing was converted

Actual: button was clickable and downloaded an empty file

Status: fail, logged as BUG04


TC09 - API test with Postman, valid request

Requirement: convert API

Steps: send a POST request with valid text and language

Expected: response should be 200 with the audio file link

Actual: worked as expected

Status: pass


TC10 - API test with Postman, empty text

Requirement: convert API

Steps: send a POST request with text left blank

Expected: response should be 400 with an error

Actual: response was 200, meaning the API accepted it, this is actually the root cause of BUG01

Status: fail


TC11 - API test with wrong language code

Requirement: convert API

Steps: send a POST request with a made up language code like xx-XX

Expected: response should be 400 with a clear error

Actual: response was 500, no useful error message

Status: fail, logged as BUG05


TC12 - Database check after successful conversion

Requirement: conversion history logging

Steps: convert some text, then check the history table in the database

Expected: a new row should be added with status success

Actual: worked as expected

Status: pass


TC13 - Database check after a failed conversion

Requirement: conversion history logging

Steps: cause a conversion to fail using a bad language code, then check the history table

Expected: row should be added with status failed

Actual: row was added but with status success even though it failed

Status: fail, logged as BUG06


TC14 - Regression check after BUG01 was fixed

Requirement: input validation

Steps: repeat TC02 and TC10

Expected: both should now reject empty text properly

Actual: both worked correctly this time

Status: pass


TC15 - Regression check after BUG06 was fixed

Requirement: conversion history logging

Steps: repeat TC13

Expected: row should show status failed

Actual: worked correctly this time

Status: pass
