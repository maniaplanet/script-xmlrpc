XmlRpc scripted callbacks and methods
=====================================

Callbacks
---------

### XmlRpc.CallbacksList

* Name: XmlRpc.CallbacksList
* Type: CallbackArray
* Description: A list with the names of all registered callbacks.
* Data:
	- Version >=2.0.0:
	```
	[
		{
			"responseid": "xyz", //< Facultative id passed by a script event  
			"callbacks": ["Callback1", "Callback2", "Callback3", ..., "CallbackN"] //< List of callbacks names  
		}
	]
	```

### XmlRpc.CallbacksList_Enabled

* Name: XmlRpc.CallbacksList_Enabled
* Type: CallbackArray
* Description: A list with the names of all enabled callbacks.
* Data:
	- Version >=2.0.0:
	```
	[
		"{
			"responseid": "xyz", //< Facultative id passed by a script event
			"callbacks": ["Callback1", "Callback2", "Callback3", ..., "CallbackN"] //< List of callbacks names
		}"
	]
	```

### XmlRpc.CallbacksList_Disabled

* Name: XmlRpc.CallbacksList_Disabled
* Type: CallbackArray
* Description: A list with the names of all disabled callbacks.
* Data:
	- Version >=2.0.0:
	```
	[
		"{
			"responseid": "xyz", //< Facultative id passed by a script event
			"callbacks": ["Callback1", "Callback2", "Callback3", ..., "CallbackN"] //< List of callbacks names
		}"
	]
	```

### XmlRpc.CallbackHelp

* Name: XmlRpc.CallbackHelp
* Type: CallbackArray
* Description: Description of a callback and its content. The array contains two items.
* Data:
	- Version >=2.0.0:
	```
	[
		"{
			"responseid": "xyz", //< Facultative id passed by a script event
			"callback": "CallbackName", //< The name of the described callback
			"available": true, //< Is the callback available in this game mode?
			"disabled": false //< Is the callback blocked?
		}", 
		"Description of the callback" //< The description of the callback
	]
	```

### XmlRpc.MethodsList

* Name: XmlRpc.MethodsList
* Type: CallbackArray
* Description: A list with the names of all registered methods.
* Data:
	- Version >=2.0.0:
	```
	[
		"{
			"responseid": "xyz", //< Facultative id passed by a script event
			"methods": ["Method1", "Method2", "Method3", ..., "MethodN"] //< List of callbacks names
		}"
	]
	```

### XmlRpc.MethodHelp

* Name: XmlRpc.MethodHelp
* Type: CallbackArray
* Description: Description of a method and its parameters. The array contains two items.
* Data:
	- Version >=2.0.0:
	```
	[
		"{
			"responseid": "xyz", //< Facultative id passed by a script event
			"method": "MethodName", //< The name of the described method
			"available": true //< Is the method available in this game mode?
		}", 
		"Description of the method" //< The description of the method
	]
	```

### XmlRpc.Documentation

* Name: XmlRpc.Documentation
* Type: CallbackArray
* Description: Documentation about the game mode xmlrpc methods and callbacks. The array contains two items.
* Data:
	- Version >=2.0.0:
	```
	[
		"{
			"responseid": "xyz" //< Facultative id passed by a script event
		}", 
		"Documentation" //< The documentation
	]
	```

### XmlRpc.ApiVersion

* Name: XmlRpc.ApiVersion
* Type: CallbackArray
* Description: Give the currently selected API version.
* Data:
	- Version >=2.0.0:
	```
	[
		"{
			"responseid": "xyz", //< Facultative id passed by a script event
			"version": "1.2.3-beta.4.5.6+build789" //< The API version in semver format
		}"
	]
	```

### XmlRpc.AllApiVersions

* Name: XmlRpc.AllApiVersions
* Type: CallbackArray
* Description: Give the latest and all available api versions.
* Data:
	- Version >=2.0.0:
	```
	[
		"{
			"responseid": "xyz", //< Facultative id passed by a script event
			"latest": "1.2.3-beta.4.5.6+build789" //< The latest API version in semver format
			"versions": ["1.0.0", "1.0.1", "1.1.0", "1.2.3-beta.4.5.6+build789"] //< All available versions
		}"
	]
	```

### Maniaplanet.StartServer_Start

* Name: Maniaplanet.StartServer_Start
* Type: CallbackArray
* Description: Callback sent when the "StartServer" section start.
* Data:
	- Version >=2.0.0:
	```
	[
		"{
			"restarted": false, //< true if the script was restarted
			"mode": {
				"updated": true, //< true if the mode was changed
				"name": "TimeAttack" //< The name of the mode
			},
			"time": 123450 //< Server time when the callback was sent
		}"
	]
	```

### Maniaplanet.StartServer_End

* Name: Maniaplanet.StartServer_End
* Type: CallbackArray
* Description: Callback sent when the "StartServer" section end.
* Data:
	- Version >=2.0.0:
	```
	[
		"{
			"restarted": false, //< true if the script was restarted
			"mode": {
				"updated": true, //< true if the mode was changed
				"name": "TimeAttack" //< The name of the mode
			},
			"time": 123450 //< Server time when the callback was sent
		}"
	]
	```

### Maniaplanet.StartMatch_Start

* Name: Maniaplanet.StartMatch_Start
* Type: CallbackArray
* Description: Callback sent when the "StartMatch" section start.
* Data:
	- Version >=2.0.0:
	```
	[
		"{
			"count": 123, //< Each time this section is played, this number is incremented by one
			"time": 123450 //< Server time when the callback was sent
		}"
	]
	```

### Maniaplanet.StartMatch_End

* Name: Maniaplanet.StartMatch_End
* Type: CallbackArray
* Description: Callback sent when the "StartMatch" section end.
* Data:
	- Version >=2.0.0:
	```
	[
		"{
			"count": 123, //< Each time this section is played, this number is incremented by one
			"time": 123450 //< Server time when the callback was sent
		}"
	]
	```

### Maniaplanet.StartMap_Start

* Name: Maniaplanet.StartMap_Start
* Type: CallbackArray
* Description: Callback sent when the "StartMap" section start.
* Data:
	- Version >=2.0.0:
	```
	[
		"{
			"count": 123, //< Each time this section is played, this number is incremented by one
			"restarted": false, //< true if the map was restarted, false otherwise
			"time": 123450, //< Server time when the callback was sent
			"map": {
				"uid": "4dNDBnxvcwDaXmQz4Qf5khJUSOd", //< Unique id of the map
				"name": "NameOfTheMap", //< Name of the map
				"filename": "Path\\To\\Map\\NameOfTheMap.Map.Gbx", //< Path to the file from the "Maps" folder
				"author": "AuthorLogin", //< Login of the author
				"environment": "Storm", //< Environment used to build the map
				"mood": "Day", //< Mood used to build the map
				"bronzetime": -1, //< Bronze medal time (valid in Trackmania only)
				"silvertime": -1, //< Silver medal time (valid in Trackmania only)
				"goldtime": -1, //< Gold medal time (valid in Trackmania only)
				"authortime": -1, //< Author medal time (valid in Trackmania only)
				"copperprice": 1008, //< Price of the map in coppers
				"laprace": false, //< Is the map a mutlilaps (valid in Trackmania only)
				"nblaps": 0, //< Number of laps if the map is a mutlilaps (valid in Trackmania only)
				"maptype": "ShootMania\\MapTypeArena", //< MapType used to validate the map
				"mapstyle": "StyleOfTheMap" //< Style applied to the map
			}
		}"
	]
	```

### Maniaplanet.StartMap_End

* Name: Maniaplanet.StartMap_End
* Type: CallbackArray
* Description: Callback sent when the "StartMap" section end.
* Data:
	- Version >=2.0.0:
	```
	[
		"{
			"count": 123, //< Each time this section is played, this number is incremented by one
			"restarted": false, //< true if the map was restarted, false otherwise
			"time": 123450, //< Server time when the callback was sent
			"map": {
				"uid": "4dNDBnxvcwDaXmQz4Qf5khJUSOd", //< Unique id of the map
				"name": "NameOfTheMap", //< Name of the map
				"filename": "Path\\To\\Map\\NameOfTheMap.Map.Gbx", //< Path to the file from the "Maps" folder
				"author": "AuthorLogin", //< Login of the author
				"environment": "Storm", //< Environment used to build the map
				"mood": "Day", //< Mood used to build the map
				"bronzetime": -1, //< Bronze medal time (valid in Trackmania only)
				"silvertime": -1, //< Silver medal time (valid in Trackmania only)
				"goldtime": -1, //< Gold medal time (valid in Trackmania only)
				"authortime": -1, //< Author medal time (valid in Trackmania only)
				"copperprice": 1008, //< Price of the map in coppers
				"laprace": false, //< Is the map a mutlilaps (valid in Trackmania only)
				"nblaps": 0, //< Number of laps if the map is a mutlilaps (valid in Trackmania only)
				"maptype": "ShootMania\\MapTypeArena", //< MapType used to validate the map
				"mapstyle": "StyleOfTheMap" //< Style applied to the map
			}
		}"
	]
	```

### Maniaplanet.StartRound_Start

* Name: Maniaplanet.StartRound_Start
* Type: CallbackArray
* Description: Callback sent when the "StartRound" section start.
* Data:
	- Version >=2.0.0:
	```
	[
		"{
			"count": 123, //< Each time this section is played, this number is incremented by one
			"time": 123450 //< Server time when the callback was sent
		}"
	]
	```

### Maniaplanet.StartRound_End

* Name: Maniaplanet.StartRound_End
* Type: CallbackArray
* Description: Callback sent when the "StartRound" section end.
* Data:
	- Version >=2.0.0:
	```
	[
		"{
			"count": 123, //< Each time this section is played, this number is incremented by one
			"time": 123450 //< Server time when the callback was sent
		}"
	]
	```

### Maniaplanet.StartTurn_Start

