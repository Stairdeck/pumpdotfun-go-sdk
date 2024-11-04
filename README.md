# Pump.fun Go SDK

A SDK allowing you to create, buy and sell pump.fun tokens in Golang.

## Usage

```go
package main

import (
    "os"

    solana "github.com/gagliardetto/solana-go"
    pumpdotfun "github.com/prdsrm/pumpdotfun-go-sdk"
)

func main() {
	privateKey, err := solana.PrivateKeyFromBase58(os.Getenv("PRIVATE_KEY"))
	if err != nil {
		return nil, fmt.Errorf("private key is invalid: %w", err)
	}
	mint := solana.NewWallet()
	err = pumpdotfunsdk.CreateToken(
		c.RpcClient,
		c.WsClient,
		privateKey,
		mint,
		"TEST",
		"TEST",
		"https://example.com",
		req.BuyAmountSol,
		req.Percentage.Or(0.98),
	)
	if err != nil {
		return nil, fmt.Errorf("can't create token: %w", err)
	}
}
```

Copy this into a file and run `go mod tidy` to automatically add the dependency.