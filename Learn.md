# Enum

Solidity supports enumerables and they are useful to model choice and keep track of state.

Enums can be declared outside of a contract.

Enums bounds a variable to have one of only a few predefined values.  
This reduces the number of bugs in your code.

Let's create an Enum representing shipping status.
It will have only five statuses.

```
    enum Status {
        Pending,
        Shipped,
        Accepted,
        Rejected,
        Canceled
    }
```

Create a public variable called `status` having `Status` as type.

```
Status public status;
```

- The default value is the first value in the enum definition. In this case `Pending`.

## Getting the value of an enum

Let's write a function that returns the value of the enum.
This function returns a uint corresponding to the enum value.

- Pending - 0
- Shipped - 1
- Accepted - 2
- Rejected - 3
- Canceled - 4

```
    function get() public view returns (Status) {
        return status;
    }
```

Hit `Run`. You should see the returned value 0 because the default value is `Pending`.

## Setting the value of an enum

Now let's write a function that sets the value of the enum.

```
    function set(Status _status) public {
        status = _status;
    }
```

Hit `Run`. After `set(3)` is called, the value of `status` should be `Rejected`. But we should see the returned value `3`.

## Update to a specific enum value

Let's write a function to update the value of the enum to `Canceled`.

```
    function cancel() public {
        status = Status.Canceled;
    }
```

Hit `Run`. After `cancel()` is called, the value of `status` should be `Canceled`. But we should see the returned value `4`.

## Resetting the value of an enum

Let's write a function to reset the value of the enum to default value.

- `delete` resets the value to the first value in the enum definition. In this case `Pending`.

```
    function reset() public {
        delete status;
    }
```

Hit `Run`. After `reset()` is called, the value of `status` should be `Pending`. But we should see the returned value `0`.