* Name: Maniaplanet.StartTurn_Start
* Type: CallbackArray
* Description: Callback sent when the "StartTurn" section start.
* Data:
	- Version >=2.0.0:
	```
	[
		"{
			"count": 123, //< Each time this section is played, this number is incremented by one
			"time": 123450 //< Server time when the callback was sent
		}"
	]
	```

### Maniaplanet.StartTurn_End

* Name: Maniaplanet.StartTurn_End
* Type: CallbackArray
* Description: Callback sent when the "StartTurn" section end.
* Data:
	- Version >=2.0.0:
	```
	[
		"{
			"count": 123, //< Each time this section is played, this number is incremented by one
			"time": 123450 //< Server time when the callback was sent
		}"
	]
	```

### Maniaplanet.StartPlayLoop

* Name: Maniaplanet.StartPlayLoop
* Type: CallbackArray
* Description: Callback sent when the "PlayLoop" section start.
* Data:
	- Version >=2.0.0:
	```
	[
		"{
			"count": 123, //< Each time this section is played, this number is incremented by one
			"time": 123450 //< Server time when the callback was sent
		}"
	]
	```

### Maniaplanet.EndPlayLoop

* Name: Maniaplanet.EndPlayLoop
* Type: CallbackArray
* Description: Callback sent when the "PlayLoop" section end.
* Data:
	- Version >=2.0.0:
	```
	[
		"{
			"count": 123, //< Each time this section is played, this number is incremented by one
			"time": 123450 //< Server time when the callback was sent
		}"
	]
	```

### Maniaplanet.EndTurn_Start

* Name: Maniaplanet.EndTurn_Start
* Type: CallbackArray
* Description: Callback sent when the "EndTurn" section start.
* Data:
	- Version >=2.0.0:
	```
	[
		"{
			"count": 123, //< Each time this section is played, this number is incremented by one
			"time": 123450 //< Server time when the callback was sent
		}"
	]
	```

### Maniaplanet.EndTurn_End

* Name: Maniaplanet.EndTurn_End
* Type: CallbackArray
* Description: Callback sent when the "EndTurn" section end.
* Data:
	- Version >=2.0.0:
	```
	[
		"{
			"count": 123, //< Each time this section is played, this number is incremented by one
			"time": 123450 //< Server time when the callback was sent
		}"
	]
	```

### Maniaplanet.EndRound_Start

* Name: Maniaplanet.EndRound_Start
* Type: CallbackArray
* Description: Callback sent when the "EndRound" section start.
* Data:
	- Version >=2.0.0:
	```
	[
		"{
			"count": 123, //< Each time this section is played, this number is incremented by one
			"time": 123450 //< Server time when the callback was sent
		}"
	]
	```

### Maniaplanet.EndRound_End

* Name: Maniaplanet.EndRound_End
* Type: CallbackArray
* Description: Callback sent when the "EndRound" section end.
* Data:
	- Version >=2.0.0:
	```
	[
		"{
			"count": 123, //< Each time this section is played, this number is incremented by one
			"time": 123450 //< Server time when the callback was sent
		}"
	]
	```

### Maniaplanet.EndMap_Start

* Name: Maniaplanet.EndMap_Start
* Type: CallbackArray
* Description: Callback sent when the "EndMap" section start.
* Data:
	- Version >=2.0.0:
	```
	[
		"{
			"count": 123, //< Each time this section is played, this number is incremented by one
			"time": 123450, //< Server time when the callback was sent
			"map": {
				"uid": "4dNDBnxvcwDaXmQz4Qf5khJUSOd", //< Unique id of the map
				"name": "NameOfTheMap", //< Name of the map
				"filename": "Path\\To\\Map\\NameOfTheMap.Map.Gbx", //< Path to the file from the "Maps" folder
				"author": "AuthorLogin", //< Login of the author
				"environment": "Storm", //< Environment used to build the map
				"mood": "Day", //< Mood used to build the map
				"bronzetime": -1, //< Bronze medal time (valid in Trackmania only)
				"silvertime": -1, //< Silver medal time (valid in Trackmania only)
				"goldtime": -1, //< Gold medal time (valid in Trackmania only)
				"authortime": -1, //< Author medal time (valid in Trackmania only)
				"copperprice": 1008, //< Price of the map in coppers
				"laprace": false, //< Is the map a mutlilaps (valid in Trackmania only)
				"nblaps": 0, //< Number of laps if the map is a mutlilaps (valid in Trackmania only)
				"maptype": "ShootMania\\MapTypeArena", //< MapType used to validate the map
				"mapstyle": "StyleOfTheMap" //< Style applied to the map
			}
		}"
	]
	```

### Maniaplanet.EndMap_End

* Name: Maniaplanet.EndMap_End
* Type: CallbackArray
* Description: Callback sent when the "EndMap" section end.
* Data:
	- Version >=2.0.0:
	```
	[
		"{
			"count": 123, //< Each time this section is played, this number is incremented by one
			"time": 123450, //< Server time when the callback was sent
			"map": {
				"uid": "4dNDBnxvcwDaXmQz4Qf5khJUSOd", //< Unique id of the map
				"name": "NameOfTheMap", //< Name of the map
				"filename": "Path\\To\\Map\\NameOfTheMap.Map.Gbx", //< Path to the file from the "Maps" folder
				"author": "AuthorLogin", //< Login of the author
				"environment": "Storm", //< Environment used to build the map
				"mood": "Day", //< Mood used to build the map
				"bronzetime": -1, //< Bronze medal time (valid in Trackmania only)
				"silvertime": -1, //< Silver medal time (valid in Trackmania only)
				"goldtime": -1, //< Gold medal time (valid in Trackmania only)
				"authortime": -1, //< Author medal time (valid in Trackmania only)
				"copperprice": 1008, //< Price of the map in coppers
				"laprace": false, //< Is the map a mutlilaps (valid in Trackmania only)
				"nblaps": 0, //< Number of laps if the map is a mutlilaps (valid in Trackmania only)
				"maptype": "ShootMania\\MapTypeArena", //< MapType used to validate the map
				"mapstyle": "StyleOfTheMap" //< Style applied to the map
			}
		}"
	]
	```

### Maniaplanet.EndMatch_Start

* Name: Maniaplanet.EndMatch_Start
* Type: CallbackArray
* Description: Callback sent when the "EndMatch" section start.
* Data:
	- Version >=2.0.0:
	```
	[
		"{
			"count": 123, //< Each time this section is played, this number is incremented by one
			"time": 123450 //< Server time when the callback was sent
		}"
	]
	```

### Maniaplanet.EndMatch_End

* Name: Maniaplanet.EndMatch_End
* Type: CallbackArray
* Description: Callback sent when the "EndMatch" section end.
* Data:
	- Version >=2.0.0:
	```
	[
		"{
			"count": 123, //< Each time this section is played, this number is incremented by one
			"time": 123450 //< Server time when the callback was sent
		}"
	]
	```

### Maniaplanet.EndServer_Start

* Name: Maniaplanet.EndServer_Start
* Type: CallbackArray
* Description: Callback sent when the "EndServer" section start.
* Data:
	- Version >=2.0.0:
	```
	[
		"{
			"time": 123450 //< Server time when the callback was sent
		}"
	]
	```

### Maniaplanet.EndServer_End

* Name: Maniaplanet.EndServer_End
* Type: CallbackArray
* Description: Callback sent when the "EndServer" section end.
* Data:
	- Version >=2.0.0:
	```
	[
		"{
			"time": 123450 //< Server time when the callback was sent
		}"
	]
	```

### Maniaplanet.LoadingMap_Start

* Name: Maniaplanet.LoadingMap_Start
* Type: CallbackArray
* Description: Callback sent when the server starts to load a map.
* Data:
	- Version >=2.0.0:
	```
	[
		"{
			"restarted": false, //< true if the map was restarted, false otherwise
			"time": 123450 //< Server time when the callback was sent
		}"
	]
	```

### Maniaplanet.LoadingMap_End

* Name: Maniaplanet.LoadingMap_End
* Type: CallbackArray
* Description: Callback sent when the server finishes to load a map.
* Data:
	- Version >=2.0.0:
	```
	[
		"{
			"restarted": false, //< true if the map was restarted, false otherwise
			"time": 123450, //< Server time when the callback was sent
			"map": {
				"uid": "4dNDBnxvcwDaXmQz4Qf5khJUSOd", //< Unique id of the map
				"name": "NameOfTheMap", //< Name of the map
				"filename": "Path\\To\\Map\\NameOfTheMap.Map.Gbx", //< Path to the file from the "Maps" folder
				"author": "AuthorLogin", //< Login of the author
				"environment": "Storm", //< Environment used to build the map
				"mood": "Day", //< Mood used to build the map
				"bronzetime": -1, //< Bronze medal time (valid in Trackmania only)
				"silvertime": -1, //< Silver medal time (valid in Trackmania only)
				"goldtime": -1, //< Gold medal time (valid in Trackmania only)
				"authortime": -1, //< Author medal time (valid in Trackmania only)
				"copperprice": 1008, //< Price of the map in coppers
				"laprace": false, //< Is the map a mutlilaps (valid in Trackmania only)
				"nblaps": 0, //< Number of laps if the map is a mutlilaps (valid in Trackmania only)
				"maptype": "ShootMania\\MapTypeArena", //< MapType used to validate the map
				"mapstyle": "StyleOfTheMap" //< Style applied to the map
			}
		}"
	]
	```

### Maniaplanet.UnloadingMap_Start

