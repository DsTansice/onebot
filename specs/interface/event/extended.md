## 扩展事件字段

OneBot 实现可以在标准事件的基础上添加扩展字段，扩展字段名必须包含前缀，扩展字段值任意。

例子：

```json
{
        "id": "b6e65187-5ac0-489c-b431-53078e9d2bbb",
        "impl": "go_onebot_qq",
        "platform": "qq",
        "self_id": "123234",
        "time": 1632847927,
        "type": "message",
        "detail_type": "private",
        "sub_type": "",
        "message_id": "6283",
        "message": [
            {
                "type": "text",
                "data": {
                    "text": "OneBot is not a bot"
                }
            },
        ],
        "alt_message": "OneBot is not a bot",
        "group_id": "12345",
        "user_id": "8000000",
        "qq.raw_event_id": "78e9d2bb530b431",
        "qq.anonymous": {
            "name": "齐天大圣",
            "id": "87364587"
        }
    }
```

OneBot 实现可以扩展标准事件的子类型（`sub_type`），扩展的子类型必须包含前缀。

例子：

```json
{
    "id": "b6e65187-5ac0-489c-b431-53078e9d2bbb",
    "impl": "go_onebot_qq",
    "platform": "qq",
    "self_id": "123234",
    "time": 1632847927,
    "type": "notice",
    "detail_type": "friend_increase",
    "sub_type": "qq.unidirectional",
    "user_id": "123456788"
}
```

## 扩展事件

OneBot 实现不得扩展事件的基本类型（`type`）。

OneBot 实现可以扩展事件的具体类型（`detail_type`），扩展的具体事件称为**扩展事件**，扩展的具体事件类型必须包含前缀。扩展事件仍必须包含 [OneBotRPC - 事件](../../onebotrpc/data-protocol/event.md) 中定义的所有字段，除此之外的字段可以任意命名。

例子：

```json
{
    "id": "b6e65187-5ac0-489c-b431-53078e9d2bbb",
    "impl": "go_onebot_qq",
    "platform": "qq",
    "self_id": "123234",
    "time": 1632847927,
    "type": "notice",
    "detail_type": "qq.group_file_upload",
    "sub_type": "",
    "group_id": "87654321",
    "user_id": "123456788",
    "file_id": "e30f9684-3d54-4f65-b2da-db291a477f16"
}
```
