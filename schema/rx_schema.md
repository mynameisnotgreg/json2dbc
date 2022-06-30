Define messages that each ECU wants to receive messages from. Codegen will only define receive functions for these messages.

Note that you can't define receivers on a signal level - the receivers for each message are common for all of the message's signals.

Create a field with each message name and set each value to `null`:
```json
{
    "example_message_1": null,
    "example_message_2": null,
    "example_message_3": null,
    "example_message_4": null,
    "example_message_5": null,
    "example_message_6": null
}
```