* Name: Maniaplanet.UnloadingMap_Start
* Type: CallbackArray
* Description: Callback sent when the server starts to unload a map.
* Data:
	- Version >=2.0.0:
	```
	[
		"{
			"time": 123450, //< Server time when the callback was sent
			"map": {
				"uid": "4dNDBnxvcwDaXmQz4Qf5khJUSOd", //< Unique id of the map
				"name": "NameOfTheMap", //< Name of the map
				"filename": "Path\\To\\Map\\NameOfTheMap.Map.Gbx", //< Path to the file from the "Maps" folder
				"author": "AuthorLogin", //< Login of the author
				"environment": "Storm", //< Environment used to build the map
				"mood": "Day", //< Mood used to build the map
				"bronzetime": -1, //< Bronze medal time (valid in Trackmania only)
				"silvertime": -1, //< Silver medal time (valid in Trackmania only)
				"goldtime": -1, //< Gold medal time (valid in Trackmania only)
				"authortime": -1, //< Author medal time (valid in Trackmania only)
				"copperprice": 1008, //< Price of the map in coppers
				"laprace": false, //< Is the map a mutlilaps (valid in Trackmania only)
				"nblaps": 0, //< Number of laps if the map is a mutlilaps (valid in Trackmania only)
				"maptype": "ShootMania\\MapTypeArena", //< MapType used to validate the map
				"mapstyle": "StyleOfTheMap" //< Style applied to the map
			}
		}"
	]
	```

### Maniaplanet.UnloadingMap_End

* Name: Maniaplanet.UnloadingMap_End
* Type: CallbackArray
* Description: Callback sent when the server finishes to unload a map.
* Data:
	- Version >=2.0.0:
	```
	[
		"{
			"time": 123450 //< Server time when the callback was sent
		}"
	]
	```

### Maniaplanet.Podium_Start

* Name: Maniaplanet.Podium_Start
* Type: CallbackArray
* Description: Callback sent when the podium sequence starts.
* Data:
	- Version >=2.0.0:
	```
	[
		"{
			"time": 123450 //< Server time when the callback was sent
		}"
	]
	```

### Maniaplanet.Podium_End

* Name: Maniaplanet.Podium_End
* Type: CallbackArray
* Description: Callback sent when the podium sequence ends.
* Data:
	- Version >=2.0.0:
	```
	[
		"{
			"time": 123450 //< Server time when the callback was sent
		}"
	]
	```

### Maniaplanet.ChannelProgression_Start

* Name: Maniaplanet.ChannelProgression_Start
* Type: CallbackArray
* Description: Callback sent when the channel progression sequence starts.
* Data:
	- Version >=2.0.0:
	```
	[
		"{
			"time": 123450 //< Server time when the callback was sent
		}"
	]
	```

### Maniaplanet.ChannelProgression_End

* Name: Maniaplanet.ChannelProgression_End
* Type: CallbackArray
* Description: Callback sent when the channel progression sequence ends.
* Data:
	- Version >=2.0.0:
	```
	[
		"{
			"time": 123450 //< Server time when the callback was sent
		}"
	]
	```

### Maniaplanet.Mode.UseTeams

* Name: Maniaplanet.Mode.UseTeams
* Type: CallbackArray
* Description: Tell if the game mode uses teams or not.
* Data:
	- Version >=2.0.0:
	```
	[
		"{
			"responseid": "xyz", //< Facultative id passed by a script event
			"teams": true //< true if the game mode uses teams, false otherwise
		}"
	]
	```

### Maniaplanet.WarmUp.Status

* Name: Maniaplanet.WarmUp.Status
* Type: CallbackArray
* Description: The status of the warmup.
* Data:
	- Version >=2.0.0:
	```
	[
		"{
			"responseid": "xyz", //< Facultative id passed by a script event
			"available": true, //< true if a warmup is available in the game mode, false otherwise
			"active": true //< true if a warmup is ongoing, false otherwise
		}"
	]
	```

### UI.Event.Default

* Name: UI.Event.Default
* Type: CallbackArray
* Description: Callback sent when the event type is not yet supported by the XmlRpc library.
* Data:
	- Version >=2.0.0:
	```
	[
		"{
			"time": 123456, //< Server time when the event occured,
			"type": "::EType::EventType" //< The type of event
		}"
	]
	```
	
### UI.Event.OnModuleCustomEvent

* Name: UI.Event.OnModuleCustomEvent
* Type: CallbackArray
* Description: Callback sent when a module triggers a custom event.
* Data:
	- Version >=2.0.0:
	```
	[
		"{
			"time": 123456 //< Server time when the event occured,
			"login": "PlayerLogin", //< Login of the player who requested a new action
			"moduletype": "EModuleType::Store", //< The type of module that triggered the event
			"param1": "SomeParam", //< First custom param of the event
			"param2":["Some", "Other", "Params"] //< Second custom param of the event
		}"
	]
	```
	
### UI.Event.OnModuleShowRequest

* Name: UI.Event.OnModuleShowRequest
* Type: CallbackArray
* Description: Callback sent when a module requests to be shown.
* Data:
	- Version >=2.0.0:
	```
	[
		"{
			"time": 123456 //< Server time when the event occured,
			"login": "PlayerLogin", //< Login of the player who received the request
			"moduletype": "EModuleType::Store" //< The type of module that sent the request
		}"
	]
	```
	
### UI.Event.OnModuleHideRequest

* Name: UI.Event.OnModuleHideRequest
* Type: CallbackArray
* Description: Callback sent when a module requests to be hidden.
* Data:
	- Version >=2.0.0:
	```
	[
		"{
			"time": 123456 //< Server time when the event occured,
			"login": "PlayerLogin", //< Login of the player who received the request
			"moduletype": "EModuleType::Store" //< The type of module that sent the request
		}"
	]
	```
	
### UI.Event.OnModuleStorePurchase

* Name: UI.Event.OnModuleStorePurchase
* Type: CallbackArray
* Description: Callback sent when a player buys something in the store.
* Data:
	- Version >=2.0.0:
	```
	[
		"{
			"time": 123456 //< Server time when the event occured,
			"login": "PlayerLogin", //< Login of the player who bought something
			"item": "ItemName", //< The name of the item
			"quantity": "5" //< The amount of items bought
		}"
	]
	```
	
### UI.Event.OnModuleInventoryDrop

* Name: UI.Event.OnModuleInventoryDrop
* Type: CallbackArray
* Description: Callback sent when a player drops an item from its inventory.
* Data:
	- Version >=2.0.0:
	```
	[
		"{
			"time": 123456 //< Server time when the event occured,
			"login": "PlayerLogin", //< Login of the player who dropped the item
			"item": "ItemName" //< The name of the item
		}"
	]
	```
	
### UI.Event.OnModuleInventoryEquip

* Name: UI.Event.OnModuleInventoryEquip
* Type: CallbackArray
* Description: Callback sent when a player equips an item from its inventory.
* Data:
	- Version >=2.0.0:
	```
	[
		"{
			"time": 123456 //< Server time when the event occured,
			"login": "PlayerLogin", //< Login of the player who equipped the item
			"item": "ItemName" //< The name of the item
		}"
	]
	```
	
### Maniaplanet.Pause.Status

* Name: Maniaplanet.Pause.Status
* Type: CallbackArray
* Description: The status of the pause.
* Data:
	- Version >=2.0.0:
	```
	[
		"{
			"responseid": "xyz", //< Facultative id passed by a script event
			"available": true, //< true if a pause is available in the game mode, false otherwise
			"active": true //< true if there is an ongoing pause, false otherwise
		}"
	]
	```

### Shootmania.Event.Default

* Name: Shootmania.Event.Default
* Type: CallbackArray
* Description: Callback sent when the event type is not yet supported by the XmlRpc library.
* Data:
	- Version >=2.0.0:
	```
	[
		"{
			"time": 123456, //< Server time when the event occured,
			"type": "::EType::EventType" //< The type of event
		}"
	]
	```
	
### Shootmania.Event.OnShoot

* Name: Shootmania.Event.OnShoot
* Type: CallbackArray
* Description: Callback sent when a player shoots.
* Data:
	- Version >=2.0.0:
	```
	[
		"{
			"time": 123456 //< Server time when the event occured,
			"shooter": "ShooterLogin", //< Login of the player who shot
			"weapon": 2 //< Id of the weapon [1-Laser, 2-Rocket, 3-Nucleus, 5-Arrow]
		}"
	]
	```
	
### Shootmania.Event.OnHit

* Name: Shootmania.Event.OnHit
* Type: CallbackArray
* Description: Callback sent when a player is hit.
* Data:
	- Version >=2.0.0:
	```
	[
		"{
			"time": 123456 //< Server time when the event occured,
			"shooter": "ShooterLogin", //< Login of the player who shot
			"victim": "VictimLogin", //< Login of the player who got hit
			"weapon": 2, //< Id of the weapon [1-Laser, 2-Rocket, 3-Nucleus, 5-Arrow]
			"damage": 100, //< Amount of damaged done by the hit
			"points": 2, //< Amount of points scored by the shooter
			"distance": 45.578, //< Distance between the victim and the shooter at the time of the hit
			"shooterposition": { "x": 19.3, "y": 9.3", "z": 59.9 }, //< Position of the shooter when his projectile hits the victim
			"victimposition": { "x": 87.6, "y": 10.0, "z": 84.5 } //< Position of the victim when he's hit by the projectile
		}"
	]
	```
	
### Shootmania.Event.OnNearMiss

* Name: Shootmania.Event.OnNearMiss
* Type: CallbackArray
* Description: Callback sent when a player dodges a projectile.
* Data:
	- Version >=2.0.0:
	```
	[
		"{
			"time": 123456 //< Server time when the event occured,
			"shooter": "ShooterLogin", //< Login of the player who shot
			"victim": "VictimLogin", //< Login of the player who dodged
			"weapon": 1, //< Id of the weapon [1-Laser, 2-Rocket, 3-Nucleus, 5-Arrow]
			"distance": 0.587, //< Distance of the near miss
			"shooterposition": { "x": 19.3, "y": 9.3", "z": 59.9 }, //< Position of the shooter when his projectile misses the victim
			"victimposition": { "x": 87.6, "y": 10.0, "z": 84.5 } //< Position of the victim when he dodged the projectile
		}"
	]
	```
	
### Shootmania.Event.OnArmorEmpty

