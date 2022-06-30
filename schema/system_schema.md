Define the default receiver to handle the case where no receiver is defined for a message. This ECU doesn't need JSON definitions and can be used to default to debug/logging purposes.
```json
{
    "default_receiver": "DEBUG"
}
```

Optional - define the bus speed in kbits/s.
```json
{
    "bus_speed": 500
}
```

Optional - define the default endianness to be `"little"` or `"big"`. This is `"little"` by default.
```json
{
    "default_endianness": "little"
}
```

Optional - define the attribute ranges and default values:
```json
{
    "cycle_time_min": 0,
    "cycle_time_max": 65535,
    "cycle_time_default": 0,
    "sig_start_val_min": 0,
    "sig_start_val_max": 2147483647,
    "sig_start_val_default": 0
}
```

