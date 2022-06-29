# JSON

This high-level schema represents a subset of the Vector DBC standard.

A bus is broken down into subsystems called ECUs (Electronic Control Units), each of which defines their own properties. This hierarchy is reflected in the expected project structure.
```
bus
| --
| ecu_1
|     ecu_1.json
|     ecu_1_enum.json
|     ecu_1_rx.json
|     ecu_1_tx.json
| --
| ecu_2
|     ecu_2.json
|     ecu_2_enum.json
|     ecu_2_rx.json
|     ecu_1_tx.json
| --
| shared_enum.json
```

Note that this system assumes that none of the ECUs are sending the same message ID.

# Codegen