* Name: Shootmania.Event.OnArmorEmpty
* Type: CallbackArray
* Description: Callback sent when a player is eliminated.
* Data:
	- Version >=2.0.0:
	```
	[
		"{
			"time": 123456 //< Server time when the event occured,
			"shooter": "ShooterLogin", //< Login of the player who eliminated the victim
			"victim": "VictimLogin", //< Login of the player who got eliminated
			"weapon": 2, //< Id of the weapon [1-Laser, 2-Rocket, 3-Nucleus, 5-Arrow]
			"distance": 65.948, //< Distance between the victim and the shooter at the time of the elimination
			"shooterposition": { "x": 19.3, "y": 9.3", "z": 59.9 }, //< Position of the shooter when the victim is eliminated
			"victimposition": { "x": 87.6, "y": 10.0, "z": 84.5 } //< Position of the victim when he's eliminated
		}"
	]
	```
	
### Shootmania.Event.OnCapture

* Name: Shootmania.Event.OnCapture
* Type: CallbackArray
* Description: Callback sent when a landmark is captured.
* Data:
	- Version >=2.0.0:
	```
	[
		"{
			"time": 123456 //< Server time when the event occured,
			"players": ["Player1", "Player2", "Player3"], //< Logins of the players who were on the landmark when it was captured
			"landmark": { //< Info about the captured landmark
				"tag": "LandmarkTag",
				"order": 5,
				"id": "#3",
				"position": { "x": 87.6, "y": 10.0, "z": 84.5 }
			}
		}"
	]
	```
	
### Shootmania.Event.OnShotDeny

* Name: Shootmania.Event.OnShotDeny
* Type: CallbackArray
* Description: Callback sent when a player denies a projectile.
* Data:
	- Version >=2.0.0:
	```
	[
		"{
			"time": 123456 //< Server time when the event occured,
			"shooter": "ShooterLogin", //< Login of the player who denied the projectile
			"victim": "VictimLogin", //< Login of the player who got denied
			"shooterweapon": 1, //< Id of the weapon [1-Laser, 2-Rocket, 3-Nucleus, 5-Arrow]
			"victimweapon": 2 //< Id of the weapon [1-Laser, 2-Rocket, 3-Nucleus, 5-Arrow]
		}"
	]
	```
	
### Shootmania.Event.OnFallDamage

* Name: Shootmania.Event.OnFallDamage
* Type: CallbackArray
* Description: Callback sent when a player suffers fall damage.
* Data:
	- Version >=2.0.0:
	```
	[
		"{
			"time": 123456 //< Server time when the event occured,
			"victim": "VictimLogin", //< Login of the player who fell
		}"
	]
	```
	
### Shootmania.Event.OnCommand

* Name: Shootmania.Event.OnCommand
* Type: CallbackArray
* Description: Callback sent when a command is executed on the server.
* Data:
	- Version >=2.0.0:
	```
	[
		"{
			"time": 123456 //< Server time when the event occured,
			"name": "CommandName", //< Name of the command
			"value": { //< The value passed by the command
				"boolean": true,
				"integer": 123,
				"real": 123.456,
				"text": "an example value"
			}
		}"
	]
	```
	
### Shootmania.Event.OnPlayerAdded

* Name: Shootmania.Event.OnPlayerAdded
* Type: CallbackArray
* Description: Callback sent when a player joins the server.
* Data:
	- Version >=2.0.0:
	```
	[
		"{
			"time": 123456 //< Server time when the event occured,
			"login": "PlayerLogin",
			"name": "Name of the player",
			"team": 0,
			"zone": "World|Europe|France|Outre-mer|Reunion",
			"language": "en",
			"ladderrank": 123456,
			"ladderpoints": 789.321
		}"
	]
	```
	
### Shootmania.Event.OnPlayerRemoved

* Name: Shootmania.Event.OnPlayerRemoved
* Type: CallbackArray
* Description: Callback sent when a player leaves the server.
* Data:
	- Version >=2.0.0:
	```
	[
		"{
			"time": 123456 //< Server time when the event occured,
			"login": "PlayerLogin"
		}"
	]
	```
	
### Shootmania.Event.OnPlayerRequestRespawn

* Name: Shootmania.Event.OnPlayerRequestRespawn
* Type: CallbackArray
* Description: Callback sent when a player presses the respawn button.
* Data:
	- Version >=2.0.0:
	```
	[
		"{
			"time": 123456 //< Server time when the event occured,
			"login": "PlayerLogin"
		}"
	]
	```
	
### Shootmania.Event.OnActionCustomEvent

* Name: Shootmania.Event.OnActionCustomEvent
* Type: CallbackArray
* Description: Callback sent when an action triggers a custom event.
* Data:
	- Version >=2.0.0:
	```
	[
		"{
			"time": 123456 //< Server time when the event occured,
			"shooter": "ShooterLogin", //< Login of the player who shot if any
			"victim": "VictimLogin", //< Login of the player who got hit if any
			"actionid": "NameOfTheAction", //< Id of the action that triggered the event
			"param1": "SomeParam", //< First custom param of the event
			"param2":["Some", "Other", "Params"] //< Second custom param of the event
		}"
	]
	```
	
### Shootmania.Event.OnActionEvent

* Name: Shootmania.Event.OnActionEvent
* Type: CallbackArray
* Description: Callback sent when a player triggers an action.
* Data:
	- Version >=2.0.0:
	```
	[
		"{
			"time": 123456 //< Server time when the event occured,
			"login": "PlayerLogin", //< Login of the player who triggered the action
			"actioninput": "" //< The input pressed to trigger the action
		}"
	]
	```
	
### Shootmania.Event.OnPlayerTouchesObject

* Name: Shootmania.Event.OnPlayerTouchesObject
* Type: CallbackArray
* Description: Callback sent when a player touches an object.
* Data:
	- Version >=2.0.0:
	```
	[
		"{
			"time": 123456 //< Server time when the event occured,
			"login": "PlayerLogin", //< Login of the player who touched the object
			"objectid": "#456", //< The id of the object
			"modelid": "#123", //< The id of the object model
			"modelname": "ObjectName" //< The name of the object model
		}"
	]
	```
	
### Shootmania.Event.OnPlayerTriggersSector

* Name: Shootmania.Event.OnPlayerTriggersSector
* Type: CallbackArray
* Description: Callback sent when a player triggers a sector.
* Data:
	- Version >=2.0.0:
	```
	[
		"{
			"time": 123456 //< Server time when the event occured,
			"login": "PlayerLogin", //< Login of the player who triggered the sector
			"sectorid": "#123" //< Id of the triggered sector
		}"
	]
	```
	
### Shootmania.Event.OnPlayerThrowsObject

* Name: Shootmania.Event.OnPlayerThrowsObject
* Type: CallbackArray
* Description: Callback sent when a player throws an object.
* Data:
	- Version >=2.0.0:
	```
	[
		"{
			"time": 123456 //< Server time when the event occured,
			"login": "PlayerLogin", //< Login of the player who threw the object
			"objectid": "#456", //< The id of the object
			"modelid": "#123", //< The id of the object model
			"modelname": "ObjectName" //< The name of the object model
		}"
	]
	```
	
### Shootmania.Event.OnPlayerRequestActionChange

* Name: Shootmania.Event.OnPlayerRequestActionChange
* Type: CallbackArray
* Description: Callback sent when a player requests to use another action.
* Data:
	- Version >=2.0.0:
	```
	[
		"{
			"time": 123456 //< Server time when the event occured,
			"login": "PlayerLogin", //< Login of the player who requested a new action
			"actionchange": 1 //< Can be -1 (request previous action) or 1 (request next action)
		}"
	]
	```
	
### Shootmania.Scores

* Name: Shootmania.Scores
* Type: CallbackArray
* Description: Teams and players scores.
* Data:
	- Version >=2.0.0: 
	```
	[
		"{
			"responseid": "xyz", //< Facultative id passed by a script event
			"section": "EndRound", //< Current progress of the match. Can be "" | "EndRound" | "EndMap" | "EndMatch"
			"useteams": true, //< The game mode use teams or not
			"winnerteam": 1, //< The team who won the match, can be -1 (no winner), 0 or 1
			"winnerplayer": "PlayerLogin1", //< Login of the player who won the match
			"teams": [ //< Scores of the teams
				{
					"id": 0,
					"name": "blue",
					"roundpoints": 498, 
					"mappoints": 46,
					"matchpoints": 9,
				},
				{
					"id": 1,
					"name": "red",
					"roundpoints": 365,
					"mappoints": 45,
					"matchpoints": 2,
				}
			],
			"players": [ //< Scores of the players
				{
					"login": "PlayerLogin1",
					"name": "Player#1",
					"rank": 1, //< Rank of the player in the match
					"roundpoints": 456,
					"mappoints": 345,
					"matchpoints": 64
				},
				{
					"login": "PlayerLogin2",
					"name": "Player#2",
					"rank": 2,
					"roundpoints": 234,
					"mappoints": 123,
					"matchpoints": 32
				}
			]
		}"
	]
	```
	
### Shootmania.UI.Properties

