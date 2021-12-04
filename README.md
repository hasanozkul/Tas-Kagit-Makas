# Tas-Kagit-Makas as a NEAR contract

Video demo: [here](https://drive.google.com/file/d/1L0licLk5sSTQ21iwIp3QHHPRhX8hhfC3/view)

Figma wireframes: [here](https://www.figma.com/file/reMNlA1lKaM1hFthWbwvrP/Untitled?node-id=3%3A117)

## Install dependencies
```
yarn
```

## Build and Deploy the contract
```
npx asb
near dev-deploy ./out/main.wasm
# save the contract id in your clipboard and send it to player 2
```

## How to Play

1. Player one call function `createGame` and send gameId to player 2
2. Player two call function `joinGame(gameId)` passing gameId that player one sent
3. Player one is the first to play, calling function `play(gameId, selectedItem)` with gameId, selectedItem as argument
4. Player two continues the game
5. The plays continue until someone win

## Run the game
**Create a game**
```
near call <contract-id> createGame --account_id <account-id> 
# save the game id in your clipboard and send it to your friend
```

**Join a game (player 2)**
```
near call <contract-id> joinGame '{"gameId": <game-id>}' --account_id <account-id> 
```

**Play the game**
```
near call <contract-id> play '{"gameId": <game-id>, "selectedItem": "Tas"}' --account_id <account-id>
```


