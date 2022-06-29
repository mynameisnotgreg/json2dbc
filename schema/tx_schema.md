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
- Note that the required signal size is automatically determined so it's illegal to define `min` and/or `max`.
```json
{
    "message_name": {
        ...
        "signals": {
            "signal_name_1": { // LEGAL
                ...
                "enum": "example_enum_1"
            },
            "signal_name_2": { // ILLEGAL
                ...
                "enum": "example_enum_2",
                "min": 0,
                "max": 3
            }
        }
    }
}
```

## Other

Can define (`min` and `max`) OR (`bits`), but not both:
```json
{
    "message_name": {
        ...
        "signals": {
            "signal_name_1": { // LEGAL
                ...
                "min": 0,
                "max": 1
            },
            "signal_name_2": { // LEGAL
                ...
                "bits": 1
            },
            "signal_name_3": { // ILLEGAL
                ...
                "min": 0,
                "max": 1,
                "bits": 1
            }
        }
    }
}
```

Generate `GenSigStartValue` and `GenMsgCycleTime` attributes for a message:
```json
{
    "message_name": {
        "sig_start_val": 99,
        "cycle_time": 10,
        ...
    }
}
```

Units:
```json
{
    "message_name": {
        ...
        "signals": {
            "signal_name": {
                ...
                "units": "kW"
            }
        }
    }
}
```