* Name: Shootmania.UI.Properties
* Type: CallbackArray
* Description: Information about the default UI components of Maniaplanet (map info, chat, ladder recap, ...).
* Data:
	- Version >=2.0.0: 
	```
	[
		"{
			"responseid": "xyz", //< Facultative id passed by a script event
		}",
		"
		<ui_properties>
		  <!-- Notifications displayed on the left of the screen -->
		  <notices visible="true" />
		  <!-- The map name and author displayed on the top right of the screen when viewing the scores table -->
		  <map_info visible="true" />
		  <!--
		    The server chat displayed on the bottom right of the screen
		    The offset values range from 0. to -3.2 for x and from 0. to 1.8 for y
		    The linecount property must be between 0 and 40
		  -->
		  <chat visible="true" offset="0. 0." linecount="5" />
		  <!-- Countdown displayed on the top of the screen -->
		  <countdown visible="true" pos="0. 85." />
		  <!-- Crosshair displayed on the center of the screen -->
		  <crosshair visible="true" />
		  <!-- Gauges displayed on the bottom of the screen -->
		  <gauges visible="true" />
		  <!-- Consumables displayed on the bottom of the screen -->
		  <consumables visible="true" />
		  <!-- 3, 2, 1, Go! message displayed on the middle of the screen when spawning -->
		  <go visible="true" />
		  <!-- The avatar of the last player speaking in the chat displayed above the chat -->
		  <chat_avatar visible="true" />
		  <!-- Ladder progression box displayed on the top of the screen at the end of the map -->
		  <endmap_ladder_recap visible="true" />
		  <!-- Scores table displayed in the middle of the screen -->
			<scorestable alt_visible="true" />
		</ui_properties>
		",
		"{
			"notices": { //< Notifications displayed on the left of the screen
				"visible": true
			},
			"map_info": { //< The map name and author displayed on the top right of the screen when viewing the scores table
				"visible": true
			},
			"chat": { //< The server chat displayed on the bottom right of the screen
				"visible": true,
				"offset": { "x": 0.0, "y": 0.0 }, //< The offset values range from 0. to -3.2 for x and from 0. to 1.8 for y
				"linecount": 5 //< The linecount property must be between 0 and 40
			},
			"countdown": { //< Countdown displayed on the top of the screen
				"visible": true,
				"pos": { "x": 0.0, "y": 85.0 }
			},
			"crosshair": { //< Crosshair displayed on the center of the screen
				"visible": true
			},
			"gauges": { //< Gauges displayed on the bottom of the screen
				"visible": true
			},
			"consumables": { //< Consumables displayed on the bottom of the screen
				"visible": true
			},
			"go": { //< 3, 2, 1, Go! message displayed on the middle of the screen when spawning
				"visible": true
			},
			"chat_avatar": { //< The avatar of the last player speaking in the chat displayed above the chat
				"visible": true
			},
			"endmap_ladder_recap": { //< Ladder progression box displayed on the top of the screen at the end of the map
				"visible": true
			},
			"scorestable": { //< Scores table displayed in the middle of the screen
				"alt_visible": true
			}
		}"
	]
	```
	
### Maniaplanet.WarmUp.Start

* Name: Maniaplanet.WarmUp.Start
* Type: CallbackArray
* Description: Callback sent when the warmup starts.
* Data:
	- Version >=2.0.0:
	```
	[
		"{}"
	]
	```

### Maniaplanet.WarmUp.End

* Name: Maniaplanet.WarmUp.End
* Type: CallbackArray
* Description: Callback sent when the warmup ends.
* Data:
	- Version >=2.0.0:
	```
	[
		"{}"
	]
	```

### Shootmania.Elite.StartTurn

* Name: Shootmania.Elite.StartTurn
* Type: CallbackArray
* Description: Information about the starting turn.
* Data:
	- Version >=2.0.0:
	```
	[
		"{
			"attacker": "login1", //< the login of the attacker
			"defenders": ["login2", "login3", "login4"] //< the logins of the defenders
		}"
	]
	```

### Shootmania.Elite.EndTurn

* Name: Shootmania.Elite.EndTurn
* Type: CallbackArray
* Description: Information about the ending turn.
* Data:
	- Version >=2.0.0:
	```
	[
		"{
			"victorytype": 1 //< Describe how the turn was won. 1 = time limit, 2 = capture, 3 = attacker eliminated, 4 = defenders eliminated
		}"
	]
	```

### Shootmania.Joust.OnReload

* Name: Shootmania.Joust.OnReload
* Type: CallbackArray
* Description: Callback sent when a player capture a pole to reload its weapons.
* Data:
	- Version >=2.0.0:
	```
	[
		"{
			"player": "PlayerLogin1" //< Login of the player who reloaded
		}"
	]
	```

### Shootmania.Joust.SelectedPlayers

* Name: Shootmania.Joust.SelectedPlayers
* Type: CallbackArray
* Description: Callback sent at the beginning of the round with the logins of the players selected to play the round.
* Data:
	- Version >=2.0.0:
	```
	[
		"{
			"players": ["PlayerLogin1", "PlayerLogin2"] //< Logins of the two players selected for the round
		}"
	]
	```

### Shootmania.Joust.RoundResult

* Name: Shootmania.Joust.RoundResult
* Type: CallbackArray
* Description: Callback sent at the end of the round with the scores of the two players.
* Data:
	- Version >=2.0.0:
	```
	[
		"{
			"players": [
				{
					"login": "PlayerLogin1",
					"score": 5
				}, {
					"login": "PlayerLogin2",
					"score": 7
				}
			]
		}"
	]
	```

### Shootmania.Royal.Points

* Name: Shootmania.Royal.Points
* Type: CallbackArray
* Description: Callback sent when a player scores some points.
* Data:
	- Version >=2.0.0:
	```
	[
		"{
			"login": "PlayerLogin", //< Login of the player who scored the points
			"type": "Pole", //< The type of points. Can be: Pole, Hit or Survival
			"points": 12 //< The number of points scored
		}"
	]
	```

### Shootmania.Royal.PlayerSpawn

* Name: Shootmania.Royal.PlayerSpawn
* Type: CallbackArray
* Description: Callback sent when a player is spawned.
* Data:
	- Version >=2.0.0:
	```
	[
		"{
			"login": "PlayerLogin", //< Login of the spawned player
			"respawn": true //< false if it is the initial player spawn in the round. true if it is a respawn.
		}"
	]
	```

### Shootmania.Royal.RoundWinner

* Name: Shootmania.Royal.RoundWinner
* Type: CallbackArray
* Description: Callback sent at the end of the round with the login of the winner.
* Data:
	- Version >=2.0.0:
	```
	[
		"{
			"login": "PlayerLogin" //< Login of the player who won the round
		}"
	]
	```

### Trackmania.Event.Default

* Name: Trackmania.Event.Default
* Type: CallbackArray
* Description: Callback sent when the event type is not yet supported by the XmlRpc library.
* Data:
	- Version >=2.0.0:
	```
	[
		"{
			"time": 123456, //< Server time when the event occured,
			"type": "::EType::EventType" //< The type of event
		}"
	]
	```
	
### Trackmania.Event.OnCommand

* Name: Trackmania.Event.OnCommand
* Type: CallbackArray
* Description: Callback sent when a command is executed on the server.
* Data:
	- Version >=2.0.0:
	```
	[
		"{
			"time": 123456 //< Server time when the event occured,
			"name": "CommandName", //< Name of the command
			"value": { //< The value passed by the command
				"boolean": true,
				"integer": 123,
				"real": 123.456,
				"text": "an example value"
			}
		}"
	]
	```
	
### Trackmania.Event.OnPlayerAdded

* Name: Trackmania.Event.OnPlayerAdded
* Type: CallbackArray
* Description: Callback sent when a player joins the server.
* Data:
	- Version >=2.0.0:
	```
	[
		"{
			"time": 123456 //< Server time when the event occured,
			"login": "PlayerLogin",
			"name": "Name of the player",
			"team": 0,
			"zone": "World|Europe|France|Outre-mer|Reunion",
			"language": "en",
			"ladderrank": 123456,
			"ladderpoints": 789.321
		}"
	]
	```
	
### Trackmania.Event.OnPlayerRemoved

* Name: Trackmania.Event.OnPlayerRemoved
* Type: CallbackArray
* Description: Callback sent when a player leaves the server.
* Data:
	- Version >=2.0.0:
	```
	[
		"{
			"time": 123456 //< Server time when the event occured,
			"login": "PlayerLogin"
		}"
	]
	```
	
### Trackmania.Event.StartLine

* Name: Trackmania.Event.StartLine
* Type: CallbackArray
* Description: Callback sent when a player starts to race (at the end of the 3,2,1,GO! sequence).
* Data:
	- Version >=2.0.0:
	```
	[
		"{
			"time": 123456 //< Server time when the event occured,
			"login": "PlayerLogin"
		}"
	]
	```
	
### Trackmania.Event.WayPoint

* Name: Trackmania.Event.WayPoint
* Type: CallbackArray
* Description: Callback sent when a player crosses a checkpoint.
* Data:
	- Version >=2.0.0:
	```
	[
		"{
			"time": 123456 //< Server time when the event occured,
			"login": "PlayerLogin",
			"racetime": 123456, //< Total race time in milliseconds
			"laptime": 45678, //< Lap time in milliseconds
			"stuntsscore": 3457, //< Stunts score
			"checkpointinrace": 13, //< Number of checkpoints crossed since the beginning of the race
			"checkpointinlap": 4, //< Number of checkpoints crossed since the beginning of the lap
			"isendrace": false, //< Is it the finish line checkpoint
			"isendlap": false, //< Is it the multilap checkpoint
			"curracecheckpoints": [1234, 5200, 7580, 9000], //< Checkpoints times since the beginning of the race
			"curlapcheckpoints": [1420], //< Checkpoints time since the beginning of the lap
			"blockid": "#123", //< Id of the checkpoint block
			"speed": 456.45, //< Speed of the player in km/h
			"distance": 398.49 //< Distance traveled by the player since the beginning of the race
		}"
	]
	```
	
### Trackmania.Event.GiveUp

* Name: Trackmania.Event.GiveUp
* Type: CallbackArray
* Description: Callback sent when a player gives up and restart from the beginning.
* Data:
	- Version >=2.0.0:
	```
	[
		"{
			"time": 123456 //< Server time when the event occured,
			"login": "PlayerLogin"
		}"
	]
	```
	
### Trackmania.Event.Respawn

