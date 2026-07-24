Text to Speech Converter - Test Documentation:

What this is?

This repo has the testing documents I made while manually testing the Text to Speech Converter web app. It has the test plan, test cases, a requirement traceability matrix, and bug reports I logged while testing.


What I tested?

I tested the main features of the app - entering text, choosing language and voice, changing speed and pitch, playing the audio, and downloading the file. I also tested the API using Postman and checked the database using SQL queries to see if the conversion history was being saved correctly.


Testing approach:

I followed the STLC process starting from requirement analysis, then test planning, writing test cases, setting up the environment, running the tests, and closing the cycle. I used Postman for API testing, MySQL for checking the database, and Apache JMeter to check how the app handles repeated requests. I logged bugs in a JIRA style format even though I did not have access to an actual JIRA account.


Key files:

test_plan.txt - the test plan with STLC steps
test_cases.md - test scenarios and test cases
rtm.md - requirement traceability matrix
bug_reports.md - bugs I found while testing


What I learned
Testing the API separately from the UI helped me catch a bug that the UI was hiding, since the button looked disabled but the request still went through. I also learned that checking the database directly can catch issues the UI never shows, like a failed conversion being marked as successful in the history table. Making the RTM before running tests helped me notice two requirements that only had positive test cases and no negative ones.
