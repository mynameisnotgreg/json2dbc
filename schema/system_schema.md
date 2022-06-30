Define the default receiver to handle the case where no receiver is defined for a message. This ECU doesn't need JSON definitions and can be used to default to debug/logging purposes.

```json
{
    "default_receiver": "DEBUG"
}
```

Define the default endianness to be `"little"` or `"big"`. This is `"little"` by default.
```json
{
    "default_endianness": "little"
}
```
