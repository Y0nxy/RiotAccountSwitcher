# RiotAccountSwitcher
can switch session tokens without having to do it yourself every time, wanted to have multiple accounts

You have to:
1) log-in and make sure to tap the stay connected/remember me button
2) go to the folder "C:\Users\your user here\AppData\Local\Riot Games\Riot Client\Data"
3) create a folder and name it
4) move the "RiotGamesPrivateSettings.yaml" to that folder, that's your saved session.
5) make sure not to disconnect but kill the app from the task manager or close it and delete the session again if it appears
6) log-in to your second account and repeat 3-4
7) That's basically it, now you just open the py and type the name of the first folder to see if it works
Enjoy
