Installation
```bash
go get -u github.com/anboo/rate-limiter
```

Usage
```go
package main

import (
	"context"
	"time"

	rate_limiter "github.com/anboo/rate-limiter"
)

func main() {
	ctx := context.Background()
	
	rateLimiter := rate_limiter.NewRealtimeRateLimiter(100, time.Second*60)
	
	for j := 0; j < 100; j++ {
		rateLimiter.Wait(ctx)
	}
}
```