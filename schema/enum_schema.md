Define the value of every field. This is good for readibility but can make refactoring difficult (note: may support automatic numbering using `null` in the future).

```json
{
    "enum_example_1": {
        "EXAMPLE_1_FIELD_0": 0,
        "EXAMPLE_1_FIELD_1": 1,
        "EXAMPLE_1_FIELD_2": 2,
        "EXAMPLE_1_FIELD_3": 3,
        "EXAMPLE_1_FIELD_4": 4,
        "EXAMPLE_1_FIELD_5": 5,
        "EXAMPLE_1_FIELD_6": 6,
        "EXAMPLE_1_FIELD_7": 7,
        "EXAMPLE_1_FIELD_8": 8
    },
    "enum_example_2": {
        "EXAMPLE_2_FIELD_0": 0,
        "EXAMPLE_2_FIELD_1": 1,
        "EXAMPLE_2_FIELD_2": 2,
        "EXAMPLE_2_FIELD_3": 3
    },
}
```

The ECU TX JSON defines which enums each signal uses, if any. Enums can be defined at the ECU or global level, but must be defined only once.
```
bus
| --
| ecu_1
|     ecu_1_enum.json
|     ecu_1_tx.json
|     ...
| --
| ecu_2
|     ecu_2_enum.json
|     ecu_2_tx.json
|     ...
| --
| shared_enum.json
```
