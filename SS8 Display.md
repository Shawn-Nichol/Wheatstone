# SS8 

## How to update the screen with subroutine
You will need to create a subroutine for each SS8 button 

```

variable: vStage = 0
variable: vSubStage
variable: vBTNColorText
variable: vBTNColorBackground
variable: vBTNTextTop
variable: vBTNTextBot

cal 
/*
 * DisplaysBTN6: Displays the information on BTN 4
 *	@Parameter $1 TextColor 
 *	@Parameter $2 Background Color 
 * 	@Parameter $3 TextBox 1, top half of button
 *	@Parameter $4 TextBox 2, bottom half of button
 */
subroutine: BTN_6_DISPLAY {
    vBTNColorText = $1
    vBTNColorBackground = $2
    vBTNTextTop = $3
    vBTNTextBot = $4    
    display_box_colors(AGL_btn6_buf1_tb1, vBTNColorText, vBTNColorBackground) 
    display_box_colors(AGL_btn6_buf1_tb2, vBTNColorText, vBTNColorBackground)
    display_box_draw_text(AGL_btn6_buf1_tb1, vBTNTextTop) 
    display_box_draw_text(AGL_btn6_buf1_tb2, vBTNTextBot)
    display_buffer_button(AGL_btn6_buf1, on, AGL_btn6) // Writes to button.   
}
```
