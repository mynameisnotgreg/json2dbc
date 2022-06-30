## Overview

Signal size can be automatically calculated or explicitly specified. Cannot (currently) specify signal position.

## Default TX message definition fields
```json
{
    "message_name": {
        "signals": {
            "signal_name": {
                "resolution": 1,
                "signed": false,
                "min": 0
            }
        }
    }
}
```

## Absolute minimum message definitions
Given the default fields there are two options of absolute minimum TX message definitions:
```json
{
    "message_name": {
        "message_id": 123,
        "signals": {
            "signal_name_1": {
                "bits": 14
            },
            "signal_name_2": {
                "max": 100
            }
        }
    }
}
```

## Associate an enum definition with a signal
Note that the required signal size/sign is automatically determined, even if the enum is negative. It's illegal to override this by defining `min`, `max` and/or `signed`.

Note that this is legal:
```json
{
    "message_name": {
        "signals": {
            "signal_name_1": {
                "enum": "example_enum_1"
            }
        }
    }
}
```

Whereas this is illegal:
```json
{
    "message_name": {
        "signals": {
            "signal_name_2": {
                "enum": "example_enum_2",
                "min": -3,
                "max": 3,
                "signed": true
            }
        }
    }
}
```

## Signal size

Can define (`min` and `max`) OR (`bits`), but not both. Note that this is legal:
```json
{
    "message_name": {
        "signals": {
            "signal_name_1": {
                "min": 0,
                "max": 10
            },
            "signal_name_2": {
                "bits": 4
            }
        }
    }
}
```

Whereas this is illegal:
```json
{
    "message_name": {
        "signals": {
            "signal_name_3": {
                "min": 0,
                "max": 10,
                "bits": 4
            }
        }
    }
}
```

## Other

Generate `GenSigStartValue` and `GenMsgCycleTime` attributes for a message:
```json
{
    "message_name": {
        "sig_start_val": 99,
        "cycle_time": 10,
    }
}
```

Define units for a signal:
```json
{
    "message_name": {
        "signals": {
            "signal_name": {
                "units": "kW"
            }
        }
    }
}
```

Override default endianness - example where default endianness is `"little"`:
```json
{
    "message_name": {
        "signals": {
            "signal_name": {
                "endianness": "big"
            }
        }
    }
}
```
