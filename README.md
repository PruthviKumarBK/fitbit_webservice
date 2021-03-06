# FITBIT WEB SERVICE USING PYTHON

FITBIT Api's are authenticated by oAuth2.0. In here, there is a Python Web Service coded as a wrapper around Fitbit's conventional API's using Python's Falcon Web Services Framework. 

NOTE: THIS CODEBASE USES FALCON & GUNICORN TO  FACILITATE WEB SERVICE. GUNICORN WORKS ONLY ON UNIX/LINUX MACHINES. HENCE, THIS WILL BE OPERATIONAL ONLY ON LINUX DISTRO'S /UNIX MACHINES. WINDOWS IMPLEMENTATION IS WIP.

# Features:
  - oAuth Authorization callable via dedicated endpoint.
  - Fitbit config will be easy and manageable.
  - Multithreaded usage using gunicorn server to build seamless apps using Fitbit data.

# Setup:
- Create a valid fitbit account and setup an App here - https://dev.fitbit.com/apps/new
- Make notes of client ID and client secret.
- clone this repo; ensure to cd into the directory 'fitbit_webservice'.
- cd fitbit_webservice/config -> edit file named 'fitbit_wrapper_config.py', add client ID and client secret where its asked to; save.
- pip install all the requirements (Python=3). (NOTE: Always better to create a dedicated virtual environment. Either using Anaconda /Conventional Python)
- To start the web service, type the following command (whilst staying on 'fitbit_webservice' directory):
```sh
    gunicorn -b localhost:8000 fitbit_web_service:app --reload
```
- The above command must start gunicorn server locally and listen on port 8000 (Please feel free to change this to your convinience).
- Go to webserver and check with this endpoint:
```sh
    http://localhost:8000/processFitbitApi?keyword=todays_steps_real_time
```
- When the above request is served for the first time, oAuth will carry on with its magic to create valid token's for usage. Response from these requests will be self-explanatory.

# Keywords
- todays_steps_realtime: Get Real time steps (Until last sync with Fitbit) from fitbit.
- last_7_days_steps: Get total steps covered for last 7 days.
- todays_calories_realtime: Get calories burned for for current day.
- last_7_days_calories: Get calories burned data for last 7 days.
- todays_sedentary_minutes_realtime: Get sedentary minutes for current day.
- last_7_days_sedentary_minutes: Get sedentary minutes for last 7 days.
- todays_lightly_active_minutes_realtime: Get lightly active minutes for current day.
- todays_fairly_active_minutes_realtime: Get fairly active minutes for current day.
- todays_very_active_minutes_realtime: Get very active minutes for current day.
- last_7_days_lightly_active_minutes: Get lightly active minutes for last 7 days.
- last_7_days_fairly_active_minutes: Get fairly active minutes for last 7 days.
- last_7_days_very_active_minutes: Get very active minutes for last 7 days.
- todays_realtime_distance_covered: Get distance covered for current day.
- last_7_days_distance_covered: Get distnace covered for last 7 days.
- lifetime_activities_details: Get fitbit lifetime activities details. 
- get_friends_leader_board: Get friends leader board details. 
- todays_sleep_details: Get sleep details for current day.
- todays_heart_details: Get heart details for current day.

# Support
For any issues write to Pruthvi @ pruthvikumar.123@gmail.com. Ensure to have a valid subject line, detailed message with appropriate stack trace to expect prompt/quick response. 

# License
----
MIT License

Copyright (c) 2018 Pruthvi Kumar

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
