# JIMM API

JIMM (Juju Intelligent Model Manager) API provides a client interface for interacting with the JIMM service. JIMM enables management of multiple Juju models across different controllers.

## Features

- Add and remove controllers
- Manage clouds associated with controllers
- Query and manipulate model status
- Handle audit logs and events
- Manage user groups and access control
- Perform cross-model queries
- Migrate models between controllers
- Manage service accounts and credentials

## Installation

To use the JIMM API in your Go project, run:

```bash
go get github.com/canonical/jimmapi
```

## Usage

Here's a quick example of how to create a JIMM API client and use it:

```go
import (
    "github.com/canonical/jimmapi"
    "github.com/canonical/jimmapi/params"
)

// Create a new JIMM API client
client := jimmapi.NewClient(yourAPICaller)

// Add a new controller
req := &params.RemoveControllerRequest{
    Name:  "example-controller",
    Force: false,
}

info, err := client.RemoveController(req)
if err != nil {
    // Handle error
}

// Use the controller info
fmt.Printf("Removed controller: %s", info.Name)
```

## Documentation

For detailed documentation on available methods and their parameters, please refer to [pkg.go.dev](https://pkg.go.dev/github.com/canonical/jimmapi)