* Name: Trackmania.Event.Respawn
* Type: CallbackArray
* Description: Callback sent when a player respawns at the previous checkpoint.
* Data:
	- Version >=2.0.0:
	```
	[
		"{
			"time": 123456 //< Server time when the event occured,
			"login": "PlayerLogin",
			"nbrespawns": 5, //< Number of respawns since the beginning of the race
			"racetime": 123456, //< Total race time in milliseconds
			"laptime": 45678, //< Lap time in milliseconds
			"stuntsscore": 3457, //< Stunts score
			"checkpointinrace": 13, //< Number of checkpoints crossed since the beginning of the race
			"checkpointinlap": 4, //< Number of checkpoints crossed since the beginning of the lap
			"speed": 456.45, //< Speed of the player in km/h
			"distance": 398.49 //< Distance traveled by the player since the beginning of the race
		}"
	]
	```
	
### Trackmania.Event.Stunt

* Name: Trackmania.Event.Stunt
* Type: CallbackArray
* Description: Callback sent when a player does a stunt figure.
* Data:
	- Version >=2.0.0:
	```
	[
		"{
			"time": 123456 //< Server time when the event occured,
			"login": "PlayerLogin",
			"racetime": 123456, //< Total race time in milliseconds
			"laptime": 45678, //< Lap time in milliseconds
			"stuntsscore": 3457, //< Stunts score
			"figure": "EStuntFigure::Roll", //< Name of the figure
			"angle": 125, //< Angle of the car
			"points": 18, //< Point awarded by the figure
			"combo": 35, //< Combo counter
			"isstraight": true, //< Is the car straight
			"isreverse": false, //< Is the car reversed
			"ismasterjump": false,
			"factor": 0.5 //< Points multiplier
		}"
	]
	```
	
### Trackmania.Scores

* Name: Trackmania.Scores
* Type: CallbackArray
* Description: Teams and players scores.
* Data:
	- Version >=2.0.0: 
	```
	[
		"{
			"responseid": "xyz", //< Facultative id passed by a script event
			"section": "EndRound", //< Current progress of the match. Can be "" | "EndRound" | "EndMap" | "EndMatch"
			"useteams": true, //< The game mode use teams or not
			"winnerteam": 1, //< The team who won the match, can be -1 (no winner), 0 or 1
			"winnerplayer": "PlayerLogin1", //< Login of the player who won the match
			"teams": [ //< Scores of the teams
				{
					"id": 0,
					"name": "blue",
					"roundpoints": 498, 
					"mappoints": 46,
					"matchpoints": 9,
				},
				{
					"id": 1,
					"name": "red",
					"roundpoints": 365,
					"mappoints": 45,
					"matchpoints": 2,
				}
			],
			"players": [ //< Scores of the players
				{
					"login": "PlayerLogin1",
					"name": "Player#1",
					"rank": 1, //< Rank of the player in the match
					"roundpoints": 456,
					"mappoints": 345,
					"matchpoints": 64,
					"bestracetime": 456789, //< Best race time in milliseconds
					"bestracerespawns": 2, //< Number of respawn during best race
					"bestracecheckpoints": [1230, 7546, 19045, 456789], //< Checkpoints times during best race
					"bestlaptime": 68942, //< Best lap time in milliseconds
					"bestlaprespawns": 1, //< Number of respawn during best lap
					"bestlapcheckpoints": [2458, 9874], //< Checkpoints times during best lap
					"stuntsscore": 492
				},
				{
					"login": "PlayerLogin2",
					"name": "Player#2",
					"rank": 2,
					"roundpoints": 234,
					"mappoints": 123,
					"matchpoints": 32,
					"bestracetime": 49854, //< Best race time in milliseconds
					"bestracerespawns": 5, //< Number of respawn during best race
					"bestracecheckpoints": [3215, 94562, 26845, 49854], //< Checkpoints times during best race
					"bestlaptime": 23254, //< Best lap time in milliseconds
					"bestlaprespawns": 2, //< Number of respawn during best lap
					"bestlapcheckpoints": [4582, 15624], //< Checkpoints times during best lap
					"stuntsscore": 9874
				}
			]
		}"
	]
	```
	
### Trackmania.PointsRepartition

* Name: Trackmania.PointsRepartition
* Type: CallbackArray
* Description: Points repartition in rounds based modes.
* Data:
	- Version >=2.0.0:
	```
	[
		"{
			"responseid": "xyz", //< Facultative id passed by a script event
			"pointsrepartition": [10, 6, 4, 3, 2, 1]	//< The points repartition
		}"
	]
	```
	
### Trackmania.Event.StartCountdown

* Name: Trackmania.Event.StartCountdown
* Type: CallbackArray
* Description: Callback sent when a player see the 3,2,1,Go! countdown.
* Data:
	- Version >=2.0.0:
	```
	[
		"{
			"time": 123456 //< Server time when the event occured,
			"login": "PlayerLogin"
		}"
	]
	```
	
### Trackmania.UI.Properties

* Name: Trackmania.UI.Properties
* Type: CallbackArray
* Description: Information about the default UI components of Maniaplanet (map info, chat, ladder recap, ...).
* Data:
	- Version >=2.0.0: 
	```
	[
		"{
			"responseid": "xyz", //< Facultative id passed by a script event
		}",
		"
		<ui_properties>
			<!-- The map name and author displayed in the top right of the screen when viewing the scores table -->
			<map_info visible="true" pos="75. -85.3 5." />
			<!-- Only visible in solo modes, it hides the medal/ghost selection UI -->
			<opponents_info visible="true" />
			<!--
				The server chat displayed on the bottom right of the screen
				The offset values range from 0. to -3.2 for x and from 0. to 1.8 for y
				The linecount property must be between 0 and 40
			-->
			<chat visible="true" offset="0. 0." linecount="7" />
			<!-- Time of the players at the current checkpoint displayed at the bottom of the screen -->
			<checkpoint_list visible="true" pos="40. -90. 5." />
			<!-- Small scores table displayed at the end of race of the round based modes (Rounds, Cup, ...) on the right of the screen -->
			<round_scores visible="true" pos="104. 14. 5." />
			<!-- Race time left displayed at the bottom right of the screen -->
			<countdown visible="true" pos="154. -57. 5." />
			<!-- 3, 2, 1, Go! message displayed on the middle of the screen when spawning -->
			<go visible="true" />
			<!-- Current race chrono displayed at the bottom center of the screen -->
			<chrono visible="true" pos="0. -80. 5." />
			<!-- Speed and distance raced displayed in the bottom right of the screen -->
			<speed_and_distance visible="true" pos="158. -79.5 5." />
			<!-- Previous and best times displayed at the bottom right of the screen -->
			<personal_best_and_rank visible="true" pos="158. -61. 5." />
			<!-- Current position in the map ranking displayed at the bottom right of the screen -->
			<position visible="true" pos="75. -85.3 5." />
			<!-- Checkpoint time information displayed in the middle of the screen when crossing a checkpoint -->
			<checkpoint_time visible="true" pos="-8. 31.8 -10." />
			<!-- The avatar of the last player speaking in the chat displayed above the chat -->
			<chat_avatar visible="true" />
			<!-- Warm-up progression displayed on the right of the screen during warm-up -->
			<warmup visible="true" pos="170. 27. 0." />
			<!-- Ladder progression box displayed on the top of the screen at the end of the map -->
			<endmap_ladder_recap visible="true" />
			<!-- Laps count displayed on the right of the screen on multilaps map -->
			<multilap_info visible="true" pos="152. 49.5 5." />
			<!-- Player's ranking at the latest checkpoint -->
			<checkpoint_ranking visible="true" pos="75., -85.3, 5." />
			<!-- Scores table displayed in the middle of the screen -->
			<scorestable alt_visible="true" />
		</ui_properties>
		",
		"{
			"map_info": { //< The map name and author displayed in the top right of the screen when viewing the scores table
				"visible": true,
				"pos": { "x": 75.0, "y": -85.3, "z": 5.0 }
			},
			"opponents_info": { //< Only visible in solo modes, it hides the medal/ghost selection UI
				"visible": true
			},
			"chat": { //< The server chat displayed on the bottom right of the screen
				"visible": true,
				"offset": { "x": 0.0, "y": 0.0 }, //< The offset values range from 0. to -3.2 for x and from 0. to 1.8 for y
				"linecount": 7 //< The linecount property must be between 0 and 40
			},
			"checkpoint_list": { //< Time of the players at the current checkpoint displayed at the bottom of the screen
				"visible": true,
				"pos": { "x": 40.0, "y": 90.0, "z": 5.0 }
			},
			"round_scores": { //< Small scores table displayed at the end of race of the round based modes (Rounds, Cup, ...) on the right of the screen
				"visible": true,
				"pos": { "x": 104.0, "y": 14.0, "z": 5.0 }
			},
			"countdown": { //< Race time left displayed at the bottom right of the screen
				"visible": true,
				"pos": { "x": 154.0, "y": -57.0, "z": 5.0 }
			},
			"go": { //< 3, 2, 1, Go! message displayed on the middle of the screen when spawning
				"visible": true
			},
			"chrono": { //< Current race chrono displayed at the bottom center of the screen
				"visible": true,
				"pos": { "x": 0.0, "y": -80.0, "z": 5.0 }
			},
			"speed_and_distance": { //< Speed and distance raced displayed in the bottom right of the screen
				"visible": true,
				"pos": { "x": 158.0, "y": -79.5, "z": 5.0 }
			},
			"personal_best_and_rank": { //< Previous and best times displayed at the bottom right of the screen
				"visible": true,
				"pos": { "x": 158.0, "y": -61.0, "z": 5.0 }
			},
			"position": { //< Current position in the map ranking displayed at the bottom right of the screen
				"visible": true,
				"pos": { "x": 75.0, "y": -85.3, "z": 5.0 }
			},
			"checkpoint_time": { //< Checkpoint time information displayed in the middle of the screen when crossing a checkpoint
				"visible": true,
				"pos": { "x": -8.0, "y": 31.8, "z": -10.0 }
			},
			"chat_avatar": { //< The avatar of the last player speaking in the chat displayed above the chat
				"visible": true
			},
			"warmup": { //< Warm-up progression displayed on the right of the screen during warm-up
				"visible": true,
				"pos": { "x": 170.0, "y": 27.0, "z": 0.0 }
			},
			"endmap_ladder_recap": { //< Ladder progression box displayed on the top of the screen at the end of the map
				"visible": true
			},
			"multilap_info": { //< Laps count displayed on the right of the screen on multilaps map
				"visible": true,
				"pos": { "x": 152.0, "y": 49.5, "z": 5.0 }
			},
			"checkpoint_ranking": { //< Player's ranking at the latest checkpoint
				"visible": true,
				"pos": { "x": 75.0, "y": -85.3, "z": 5.0 }
			},
			"scorestable": { //< Scores table displayed in the middle of the screen
				"alt_visible": true
			}
		}"
	]
	```
	
