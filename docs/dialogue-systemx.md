### HOW TO USE:
- 1st: Open your room and create an instance_layer called "GUI"
- 2nd: If you want to start the text in the room, open the Room Creation Code -  and add the following inside:
"scr_dialogue_start("dialogueID", DIALOGUE_POSITION.[Enter MIDDLE, TOP or BOTTOM without curly braces], [Alpha 0 or 1])"

- 3rd: Have fun, and use your creativity as you see fit, change the sprite
of the box, or the arrow, create your dialogues with case "DialogueName": return["Dialogue"] break; in scr_dialogue_library


### HOW TO USE IN ROOM CREATION:
# ex: ```gml scr_dialogue_start("npc_02", DIALOGUE_POSITION.MIDDLE, 0);```