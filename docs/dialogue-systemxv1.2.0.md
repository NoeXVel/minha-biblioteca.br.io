### NEW FEATURES
- Added parser system.
- Added parser triggers

## <span style="color: blue">Fixes:</span>
- Alpha can be defined in the dialog initialization script, or in the text itself.
- The dialog box position can be defined in the dialog initialization script, or in the text.

# How to Use:
**1st** Go to the tab and then to Tools -> Import Local Package
<img width="723" height="238" alt="Captura de tela 2026-07-25 123003" src="https://github.com/user-attachments/assets/5390ceb9-6f48-47fd-b546-cc5cb016c581" />

**2nd** Select the downloaded file.
<img width="466" height="37" alt="Captura de tela 2026-07-25 123143" src="https://github.com/user-attachments/assets/4ac09ecd-331e-408a-87dd-ae5c7f2530e3" />

**3rd** Click on the file folder, click on Add All, then Import.
<img width="987" height="777" alt="Captura de tela 2026-07-25 123333" src="https://github.com/user-attachments/assets/8b0be5e0-df41-4831-a12d-92c88808b6c8" />

---

### How do I start a new text?

**1st**. Go to your Room, and create a new instance layer called GUI.
<img width="365" height="157" alt="Captura de tela 2026-07-25 123733" src="https://github.com/user-attachments/assets/ca5dcbc5-5464-4221-adc4-556c4f78e1f1" />

**2nd**. In the Room settings, click on Room Creation.
<img width="353" height="246" alt="Captura de tela 2026-07-25 123828" src="https://github.com/user-attachments/assets/b9114066-9c85-4cd7-81b3-6b5e24c8474e" />

**3rd**. Start the dialog using the script, define the name of the dialog that will be displayed (Editable in the library), then define its Position with DIALOGUE_POSITION (Choose Top, Middle or Bottom), then the alpha to 1 (Visible) or 0 (Invisible) for the opacity of the dialog box to disappear.
<img width="653" height="87" alt="Captura de tela 2026-07-25 123918" src="https://github.com/user-attachments/assets/d0dd3767-64b4-4289-856b-9cfc4dd716ed" />

---

### Parsers Tags:
```gml
+ "[color: white]" - To change the color of the following text, it also works with hexadecimal characters (#fffff).
+ "[/color]" - To change the color to the default.
+ "[size: 1]" - To change the text size.
+ "[/size]" - To change the text size to the default.
+ "[wave]" - To give the text a wave effect.
+ "[/wave]" - To stop the wave effect.
+ "[rainbow]" - To give the text a rainbow effect.
+ "[/rainbow]" - To stop the rainbow effect.
+ "[shake]" - To give the text a shake effect.
+ "[/shake]" - To stop the shake effect.
+ "[goto_room: room]" - So that, once the text is finalized, it can be moved to the designated room.
+ "[await:2]" - For Automatic Dialogue, once finished, it waits the defined amount of time and moves on to the next text.
+ "[new_text: npc_01]" - Once completed, proceed to the defined dialogue.
+ "[alpha: 1]" - To set the alpha opacity of the dialog box.
+ "[top]" - To position the dialog box at the top.
+ "[middle]" - To position the dialog box at the middle.
+ "[bottom]" - To position the dialog box at the bottom.
```

