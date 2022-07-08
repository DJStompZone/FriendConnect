# Friend Connect

## WARNING

BEFORE YOU USE THIS TOOL, PLEASE READ THE FOLLOWING:
WE _AS CONTRIBUTORS_ ARE NOT RESPONSIBLE FOR ANY DAMAGE OR LOSS CAUSED BY THIS APP.
USE AN ALT ACCOUNT, JUST IN CASE THERE IS AN ISSUE WITH THIS METHOD.

## About

This is a project for minecraft bedrock that allows you to join servers via the in game friends tab. Allowing console players to connect to servers.

## How it works in game

[![A New Realms Replacement, A new method for joining servers on console.](https://res.cloudinary.com/marcomontalbano/image/upload/v1657258514/video_to_markdown/images/youtube--77qXotN9jGo-c05b58ac6eb4c4700831b2b3070cd403.jpg)](https://youtu.be/77qXotN9jGo "A New Realms Replacement, A new method for joining servers on console.")

## How to use it:

```js
const { Authflow, Titles } = require("prismarine-auth");
const { Session } = require("friend-connect");

new Authflow("FriendConnect", "./", {
	authTitle: Titles.MinecraftNintendoSwitch,
	deviceType: "Nintendo",
})
	.getXboxToken()
	.then((token) => {
		new Session(
			{
				hostName: "Friend Connect",
				worldName:
					"Fun Fact: Friend Connect was first revealed 7/7/2022",
				version: "1.19.2",
				protocol: 527,
				players: 0,
				maxPlayers: 20,
				ip: "", // Put your ip here
				port: 19132,
			},
			token
		);
	});
```

## To Do List

-   [ ] Add a way to fetch the version and protocol of the server on session Update.
-   [ ] Add automatically querying the player numbers from the server on session Update.
-   [ ] Add the ability to provide an array of strings to be chosen from for the hostName and worldName that is rotated through on session Update.
-   [ ] Check if the user owns any games if so send an error telling them to use an alt account.
-   [ ] Add an option to disable auto friending.

## Credit

This project is a js port of the [rtm516/MCXboxBroadcast](https://github.com/rtm516/MCXboxBroadcast) from java.

Friend Connect adds a key feature that makes the friending automated.

I worked with [rtm516](https://github.com/rtm516) to figure out the uri and headers for finding the followers of an xbox profile.
