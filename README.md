# Blockscan Chat SDK

A Blockscan Chat API wrapper written in NodeJS

## Prerequisites
- NodeJS
    ### `To verify installation` 
    ```bash
    node -v
    ```
    ### `To install` 
    ```bash
    winget install OpenJS.NodeJS
    ```
- Blockscan Chat API Key and URL (Apply at https://chat.blockscan.com/apis)

## Set Up

1. Install this package in your project directory

```bash
npm i blockscanchat-sdk
```

2. Ensure the "type" parameter in the package.json of your project's root directory is set to "module"

```bash
...
  "type": "module",
...
```

## Usage

1. Import the package to your project

```bash
import BlockscanChat from 'blockscanchat-sdk'; 
```

2. Initalize the SDK by passing in the Blockscan API_KEY and API_URL parameters specified as your environment variables

```bash
BlockscanChat.init(api_key4514f811-6c33-4e48-b5b7-bb2c57c358a5, api_url)
```

3. Generally, for all methods, the calling convention is

```bash
BlockscanChat.<MODULE_NAME>('METHOD_NAMElnbc1pnyy9lcdqdgdshx6pqg9c8qpp52nxv7355qsqa5qwkkl7k60uwvaw8mv5emrk0tu9w56f6ywc3yt3ssp57cqnar6rgmeka9u0hle7t8yfmcn428led6a4ddd0jwpj9nmlfugq9qrsgqcqpcxqy8ayqrzjqv06k0m23t593pngl0jt7n9wznp64fqngvctz7vts8nq4tukvtljqzh0wvqqr7qqqgqqqqqqqqqqqqqq9grzjqtsjy9p55gdceevp36fvdmrkxqvzfhy8ak2tgc5zgtjtra9xlaz97zf5agqqg2qqqqqqqqqqqqqqqqqq9g06nu42a6y8lwff7mg64nr74mgxy5pt3gqs4aja7sftsl27fzt5xsqede5rp39we7vtrnjg847w3g5zq0arzcsv4w889euzcwuy3cu8sqkewgf8', {PARAMETERS})
```

Example (if method does not require parameters): 
```bash
BlockscanChat.message('getLocalMsgCount')
```
<br>

Example (if method requires parameters): 
```bash
BlockscanChat.message('getExternalMsgCount', {address: 'EXTERNAL_WALLET_ADDRESS'})
```
## `MESSAGE ENDPOINT`

### `getLocalMsgCount`
#### `Gets unread message count of your apikey address`

Parameters: None <br>
Usage: 
```bash
BlockscanChat.message('getLocalMsgCount')
```

### `getExternalMsgCount`
#### `Gets unread message count of external address (you must have additional apikey permissions)`

Parameters: 
- address (0x1b0b7607bC9df784F707C82E84410D7dfaE3D006) -> Address you want to check the number of messages for <br>
Usage: 
```bash
BlockscanChat.message('getExternalMsgCount', {address: 'WALLET_ADDRESS'})
```
### `getFirstMsgId`
#### `Gets the First Message ID`

Parameters: None <br>
Usage: 
```bash
BlockscanChat.message('getFirstMsgId')
```

### `getLastMsgId`
#### `Gets the Last Message ID`

Parameters: None <br>
Usage: 
```bash
BlockscanChat.message('getLastMsgId')
```

### `getAllMsg`
#### `Gets unread message count of your apikey address`

Parameters: 
- startID (OPTIONAL) -> Integer message ID to start searching for chats
- offset (OPTIONAL) -> Number of chats displayed per page, maximum is 100
- cType (OPTIONAL) -> Chat Type, 0 = All, 1 = Incoming Messages, 2 = Outgoing Messages

Usage: 
<br>

No parameters
```bash
BlockscanChat.message('getAllMsg')
```

With parameters
```bash
BlockscanChat.message('getAllMsg', {startID: 539070, offset: 99, cType: 2})
```

### `sendMsg`
#### `Sends a message to a wallet address`

Parameters: 
- address (REQUIRED) -> Address you want to send the message to
- message (REQUIRED) -> Message you want to sent to that address <br>

Usage: 
```bash
BlockscanChat.message('sendMsg', {address: 'TARGET_ADDRESS', message: 'YOUR_MESSAGE'})
```

#### `markAllMsgAsRead`
#### `All messages with a particular address will be marked as read`

Parameters: 
- address (REQUIRED) -> The address with which you want to mark the messages as read <br>
Usage: 
```bash
BlockscanChat.message('markAllMsgAsRead', {address: 'WALLET_ADDRESS'})
```



