You can send items through the CodeUtilities Item API. To connect, open a socket on port `31372`. You will send/receive data from this port.

You can also use **websockets**, which can be accessed at at `ws://localhost:31371/codeutilities/item`

**Sending**
To send items, you need to send a json object to the port. **There must be no newlines, as that is supposed to mark the end of your message. (So make sure to put a newline at the end)**

**Parameters**

- `type` - The type of the item you want. Valid types are `nbt`, `template` & `raw_template`.
- `data` - A **string** containing the data the item will use. Even though certain code items may json objects, please note that they need to be strings!
- `source` - A **string** representing the name of your application. This is shown in the message that appears when the player receives an item.

**Item Types**
There are 3 current item types that you can send through the CodeUtilities Item API.
**`nbt`**
```
{id:"minecraft:stone",Count:1b}
```
The NBT type accepts minecraft NBT to construct an item

**`template`**
This JSON Object has the following values
- `data` The encoded data for the code template.
- `author` The name of the template author, this is optional and if not provided will default to the player's ingame name.
- `name` The name of the template, this is set in the NBT and as the items name. If none is provided it becomes "Imported Code Template"
- `version` This is the version id, which is highly recommended you set yourself. If you leave this blank it will default to the id provided in CodeUtilities.
  **`raw_template`**
  This is the same as `template` but with one major difference.
- `data` The raw json  data for the code template. (Not encoded)

**Results**
CodeUtilities also sends success/error messages when an action is run. The format for these is very temporary and is rather basic.

If an error occurs the following will be sent -> `{"status":"error", "error":"error_desc"}` (These are not user friendly messages!)

If it succeeds the following is sent -> `{"status":"success"}` (No message is sent)

**Receiving**
CodeUtilities allows you to also receive NBT data. This is currently only sent via the `/sendtemplate` command.
As long as you are still connected to the server you will be sent the following json object.

- `received` Contains the data received
- `type` The type of data received (currently this is only template)

**Receive Types**
- `template` - The `received` property will contain the raw `hypercube:codetemplatedata` tag from an item.

**Example**
```
{"type":"template","source":"DFVisual","data":"{\"name\":\"DFVisual Template\",\"data\":\"H4sIAAAAAAAAAKtWSsrJT84uVrKKroYwlayUUvNKMksq4xOTSzLz85R0lDJTgIIQSR2lxKJ0oOpqpcyS1FyQtthaoBhEpZWSUm1sLQCIvxHHUwAAAA==\"}"}
```
-> `{"success":""}`