### Trackmania.WarmUp.Start

* Name: Trackmania.WarmUp.Start
* Type: CallbackArray
* Description: Callback sent when the warm up sequence start.
* Data:
	- Version >=2.0.0:
	```
	[
		"{}"
	]
	```
	
### Trackmania.WarmUp.StartRound

* Name: Trackmania.WarmUp.StartRound
* Type: CallbackArray
* Description: Callback sent when a warm up round start.
* Data:
	- Version >=2.0.0:
	```
	[
		"{
			"current": 2,	//< The number of the current round
			"total": 3 //< The total number of warm up rounds
		}"
	]
	```
	
### Trackmania.WarmUp.EndRound

* Name: Trackmania.WarmUp.EndRound
* Type: CallbackArray
* Description: Callback sent when a warm up round end.
* Data:
	- Version >=2.0.0:
	```
	[
		"{
			"current": 2,	//< The number of the current round
			"total": 3 //< The total number of warm up rounds
		}"
	]
	```
	
### Trackmania.WarmUp.End

* Name: Trackmania.WarmUp.End
* Type: CallbackArray
* Description: Callback sent when the warm up sequence end.
* Data:
	- Version >=2.0.0:
	```
	[
		"{}"
	]
	```
	
### Trackmania.WarmUp.Status

* Name: Trackmania.WarmUp.Status
* Type: CallbackArray
* Description: The status of Trackmania's the warmup.
* Data:
  - Version >=2.0.0:
  ```
  [
    "{
      "responseid": "xyz", //< Facultative id passed by a script event
      "available": true, //< true if a warmup is available in the game mode, false otherwise
      "active": true //< true if a warmup is ongoing, false otherwise
    }"
  ]
  ```

Methods
-------

### XmlRpc.EnableCallbacks

* Name: XmlRpc.EnableCallbacks
* Type: TriggerModeScriptEventArray
* Description: Enable or disable script callbacks.
* Data:
	- Version >=2.0.0:
	```
	[
		"true" //< "true" to enable callbacks, "false" to disable them.
	]
	```

### XmlRpc.GetCallbacksList

* Name: XmlRpc.GetCallbacksList
* Type: TriggerModeScriptEventArray
* Description: Request a list of all available callbacks. This method will trigger the "XmlRpc.CallbacksList" callback.
* Data:
	- Version >=2.0.0:
	```
	[
		"responseid" //< Facultative id that will be passed to the "XmlRpc.CallbacksList" callback.
	]
	```

### XmlRpc.GetCallbacksList_Enabled

* Name: XmlRpc.GetCallbacksList_Enabled
* Type: TriggerModeScriptEventArray
* Description: Request a list of all enabled callbacks. This method will trigger the "XmlRpc.CallbacksList_Enabled" callback.
* Data:
	- Version >=2.0.0:
	```
	[
		"responseid" //< Facultative id that will be passed to the "XmlRpc.CallbacksList_Enabled" callback.
	]
	```

### XmlRpc.GetCallbacksList_Disabled

* Name: XmlRpc.GetCallbacksList_Disabled
* Type: TriggerModeScriptEventArray
* Description: Request a list of all disabled callbacks. This method will trigger the "XmlRpc.CallbacksList_Disabled" callback.
* Data:
	- Version >=2.0.0:
	```
	[
		"responseid" //< Facultative id that will be passed to the "XmlRpc.CallbacksList_Disabled" callback.
	]
	```

### XmlRpc.BlockCallbacks

* Name: XmlRpc.BlockCallbacks
* Type: TriggerModeScriptEventArray
* Description: Block a callback and prevent it from being sent by the script.
* Data:
	- Version >=2.0.0:
	```
	[
		"CallbackName",  //< The name of the callback to block
		"CallbackNameN" //< You can pass as many callbacks as you want
	]
	```

### XmlRpc.UnblockCallbacks

* Name: XmlRpc.UnblockCallbacks
* Type: TriggerModeScriptEventArray
* Description: Unblock a blocked callback.
* Data:
	- Version >=2.0.0:
	```
	[
		"CallbackName", //< The name of the callback to unblock
		"CallbackNameN" //< You can pass as many callbacks as you want
	]
	```

### XmlRpc.GetCallbackHelp

* Name: XmlRpc.GetCallbackHelp
* Type: TriggerModeScriptEventArray
* Description: Request help about a callback. This method will trigger the "XmlRpc.CallbackHelp" callback.
* Data:
	- Version >=2.0.0:
	```
	[
		"callbackname", //< Name of the callback to get help for
		"responseid" //< Facultative id that will be passed to the "XmlRpc.CallbackHelp" callback.
	]
	```

### XmlRpc.GetMethodsList

* Name: XmlRpc.GetMethodsList
* Type: TriggerModeScriptEventArray
* Description: Request a list of all available methods. This method will trigger the "XmlRpc.MethodsList" callback.
* Data:
	- Version >=2.0.0:
	```
	[
		"responseid" //< Facultative id that will be passed to the "XmlRpc.MethodsList" callback.
	]
	```

### XmlRpc.GetMethodHelp

* Name: XmlRpc.GetMethodHelp
* Type: TriggerModeScriptEventArray
* Description: Request help about a method. This method will trigger the "XmlRpc.MethodHelp" callback.
* Data:
	- Version >=2.0.0:
	```
	[
		"callbackname", //< Name of the method to get help for
		"responseid" //< Facultative id that will be passed to the "XmlRpc.MethodHelp" callback.
	]
	```

### XmlRpc.GetDocumentation

* Name: XmlRpc.GetDocumentation
* Type: TriggerModeScriptEventArray
* Description: Request the current game mode xmlrpc callbacks and methods documentation. This method will trigger the "XmlRpc.Documentation" callback.
* Data:
	- Version >=2.0.0:
	```
	[
		"responseid" //< Facultative id that will be passed to the "XmlRpc.Documentation" callback.
	]
	```

### XmlRpc.SetApiVersion

* Name: XmlRpc.SetApiVersion
* Type: TriggerModeScriptEventArray
* Description: Select the version of the API to use.
* Data:
	- Version >=2.0.0:
	```
	[
		"1.2.3-beta.4.5.6+build789" //< The version to use in semver format
	]
	```

### XmlRpc.GetApiVersion

* Name: XmlRpc.GetApiVersion
* Type: TriggerModeScriptEventArray
* Description: Request the version of the API currently in use. This method will trigger the "XmlRpc.ApiVersion" callback.
* Data:
	- Version >=2.0.0:
	```
	[
		"responseid" //< Facultative id that will be passed to the "XmlRpc.ApiVersion" callback.
	]
	```

### XmlRpc.GetAllApiVersions

* Name: XmlRpc.GetAllApiVersions
* Type: TriggerModeScriptEventArray
* Description: Request all available versions of the API. This method will trigger the "XmlRpc.AllApiVersions" callback.
* Data:
	- Version >=2.0.0:
	```
	[
		"responseid" //< Facultative id that will be passed to the "XmlRpc.AllApiVersions" callback.
	]
	```

### Maniaplanet.Mode.GetUseTeams

* Name: Maniaplanet.Mode.GetUseTeams
* Type: TriggerModeScriptEventArray
* Description: Check if the game mode uses teams or not.
* Data:
	- Version >=2.0.0:
	```
	[
		"responseid" //< Facultative id that will be passed to the "Maniaplanet.Mode.UseTeams" callback.
	]
	```

### Maniaplanet.UI.SetAltScoresTableVisibility

* Name: Maniaplanet.UI.SetAltScoresTableVisibility
* Type: TriggerModeScriptEventArray
* Description: Enable or disable the scores table display with the alt key.
* Data:
	- Version >=2.0.0:
	```
	[
		"PlayerLogin", //< The login of the player to update
		"false" //< false to disable, true to enable
	]
	```

### Maniaplanet.WarmUp.GetStatus

* Name: Maniaplanet.WarmUp.GetStatus
* Type: TriggerModeScriptEventArray
* Description: Get the status of the warmup.
* Data:
	- Version >=2.0.0:
	```
	[
		"responseid" //< Facultative id that will be passed to the "Maniaplanet.WarmUp.Status" callback.
	]
	```

### Maniaplanet.Pause.GetStatus

* Name: Maniaplanet.Pause.GetStatus
* Type: TriggerModeScriptEventArray
* Description: Get the status of the pause.
* Data:
	- Version >=2.0.0:
	```
	[
		"responseid" //< Facultative id that will be passed to the "Maniaplanet.Pause.Status" callback.
	]
	```

### Maniaplanet.Pause.SetActive

* Name: Maniaplanet.Pause.SetActive
* Type: TriggerModeScriptEventArray
* Description: Enable or disable the pause if it is available.
* Data:
	- Version >=2.0.0:
	```
	[
		"true", //< true to enable the pause, false to disable it.
		"responseid" //< Facultative id that will be passed to the "Maniaplanet.Pause.Status" callback.
	]
	```

### Shootmania.GetScores

* Name: Shootmania.GetScores
* Type: TriggerModeScriptEventArray
* Description: Request the current scores. This method will trigger the "Shootmania.Scores" callback.
* Data:
	- Version >=2.0.0: 
	```
	[
		"responseid" //< Facultative id that will be passed to the "Shootmania.Scores" callback.
	]
	```
	
### Shootmania.UI.GetProperties

