# Talkactions

Talkactions are commands used by a creature to perform a specific task such as  

```xml
<talkaction words="/hello" script="helloworld.lua" />
```


```lua
--[[
    onSay is a talkaction script interface that allows creatures to execute commands 
    It's parameter's are player, words & param
    player is userdata and refers to the creature that is executing the command
    words are the spoken words that execute the command
    param are the arguments sent to the command if any
]]
function onSay(player, words, param)
    --[[
        At this point in the script it is saying
        To get the player's account type and compare it
        to see if it is less than or equal to ( <= ) a god account type
        The return value of player:getAccountType() & the assigned value of 
        ACCOUNT_TYPE_GOD are numbers
    ]]
    if player:getAccountType() <= ACCOUNT_TYPE_GOD then
        -- if it is then exit the script
        -- returning true allows the command to appear above the player's head for all to see
        return true
    end

    -- if it isn't then send a text message to the player executing the command
    player:sendTextMessage(MESSAGE_EVENT_ADVANCE, "Hello World")

    -- returning false prevents the words from appearing above the player's head
    return false
end
```