* Name: Shootmania.UI.GetProperties
* Type: TriggerModeScriptEventArray
* Description: Request the current ui properties. This method will trigger the "Shootmania.UI.Properties" callback.
* Data:
	- Version >=2.0.0:
	```
	[
		"responseid" //< Facultative id that will be passed to the "Shootmania.UI.Properties" callback.
	]
	```
	
### Shootmania.UI.SetProperties

* Name: Shootmania.UI.SetProperties
* Type: TriggerModeScriptEventArray
* Description: Update the ui properties.
* Data:
	- Version >=2.0.0:
	```
	[
		"
		<!--
		  Each node is optional and can be omitted.
		  If it's the case then the previous value will be kept.
		-->
		<ui_properties>
		  <!-- Notifications displayed on the left of the screen -->
		  <notices visible="true" />
		  <!-- The map name and author displayed on the top right of the screen when viewing the scores table -->
		  <map_info visible="true" />
		  <!--
		    The server chat displayed on the bottom right of the screen
		    The offset values range from 0. to -3.2 for x and from 0. to 1.8 for y
		    The linecount property must be between 0 and 40
		  -->
		  <chat visible="true" offset="0. 0." linecount="5" />
		  <!-- Countdown displayed on the top of the screen -->
		  <countdown visible="true" pos="0. 85." />
		  <!-- Crosshair displayed on the center of the screen -->
		  <crosshair visible="true" />
		  <!-- Gauges displayed on the bottom of the screen -->
		  <gauges visible="true" />
		  <!-- Consumables displayed on the bottom of the screen -->
		  <consumables visible="true" />
		  <!-- 3, 2, 1, Go! message displayed on the middle of the screen when spawning -->
		  <go visible="true" />
		  <!-- The avatar of the last player speaking in the chat displayed above the chat -->
		  <chat_avatar visible="true" />
		  <!-- Ladder progression box displayed on the top of the screen at the end of the map -->
		  <endmap_ladder_recap visible="true" />
		  <!-- Scores table displayed in the middle of the screen -->
			<scorestable alt_visible="true" />
		</ui_properties>
		"
	]
	```
	
### Maniaplanet.WarmUp.Extend

* Name: Maniaplanet.WarmUp.Extend
* Type: TriggerModeScriptEventArray
* Description: Extend the duration of any ongoing warmup.
* Data:
	- Version >=2.0.0:
	```
	[
		"60000" //< the duration of the extension in milliseconds.
	]
	```

### Maniaplanet.WarmUp.ForceStop

* Name: Maniaplanet.WarmUp.ForceStop
* Type: TriggerModeScriptEventArray
* Description: Stop any ongoing warmup.
* Data:
	- Version >=2.0.0:
	```
	[]
	```

### Maniaplanet.WarmUp.BlockEndWarmUp

* Name: Maniaplanet.WarmUp.BlockEndWarmUp
* Type: TriggerModeScriptEventArray
* Description: Disable the countdown when all teams' slots are filled and force all players to be ready before ending the warmup.
* Data:
	- Version >=2.0.0:
	```
	[
		"true", //< true to block the warmup countdown, false to unblock.
		"5000" //< Timer before the end of the warmup when all players are ready. Use a negative value to prevent the warmup from ending even if all players are ready.
	]
	```

### Shootmania.Combo.SetTimersPosition

* Name: Shootmania.Combo.SetTimersPosition
* Type: TriggerModeScriptEventArray
* Description: Move the spectators' timers UI.
* Data:
	- Version >=2.0.0:
	```
	[
		"10.", //< X position
		"50.5", //< Y position
		"0." //< Z position
	]
	```

### Maniaplanet.WarmUp.Stop

* Name: Maniaplanet.WarmUp.Stop
* Type: TriggerModeScriptEventArray
* Description: Stop any ongoing warmup.
* Data:
	- Version >=2.0.0:
	```
	[]
	```

### Shootmania.Siege.SetProgressionUIPosition

* Name: Shootmania.Siege.SetProgressionUIPosition
* Type: TriggerModeScriptEventArray
* Description: Move the progression UI.
* Data:
	- Version >=2.0.0:
	```
	[
		"10.", //< X position
		"50.5", //< Y position
		"0." //< Z position
	]
	```

### Trackmania.GetScores

* Name: Trackmania.GetScores
* Type: TriggerModeScriptEventArray
* Description: Request the current scores. This method will trigger the "Trackmania.Scores" callback.
* Data:
	- Version >=2.0.0: 
	```
	[
		"responseid" //< Facultative id that will be passed to the "Trackmania.Scores" callback.
	]
	```
	
### Trackmania.GetPointsRepartition

* Name: Trackmania.GetPointsRepartition
* Type: TriggerModeScriptEventArray
* Description: Request the current points repartition. This method will trigger the "Trackmania.PointsRepartition" callback.
* Data:
	- Version >=2.0.0:
	```
	[
		"responseid" //< Facultative id that will be passed to the "Trackmania.PointsRepartition" callback.
	]
	```
	
### Trackmania.SetPointsRepartition

* Name: Trackmania.SetPointsRepartition
* Type: TriggerModeScriptEventArray
* Description: Update the points repartition.
* Data:
	- Version >=2.0.0:
	```
	[
		"10", "9", "8", "7", "6", "5" //< An array of points
	]
	```
	
### Trackmania.UI.GetProperties

* Name: Trackmania.UI.GetProperties
* Type: TriggerModeScriptEventArray
* Description: Request the current ui properties. This method will trigger the "Trackmania.UI.Properties" callback.
* Data:
	- Version >=2.0.0:
	```
	[
		"responseid" //< Facultative id that will be passed to the "Trackmania.UI.Properties" callback.
	]
	```
	
### Trackmania.UI.SetProperties

* Name: Trackmania.UI.SetProperties
* Type: TriggerModeScriptEventArray
* Description: Update the ui properties.
* Data:
	- Version >=2.0.0:
	```
	[
		"
		<!--
		  Each node is optional and can be omitted.
		  If it's the case then the previous value will be kept.
		-->
		<ui_properties>
			<!-- The map name and author displayed in the top right of the screen when viewing the scores table -->
			<map_info visible="true" pos="75. -85.3 5." />
			<!-- Only visible in solo modes, it hides the medal/ghost selection UI -->
			<opponents_info visible="true" />
			<!--
				The server chat displayed on the bottom right of the screen
				The offset values range from 0. to -3.2 for x and from 0. to 1.8 for y
				The linecount property must be between 0 and 40
			-->
			<chat visible="true" offset="0. 0." linecount="7" />
			<!-- Time of the players at the current checkpoint displayed at the bottom of the screen -->
			<checkpoint_list visible="true" pos="40. -90. 5." />
			<!-- Small scores table displayed at the end of race of the round based modes (Rounds, Cup, ...) on the right of the screen -->
			<round_scores visible="true" pos="104. 14. 5." />
			<!-- Race time left displayed at the bottom right of the screen -->
			<countdown visible="true" pos="154. -57. 5." />
			<!-- 3, 2, 1, Go! message displayed on the middle of the screen when spawning -->
			<go visible="true" />
			<!-- Current race chrono displayed at the bottom center of the screen -->
			<chrono visible="true" pos="0. -80. 5." />
			<!-- Speed and distance raced displayed in the bottom right of the screen -->
			<speed_and_distance visible="true" pos="158. -79.5 5." />
			<!-- Previous and best times displayed at the bottom right of the screen -->
			<personal_best_and_rank visible="true" pos="158. -61. 5." />
			<!-- Current position in the map ranking displayed at the bottom right of the screen -->
			<position visible="true" pos="75. -85.3 5." />
			<!-- Checkpoint time information displayed in the middle of the screen when crossing a checkpoint -->
			<checkpoint_time visible="true" pos="-8. 31.8 -10." />
			<!-- The avatar of the last player speaking in the chat displayed above the chat -->
			<chat_avatar visible="true" />
			<!-- Warm-up progression displayed on the right of the screen during warm-up -->
			<warmup visible="true" pos="170. 27. 0." />
			<!-- Ladder progression box displayed on the top of the screen at the end of the map -->
			<endmap_ladder_recap visible="true" />
			<!-- Laps count displayed on the right of the screen on multilaps map -->
			<multilap_info visible="true" pos="152. 49.5 5." />
			<!-- Player's ranking at the latest checkpoint -->
			<checkpoint_ranking visible="true" pos="75., -85.3, 5." />
			<!-- Scores table displayed in the middle of the screen -->
			<scorestable alt_visible="true" />
		</ui_properties>
		"
	]
	```
	
### Trackmania.WarmUp.ForceStop

* Name: Trackmania.WarmUp.ForceStop
* Type: TriggerModeScriptEventArray
* Description: Stop the whole warm up sequence.
* Data:
	- Version >=2.0.0:
	```
	[]
	```
	
### Trackmania.WarmUp.ForceStopRound

* Name: Trackmania.WarmUp.ForceStopRound
* Type: TriggerModeScriptEventArray
* Description: Stop the current warm up round.
* Data:
	- Version >=2.0.0:
	```
	[]
	```
	
### Trackmania.WarmUp.GetStatus

* Name: Trackmania.WarmUp.GetStatus
* Type: TriggerModeScriptEventArray
* Description: Get the status of the trackmania's warmup.
* Data:
  - Version >=2.0.0:
  ```
  [
    "responseid" //< Facultative id that will be passed to the "Trackmania.WarmUp.Status" callback.
  ]
  ```

### Trackmania.Chase.ForceStopRound

* Name: Trackmania.Chase.ForceStopRound
* Type: TriggerModeScriptEventArray
* Description: Force the end of the current round.
* Data:
	- Version >=2.0.0:
	```[]```

### Trackmania.ForceEndRound

* Name: Trackmania.ForceEndRound
* Type: TriggerModeScriptEventArray
* Description: Stop the current round. Only available in Cup, Rounds and Team modes.
* Data:
	- Version >=2.0.0:
	```
	[]
	```
	
