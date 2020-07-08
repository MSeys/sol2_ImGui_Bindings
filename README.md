# sol2_ImGui_Bindings

## Windows
```lua
  -- ImGui.Begin(...)
  -- Parameters: text (name), bool (open) [O], ImGuiWindowFlags (flags) [O]
  -- Returns A: bool (shouldDraw)
  -- Returns B & C: bool (open), bool (shouldDraw)
  -- Overloads
  shouldDraw = ImGui.Begin("Name")
  open, shouldDraw = ImGui.Begin("Name", open)
  open, shouldDraw = ImGui.Begin("Name", open, ImGuiWindowFlags.NoMove)
  
  -- ImGui.End()
  ImGui.End()
```

## Child Windows
```lua
  -- ImGui.BeginChild(...)
  -- Parameters: text (name), float (size_x) [O], float (size_y) [O], ImGuiWindowFlags (flags) [O]
  -- Returns: bool (shouldDraw)
  -- Overloads
  shouldDraw = ImGui.BeginChild("Name", 100)
  shouldDraw = ImGui.BeginChild("Name", 100)
  shouldDraw = ImGui.BeginChild("Name", 100, 200)
  shouldDraw = ImGui.BeginChild("Name", 100, 200, true)
  shouldDraw = ImGui.BeginChild("Name", 100, 200, true, ImGuiWindowFlags.NoMove)
  
  -- ImGui.EndChild()
  ImGui.EndChild()
```

## Windows Utilities
```lua
  -- ImGui.IsWindowAppearing()
  -- Returns: bool (appearing)
  appearing = ImGui.IsWindowAppearing()
  
  -- ImGui.IsWindowCollapsed()
  -- Returns: bool (collapsed)
  collapsed = ImGui.IsWindowCollapsed()
  
  -- ImGui.IsWindowFocused(...)
  -- Parameters: ImGuiFocusedFlags (flags) [O]
  -- Returns: bool (focused)
  -- Overloads
  focused = ImGui.IsWindowFocused()
  focused = ImGui.IsWindowFocused(ImGuiFocusedFlags.ChildWindows)
  
  -- ImGui.IsWindowHovered(...)
  -- Parameters: ImGuiHoveredFlags (flags) [O]
  -- Returns: bool (hovered)
  -- Overloads
  hovered = ImGui.IswindowHovered()
  hovered = ImGui.IsWindowHovered(ImGuiHoveredFlags.ChildWindows)
  
  -- ImGui.GetWindowDpiScale()
  -- Returns: float (dpiScale)
  dpiScale = ImGui.GetWindowDpiScale()
  
  -- ImGui.GetWindowPos()
  -- Returns: float (pos_x), float (pos_y)
  pos_x, pos_y = ImGui.GetWindowPos()
  
  -- ImGui.GetWindowSize()
  -- Returns: float (size_x), float (size_y)
  size_x, size_y = ImGui.GetWindowSize()
  
  -- ImGui.GetWindowWidth()
  -- Returns: float (width)
  width = ImGui.GetWindowWidth()
  
  -- ImGui.GetWindowHeight()
  -- Returns: float (height)
  height = ImGui.GetWindowHeight()
  
  -- ImGui.SetNextWindowPos(...)
  -- Parameters: float (pos_x), float (pos_y), ImGuiCond (cond) [O], float (pivot_x) [O], float (pivot_y) [O]
  -- Overloads
  ImGui.SetNextWindowPos(100, 100)
  ImGui.SetNextWindowPos(100, 100, ImGuiCond.Always)
  ImGui.SetNextWindowPos(100, 100, ImGuiCond.Always, 0, 0.5)
  
  -- ImGui.SetNextWindowSize(...)
  -- Parameters: float (size_x), float (size_y), ImGuiCond (cond) [O]
  -- Overloads
  ImGui.SetNextWindowSize(500, 500)
  ImGui.SetNextWindowSize(500, 500, ImGuiCond.Appearing)
  
  -- ImGui.SetNextWindowSizeConstraints(...)
  -- Parameters: float (min_x), float (min_y), float (max_x), float (max_y)
  ImGui.SetNextWindowSizeConstraints(100, 100, 500, 600)
  
  -- ImGui.SetNextWindowContentSize(...)
  -- Parameters: float (size_x), float (size_y)
  ImGui.SetNextWindowContentSize(200, 100)
  
  -- ImGui.SetNextWindowCollapsed(...)
  -- Parameters: bool (collapsed), ImGuiCond (cond) [O]
  -- Overloads
  ImGui.SetNextWindowCollapsed(true)
  ImGui.SetNextWindowCollapsed(true, ImGuiCond.Appearing)
  
  -- ImGui.SetNextWindowFocus()
  ImGui.SetNextWindowFocus()
  
  -- ImGui.SetNextWindowBgAlpha(...)
  -- Parameters: float (alpha)
  ImGui.SetNextWindowBgAlpha(0.5)
  
  -- ImGui.SetWindowPos(...)
  -- Parameters: float (pos_x), float (pos_y), ImguiCond (cond) [O]
  -- Overloads
  ImGui.SetWindowPos(100, 100)
  ImGui.SetWindowPos(100, 100, ImGuiCond.Appearing)
  
  -- ImGui.SetWindowSize(...)
  -- Parameters: float (size_x), float (size_y), ImguiCond (cond) [O]
  -- Overloads
  ImGui.SetWindowSize(100, 300)
  ImGui.SetWindowSize(100, 300, ImGuiCond.Appearing)
  
  -- ImGui.SetWindowCollapsed(...)
  -- Parameters: bool (collapsed), ImguiCond (cond) [O]
  -- Overloads
  ImGui.SetWindowCollapsed(false)
  ImGui.SetWindowCollapsed(true, ImGuiCond.Appearing)
  
  -- ImGui.SetWindowFocus()
  ImGui.SetWindowFocus()
  
  -- ImGui.SetWindowFontScale(...)
  -- Parameters: float (scale)
  ImGui.SetWindowFontScale(1.2)
  
  -- ImGui.SetWindowPos(...)
  -- Parameters: text (name), float (pos_x), float (pos_y), ImGuiCond (cond) [O]
  -- Overloads
  ImGui.SetWindowPos("WindowName", 100, 100)
  ImGui.SetWindowPos("WindowName", 100, 100, ImGuiCond.Always)
  
  -- ImGui.SetWindowSize(...)
  -- Parameters: text (name), float (size_x), float (size_y), ImGuiCond (cond) [O]
  -- Overloads
  ImGui.SetWindowSize("WindowName", 300, 400)
  ImGui.SetWindowSize("WindowName", 300, 400, ImGuiCond.Always)
  
  -- ImGui.SetWindowCollapsed(...)
  -- Parameters: text (name), bool (collapsed), ImGuiCond (cond) [O]
  -- Overloads
  ImGui.SetWindowCollapsed("WindowName", true)
  ImGui.SetWindowCollapsed("WindowName", false, ImGuiCond.Always)
  
  -- ImGui.SetWindowFocus(...)
  -- Parameters: text (name)
  ImGui.SetWindowFocus("WindowName")
```

## Content Region
```lua
  -- ImGui.GetContentRegionMax()
  -- Returns: float (x), float (y)
  x, y = ImGui.GetContentRegionMax()
  
  -- ImGui.GetContentRegionAvail()
  -- Returns: float (x), float (y)
  x, y = ImGui.GetContentRegionAvail()
  
  -- ImGui.GetWindowContentRegionMin()
  -- Returns: float (x), float (y)
  x, y = ImGui.GetWindowContentRegionMin()
  
  -- ImGui.GetWindowContentRegionMax()
  -- Returns: float (x), float (y)
  x, y = ImGui.GetWindowContentRegionMax()
  
  -- ImGui.GetWindowContentRegionWidth()
  -- Returns: float (width)
  width = ImGui.GetWindowContentRegionWidth()
```

## Windows Scrolling
```lua
  -- ImGui.GetScrollX()
  -- Returns: float (x)
  x = ImGui.GetScrollX()
  
  -- ImGui.GetScrollY()
  -- Returns: float (y)
  y = ImGui.GetScrollY()
  
  -- ImGui.GetScrollMaxX()
  -- Returns: float (x)
  x = ImGui.GetScrollMaxX()
  
  -- ImGui.GetScrollMaxY()
  -- Returns: float (y)
  y = ImGui.GetScrollMaxY()
  
  -- ImGui.SetScrollX(...)
  -- Parameters: float (scroll_x)
  ImGui.SetScrollX(0.7)
  
  -- ImGui.SetScrollY(...)
  -- Parameters: float (scroll_y)
  ImGui.SetScrollY(0.7)
  
  -- ImGui.SetScrollHereX(...)
  -- Parameters: float (center_x_ratio) [O]
  -- Overloads
  ImGui.SetScrollHereX()
  ImGui.SetScrollHereX(0.5)
  
  -- ImGui.SetScrollHereY(...)
  -- Parameters: float (center_y_ratio) [O]
  -- Overloads
  ImGui.SetScrollHereY()
  ImGui.SetScrollHereY(0.5)
  
  -- ImGui.SetScrollFromPosX(...)
  -- Parameters: float (local_x), float (center_x_ratio) [O]
  -- Overloads
  ImGui.SetScrollFromPosX(10)
  ImGui.SetScrollFromPosX(10, 0.5)
  
  -- ImGui.SetScrollFromPosY(...)
  -- Parameters: float (local_y), float (center_y_ratio) [O]
  -- Overloads
  ImGui.SetScrollFromPosY(10)
  ImGui.SetScrollFromPosY(10, 0.5)
```

## Parameters Stacks (Shared)
Note: This binding does not give functions that can obtain an ImFont* from inside Lua (besides GetFont), You'll need to add your own.
```lua
  -- ImGui.PushFont(...)
  -- Parameters: ImFont* (font)
  ImGui.PushFont(font) -- font is obtained from your own custom function
  
  -- ImGui.PopFont()
  ImGui.PopFont()
  
  -- ImGui.PushStyleColor(...)
  -- Parameters: ImGuiCol (idx), float (color_r), float (color_g), float (color_b), float (color_a)
  ImGui.PushStyleColor(ImGuiCol.Border, 1, 0, 0, 1)
  
  -- ImGui.PopStyleColor(...)
  -- Parameters: int (count) [O]
  -- Overloads
  ImGui.PopStyleColor()
  ImGui.PopStyleColor(5)
  
  -- ImGui.PushStyleVar(...)
  -- Parameters A: ImGuiStyleVar (idx), float (value)
  -- Parameters B: ImGuiStyleVar (idx), float (value_x), float (value_y)
  -- Overloads
  ImGui.PushStyleVar(ImGuiStyleVar.Alpha, 0.5)
  ImGui.PushStyleVar(ImGuiStyleVar.WindowPadding, 0.2, 0.1)
  
  -- ImGui.PopStyleVar(...)
  -- Parameters: int (count) [O]
  ImGui.PopStyleVar()
  ImGui.PopStyleVar(2)
  
  -- ImGui.GetStyleColorVec4(...)
  -- Parameters: ImGuiCol (idx)
  -- Returns: float (color_r), float (color_g), float (color_b), float (color_a)
  color_r, color_g, color_b, color_a = ImGui.GetStyleColorVec4(ImGuiCol.Text)
  
  -- ImGui.GetFont()
  -- Returns: ImFont* (font) -- Only function in ImGui giving a font
  font = ImGui.GetFont()
  
  -- ImGui.GetFontSize()
  -- Returns: float (fontSize)
  fontSize = ImGui.GetFontSize()
  
  -- ImGui.GetFontTexUvWhitePixel()
  -- Returns: float (x), float (y)
  x, y = ImGui.GetFontTexUvWhitePixel()
```

## Parameter Stacks (Current Window)
```lua
  -- ImGui.PushItemWidth(...)
  -- Parameters: float (width)
  ImGui.PushItemWidth(100)
  
  -- ImGui.PopItemWidth()
  ImGui.PopItemWidth()
  
  -- ImGui.SetNextItemWidth(...)
  -- Parameters: float (width)
  ImGui.SetNextItemWidth(100)
  
  -- ImGui.CalcItemWidth()
  -- Returns: float (width)
  width = ImGui.CalcItemWidth()
  
  -- ImGui.PushTextWrapPos(...)
  -- Parameters: float (wrap_local_pos_x) [O]
  -- Overloads
  ImGui.PushTextWrapPos()
  ImGui.PushTextWrapPos(50)
  
  -- ImGui.PopTextWrapPos()
  ImGui.PopTextWrapPos()
  
  -- ImGui.PushAllowKeyboardFocus(...)
  -- Parameters: bool (allow_keyboard_focus)
  ImGui.PushAllowKeyboardFocus(true)
  
  -- ImGui.PopAllowKeyboardFocus()
  ImGui.PopAllowKeyboardFocus()
  
  -- ImGui.PushButtonRepeat(...)
  -- Parameters: bool (repeat)
  ImGui.PushButtonRepeat(true)
  
  -- ImGui.PopButtonRepeat()
  ImGui.PopButtonRepeat()
```

## Cursor / Layout
```lua
  -- ImGui.Separator()
  ImGui.Separator
  
  -- ImGui.SameLine(...)
  -- Parameters: float (offset_from_start_x) [O], float (spacing) [O]
  -- Overloads
  ImGui.SameLine()
  ImGui.SameLine(100)
  ImGui.SameLine(100, 5)
  
  -- ImGui.NewLine()
  ImGui.NewLine()
  
  -- ImGui.Spacing()
  ImGui.Spacing()
  
  -- ImGui.Dummy(...)
  -- Parameters: float (size_x), float (size_y)
  ImGui.Dummy(100, 200)
  
  -- ImGui.Indent(...)
  -- Parameters: float (indent_w) [O]
  ImGui.Indent()
  ImGui.Indent(10)
  
  -- ImGui.Unindent(...)
  -- Parameters: float (indent_w) [O]
  ImGui.Unindent()
  ImGui.Unindent(-10)
  
  -- ImGui.BeginGroup()
  ImGui.BeginGroup()
  
  -- ImGui.EndGroup()
  ImGui.EndGroup()
  
  -- ImGui.GetCursorPos()
  -- Returns: float (x), float(y)
  x, y = ImGui.GetCursorPos()
  
  -- ImGui.GetCursorPosX()
  -- Returns: float (x)
  x = ImGui.GetCursorPosX()
  
  -- ImGui.GetCursorPosY()
  -- Returns: float (y)
  y = ImGui.GetCursorPosY()
  
  -- ImGui.SetCursorPos(...)
  -- Parameters: float (x), float (y)
  ImGui.SetCursorPos(10, 10)
  
  -- ImGui.SetCursorPosX(...)
  -- Parameters: float (x)
  ImGui.SetCursorPosX(10)
  
  -- ImGui.SetCursorPosY(...)
  -- Parameters: float (y)
  ImGui.SetCursorPosY(10)
  
  -- ImGui.GetCursorStartPos()
  -- Returns: float (x), float(y)
  x, y = ImGui.GetCursorStartPos()
  
  -- ImGui.GetCursorScreenPos()
  -- Returns: float (x), float(y)
  x, y = ImGui.GetCursorScreenPos()
  
  -- ImGui.SetCursorScreenPos(...)
  -- Parameters: float (x), float (y)
  ImGui.SetCursorScreenPos(10, 10)
  
  -- ImGui.AlignTextToFramePadding()
  ImGui.AlignTextToFramePadding()
  
  -- ImGui.GetTextLineHeight()
  -- Returns: float (height)
  height = ImGui.GetTextLineHeight()
  
  -- ImGui.GetTextLineHeightWithSpacing()
  -- Returns: float (height)
  height = ImGui.GetTextLineHeightWithSpacing()
  
  -- ImGui.GetFrameHeight()
  -- Returns: float (height)
  height = ImGui.GetFrameHeight()
  
  -- ImGui.GetFrameHeightWithSpacing()
  -- Returns: float (height)
  height = ImGui.GetFrameHeightWithSpacing()
```

## ID Stack / Scopes
```lua
  -- ImGui.PushID(...)
  -- Parameters A: text (str_id)
  -- Parameters B: text (str_id_begin), text (str_id_end)
  -- Parameters C: int (int_id)
  -- Overloads
  ImGui.PushID("MyID")
  ImGui.PushID("MyID_Begin", "MyID_End")
  ImGui.PushID(1)
  
  -- ImGui.PopID()
  ImGui.PopID()
  
  -- ImGui.GetID(...)
  -- Parameters A: text (str_id)
  -- Parameters B: text (str_id_begin), text (str_id_end)
  -- Returns: int (id)
  -- Overloads
  id = ImGui.PushID("MyID")
  id = ImGui.PushID("MyID_Begin", "MyID_End")
```

## Widgets: Text
```lua
  -- ImGui.TextUnformatted(...)
  -- Parameters: text (text), text (text_end) [O]
  -- Overloads
  ImGui.TextUnformatted("I am Unformatted")
  ImGui.TextUnformatted("I am ", "Unformatted")
  
  -- ImGui.Text(...)
  -- Parameters: text (text)
  ImGui.Text("Well hello there, General Kenobi")
  
  -- ImGui.TextColored(...)
  -- Parameters: float (color_r), float (color_g), float (color_b), float (color_a), text (text)
  ImGui.TextColored(1, 0, 0, 1, "Well hello there, General Kenobi")
  
  -- ImGui.TextDisabled(...)
  -- Parameters: text (text)
  ImGui.TextDisabled("Well hello there, General Kenobi")
  
  -- ImGui.TextWrapped(...)
  -- Parameters: text (text)
  ImGui.TextWrapped("Well hello there, General Kenobi")
  
  -- ImGui.LabelText(...)
  -- Parameters: text (label), text (text)
  ImGui.LabelText("Well hello there", "General Kenobi")
  
  -- ImGui.BulletText(...)
  -- Parameters: text (text)
  ImGui.BulletText("Well hello there, General Kenobi")
```

## Widgets: Main
```lua
  -- ImGui.Button(...)
  -- Parameters: text (label), float (size_x) [O], float (size_y) [O]
  -- Returns: bool (clicked)
  -- Overloads
  clicked = ImGui.Button("Label")
  clicked = ImGui.Button("Label", 100, 50)
  
  -- ImGui.SmallButton(...)
  -- Parameters: text (label)
  -- Returns: bool (clicked)
  clicked = ImGui.SmallButton("Label")
  
  -- ImGui.InvisibleButton(...)
  -- Parameters: text (label), float (size_x), float (size_y)
  -- Returns: bool (clicked)
  clicked = ImGui.InvisibleButton("Label", 100, 50)
  
  -- ImGui.ArrowButton(...)
  -- Parameters: text (str_id), ImGuiDir (dir)
  -- Returns: bool (clicked)
  clicked = ImGui.ArrowButton("I have an arrow", ImGuiDir.Down)
  
  -- ImGui.Checkbox(...)
  -- Parameters: text (label), bool (value)
  -- Returns: bool (value), bool (pressed)
  value, pressed = ImGui.Checkbox("My Checkbox", value)
  
  -- ImGui.RadioButton(...)
  -- Parameters A: text (label), bool (active)
  -- Parameters B: text (label), int (value), int (v_button)
  -- Returns A: bool (pressed)
  -- Returns B: int (value), bool (pressed)
  -- Overloads
  pressed = ImGui.RadioButton("Click me", pressed == true)
  value, pressed = ImGui.RadioButton("Click me too", value, 2)
  
  -- ImGui.ProgressBar(...)
  -- Parameters: float (fraction), float (size_x) [O], float (size_y) [O], text (overlay) [O]
  -- Overloads
  ImGui.ProgressBar(0.5)
  ImGui.ProgressBar(0.5, 100, 25)
  ImGui.ProgressBar(0.5, 100, 25, "Loading Failed. Sike. - 50%")
  
  -- ImGui.Bullet()
  ImGui.Bullet()
```

## Widgets: Combo Box
```lua
  -- ImGui.BeginCombo(...)
  -- Parameters: text (label), text (previewValue), ImGuiComboFlags (flags) [O]
  -- Returns: bool (shouldDraw)
  -- Overloads
  shouldDraw = ImGui.BeginCombo("My Combo", "Preview")
  shouldDraw = ImGui.BeginCombo("My Combo", "Preview", ImGuiComboFlags.PopupAlignLeft)
  
  -- ImGui.EndCombo()
  ImGui.EndCombo()
  
  -- ImGui.Combo(...)
  -- Parameters A: text (label), int (current_item), table (items), int (items_count), int (popup_max_height_in_items) [O] 
  -- Parameters B: text (label), int (current_item), text (items_separated_by_zeros), int (popup_max_height_in_items) [O] 
  -- Returns: int (current_item), bool (clicked)
  -- Overloads
  current_item, clicked = ImGui.Combo("Label", current_item, { "Option 1 ", "Option 2" }, 2)
  current_item, clicked = ImGui.Combo("Label", current_item, { "Option 1 ", "Option 2" }, 2, 5)
  current_item, clicked = ImGui.Combo("Label", current_item, "Option1\0Option2\0")
  current_item, clicked = ImGui.Combo("Label", current_item, "Option1\0Option2\0", 5)
```

## Widgets: Drags
```lua
  -- ImGui.DragFloat(...)
  -- Parameters: text (label), float (value), float (value_speed) [O], float (value_min) [O], float (value_max) [O], text (format) [O], float (power) [O]
  -- Returns: float (value), bool (used)
  -- Overloads
  value, used = ImGui.DragFloat("Label", value)
  value, used = ImGui.DragFloat("Label", value, 0.01)
  value, used = ImGui.DragFloat("Label", value, 0.01, -10)
  value, used = ImGui.DragFloat("Label", value, 0.01, -10, 10)
  value, used = ImGui.DragFloat("Label", value, 0.01, -10, 10, "%.1f")
  value, used = ImGui.DragFloat("Label", value, 0.01, -10, 10, "%.1f", 0.5)
  
  -- ImGui.DragFloat2(...)
  -- Parameters: text (label), table (values), float (value_speed) [O], float (value_min) [O], float (value_max) [O], text (format) [O], float (power) [O]
  -- Returns: table (values), bool (used)
  -- Overloads
  values, used = ImGui.DragFloat2("Label", values)
  values, used = ImGui.DragFloat2("Label", values, 0.01)
  values, used = ImGui.DragFloat2("Label", values, 0.01, -10)
  values, used = ImGui.DragFloat2("Label", values, 0.01, -10, 10)
  values, used = ImGui.DragFloat2("Label", values, 0.01, -10, 10, "%.1f")
  values, used = ImGui.DragFloat2("Label", values, 0.01, -10, 10, "%.1f", 0.5)
  
  -- ImGui.DragFloat3(...)
  -- Parameters: text (label), table (values), float (value_speed) [O], float (value_min) [O], float (value_max) [O], text (format) [O], float (power) [O]
  -- Returns: table (values), bool (used)
  -- Overloads
  values, used = ImGui.DragFloat3("Label", values)
  values, used = ImGui.DragFloat3("Label", values, 0.01)
  values, used = ImGui.DragFloat3("Label", values, 0.01, -10)
  values, used = ImGui.DragFloat3("Label", values, 0.01, -10, 10)
  values, used = ImGui.DragFloat3("Label", values, 0.01, -10, 10, "%.1f")
  values, used = ImGui.DragFloat3("Label", values, 0.01, -10, 10, "%.1f", 0.5)
  
  -- ImGui.DragFloat4(...)
  -- Parameters: text (label), table (values), float (value_speed) [O], float (value_min) [O], float (value_max) [O], text (format) [O], float (power) [O]
  -- Returns: table (values), bool (used)
  -- Overloads
  values, used = ImGui.DragFloat4("Label", values)
  values, used = ImGui.DragFloat4("Label", values, 0.01)
  values, used = ImGui.DragFloat4("Label", values, 0.01, -10)
  values, used = ImGui.DragFloat4("Label", values, 0.01, -10, 10)
  values, used = ImGui.DragFloat4("Label", values, 0.01, -10, 10, "%.1f")
  values, used = ImGui.DragFloat4("Label", values, 0.01, -10, 10, "%.1f", 0.5)
  
  -- ImGui.DragInt(...)
  -- Parameters: text (label), int (value), float (value_speed) [O], int (value_min) [O], int (value_max) [O], text (format) [O]
  -- Returns: int (value), bool (used)
  -- Overloads
  value, used = ImGui.DragInt("Label", value)
  value, used = ImGui.DragInt("Label", value, 0.01)
  value, used = ImGui.DragInt("Label", value, 0.01, -10)
  value, used = ImGui.DragInt("Label", value, 0.01, -10, 10)
  value, used = ImGui.DragInt("Label", value, 0.01, -10, 10, "%d")
  
  -- ImGui.DragInt2(...)
  -- Parameters: text (label), table (values), float (value_speed) [O], int (value_min) [O], int (value_max) [O], text (format) [O]
  -- Returns: table (values), bool (used)
  -- Overloads
  values, used = ImGui.DragInt2("Label", values)
  values, used = ImGui.DragInt2("Label", values, 0.01)
  values, used = ImGui.DragInt2("Label", values, 0.01, -10)
  values, used = ImGui.DragInt2("Label", values, 0.01, -10, 10)
  values, used = ImGui.DragInt2("Label", values, 0.01, -10, 10, "%d")
  
  -- ImGui.DragInt3(...)
  -- Parameters: text (label), table (values), float (value_speed) [O], int (value_min) [O], int (value_max) [O], text (format) [O]
  -- Returns: table (values), bool (used)
  -- Overloads
  values, used = ImGui.DragInt3("Label", values)
  values, used = ImGui.DragInt3("Label", values, 0.01)
  values, used = ImGui.DragInt3("Label", values, 0.01, -10)
  values, used = ImGui.DragInt3("Label", values, 0.01, -10, 10)
  values, used = ImGui.DragInt3("Label", values, 0.01, -10, 10, "%d")
  
  -- ImGui.DragInt4(...)
  -- Parameters: text (label), table (values), float (value_speed) [O], int (value_min) [O], int (value_max) [O], text (format) [O]
  -- Returns: table (values), bool (used)
  -- Overloads
  values, used = ImGui.DragInt4("Label", values)
  values, used = ImGui.DragInt4("Label", values, 0.01)
  values, used = ImGui.DragInt4("Label", values, 0.01, -10)
  values, used = ImGui.DragInt4("Label", values, 0.01, -10, 10)
  values, used = ImGui.DragInt4("Label", values, 0.01, -10, 10, "%d")
```

## Widgets: Sliders
```lua
  -- ImGui.SliderFloat(...)
  -- Parameters: text (label), float (value), float (value_min), float (value_max), text (format) [O], float (power) [O]
  -- Returns: float (value), bool (used)
  -- Overloads
  value, used = ImGui.SliderFloat("Label", value, -10, 10)
  value, used = ImGui.SliderFloat("Label", value, -10, 10, "%.1f")
  value, used = ImGui.SliderFloat("Label", value, -10, 10, "%.1f", 0.5)
  
  -- ImGui.SliderFloat2(...)
  -- Parameters: text (label), table (values), float (value_min), float (value_max), text (format) [O], float (power) [O]
  -- Returns: table (values), bool (used)
  -- Overloads
  values, used = ImGui.SliderFloat2("Label", values, 0.01, -10, 10)
  values, used = ImGui.SliderFloat2("Label", values, 0.01, -10, 10, "%.1f")
  values, used = ImGui.SliderFloat2("Label", values, 0.01, -10, 10, "%.1f", 0.5)
  
  -- ImGui.SliderFloat3(...)
  -- Parameters: text (label), table (values), float (value_min), float (value_max), text (format) [O], float (power) [O]
  -- Returns: table (values), bool (used)
  -- Overloads
  values, used = ImGui.SliderFloat3("Label", values, 0.01, -10, 10)
  values, used = ImGui.SliderFloat3("Label", values, 0.01, -10, 10, "%.1f")
  values, used = ImGui.SliderFloat3("Label", values, 0.01, -10, 10, "%.1f", 0.5)
  
  -- ImGui.SliderFloat4(...)
  -- Parameters: text (label), table (values), float (value_min), float (value_max), text (format) [O], float (power) [O]
  -- Returns: table (values), bool (used)
  -- Overloads
  values, used = ImGui.SliderFloat4("Label", values, 0.01, -10, 10)
  values, used = ImGui.SliderFloat4("Label", values, 0.01, -10, 10, "%.1f")
  values, used = ImGui.SliderFloat4("Label", values, 0.01, -10, 10, "%.1f", 0.5)
  
  -- ImGui.SliderAngle(...)
  -- Parameters: text (label), float (v_rad), float (v_degrees_min) [O], float (v_degrees_max) [O], text (format) [O]
  -- Returns: float (v_rad), bool (used)
  -- Overloads
  v_rad, used = ImGui.SliderAngle("Label", v_rad)
  v_rad, used = ImGui.SliderAngle("Label", v_rad, -255)
  v_rad, used = ImGui.SliderAngle("Label", v_rad, -255, 360)
  v_rad, used = ImGui.SliderAngle("Label", v_rad, -255, 360, "%.0f deg")
  
  -- ImGui.SliderInt(...)
  -- Parameters: text (label), int (value), int (value_min), int (value_max), text (format) [O]
  -- Returns: int (value), bool (used)
  -- Overloads
  value, used = ImGui.SliderInt("Label", value, -10, 10)
  value, used = ImGui.SliderInt("Label", value, -10, 10, "%d")
  
  -- ImGui.SliderInt2(...)
  -- Parameters: text (label), table (values), int (value_min), int (value_max), text (format) [O]
  -- Returns: table (values), bool (used)
  -- Overloads
  values, used = ImGui.SliderInt2("Label", values, -10, 10)
  values, used = ImGui.SliderInt2("Label", values, -10, 10, "%d")
  
  -- ImGui.SliderInt3(...)
  -- Parameters: text (label), table (values), int (value_min), int (value_max), text (format) [O]
  -- Returns: table (values), bool (used)
  -- Overloads
  values, used = ImGui.SliderInt3("Label", values, -10, 10)
  values, used = ImGui.SliderInt3("Label", values, -10, 10, "%d")
  
  -- ImGui.SliderInt4(...)
  -- Parameters: text (label), table (values), int (value_min), int (value_max), text (format) [O]
  -- Returns: table (values), bool (used)
  -- Overloads
  values, used = ImGui.SliderInt4("Label", values, -10, 10)
  values, used = ImGui.SliderInt4("Label", values, -10, 10, "%d")
  
  -- ImGui.VSliderFloat(...)
  -- Parameters: text (label), float (size_x), float (size_y), float (value), float (value_min), float (value_max), text (format) [O], float (power) [O]
  -- Returns: float (value), bool (used)
  -- Overloads
  value, used = ImGui.VSliderFloat("Label", 100, 25, value, -10, 10)
  value, used = ImGui.VSliderFloat("Label", 100, 25, value, -10, 10, "%.1f")
  value, used = ImGui.VSliderFloat("Label", 100, 25, value, -10, 10, "%.1f", 0.5)
  
  -- ImGui.VSliderInt(...)
  -- Parameters: text (label), float (size_x), float (size_y), int (value), int (value_min), int (value_max), text (format) [O]
  -- Returns: int (value), bool (used)
  -- Overloads
  value, used = ImGui.VSliderInt("Label", 100, 25, value, -10, 10)
  value, used = ImGui.VSliderInt("Label", 100, 25, value, -10, 10, "%d")
```

## Widgets: Input with Keyboard
```lua
  -- ImGui.InputText(...)
  -- Parameters: text (label), text (text), int (buf_size), ImGuiInputTextFlags (flags) [O]
  -- Returns: text (text), bool (selected)
  -- Overloads
  text, selected = ImGui.InputText("Label", text, 100)
  text, selected = ImGui.InputText("Label", text, 100, ImGuiInputTextFlags.ReadOnly)
  
  -- ImGui.InputTextMultiline(...)
  -- Parameters: text (label), text (text), int (buf_size), float (size_x) [O], float (size_y) [O], ImGuiInputTextFlags (flags) [O]
  -- Returns: text (text), bool (selected)
  -- Overloads
  text, selected = ImGui.InputTextMultiline("Label", text, 100)
  text, selected = ImGui.InputTextMultiline("Label", text, 100, 200, 35)
  text, selected = ImGui.InputTextMultiline("Label", text, 100, 200, 35, ImGuiInputTextFlags.ReadOnly)
  
  -- ImGui.InputTextWithHint(...)
  -- Parameters: text (label), text (hint), text (text), int (buf_size), ImGuiInputTextFlags (flags) [O]
  -- Returns: text (text), bool (selected)
  -- Overloads
  text, selected = ImGui.InputTextWithHint("Label", "Hint", text, 100)
  text, selected = ImGui.InputTextWithHint("Label", "Hint", text, 100, ImGuiInputTextFlags.ReadOnly)
  
  -- ImGui.InputFloat(...)
  -- Parameters: text (label), float (value), float (step) [O], float (step_fast) [O], text (format) [O], ImGuiInputTextFlags (flags) [O]
  -- Returns: float (value), bool (used)
  -- Overloads
  value, used = ImGui.InputFloat("Label", value)
  value, used = ImGui.InputFloat("Label", value, 1)
  value, used = ImGui.InputFloat("Label", value, 1, 10)
  value, used = ImGui.InputFloat("Label", value, 1, 10, "%.1f")
  value, used = ImGui.InputFloat("Label", value, 1, 10, "%.1f", ImGuiInputTextFlags.None)
  
  -- ImGui.InputFloat2(...)
  -- Parameters: text (label), table (values), text (format) [O], ImGuiInputTextFlags (flags) [O]
  -- Returns: table (values), bool (used)
  -- Overloads
  values, used = ImGui.InputFloat2("Label", values)
  values, used = ImGui.InputFloat2("Label", values, "%.1f")
  values, used = ImGui.InputFloat2("Label", values, "%.1f", ImGuiInputTextFlags.None)
  
  -- ImGui.InputFloat3(...)
  -- Parameters: text (label), table (values), text (format) [O], ImGuiInputTextFlags (flags) [O]
  -- Returns: table (values), bool (used)
  -- Overloads
  values, used = ImGui.InputFloat3("Label", values)
  values, used = ImGui.InputFloat3("Label", values, "%.1f")
  values, used = ImGui.InputFloat3("Label", values, "%.1f", ImGuiInputTextFlags.None)
  
  -- ImGui.InputFloat4(...)
  -- Parameters: text (label), table (values), text (format) [O], ImGuiInputTextFlags (flags) [O]
  -- Returns: table (values), bool (used)
  -- Overloads
  values, used = ImGui.InputFloat4("Label", values)
  values, used = ImGui.InputFloat4("Label", values, "%.1f")
  values, used = ImGui.InputFloat4("Label", values, "%.1f", ImGuiInputTextFlags.None)
  
  -- ImGui.InputInt(...)
  -- Parameters: text (label), int (value), int (step) [O], int (step_fast) [O], ImGuiInputTextFlags (flags) [O] 
  -- Returns: int (value), bool (used)
  -- Overloads
  value, used = ImGui.InputInt("Label", value)
  value, used = ImGui.InputInt("Label", value, 1)
  value, used = ImGui.InputInt("Label", value, 1, 10)
  value, used = ImGui.InputInt("Label", value, 1, 10, ImGuiInputTextFlags.None)
  
  -- ImGui.InputInt2(...)
  -- Parameters: text (label), table (values), ImGuiInputTextFlags (flags) [O] 
  -- Returns: table (values), bool (used)
  -- Overloads
  values, used = ImGui.InputInt2("Label", values)
  values, used = ImGui.InputInt2("Label", values, ImGuiInputTextFlags.None)
  
  -- ImGui.InputInt3(...)
  -- Parameters: text (label), table (values), ImGuiInputTextFlags (flags) [O] 
  -- Returns: table (values), bool (used)
  -- Overloads
  values, used = ImGui.InputInt3("Label", values)
  values, used = ImGui.InputInt3("Label", values, ImGuiInputTextFlags.None)
  
  -- ImGui.InputInt4(...)
  -- Parameters: text (label), table (values), ImGuiInputTextFlags (flags) [O] 
  -- Returns: table (values), bool (used)
  -- Overloads
  values, used = ImGui.InputInt4("Label", values)
  values, used = ImGui.InputInt4("Label", values, ImGuiInputTextFlags.None)
  
  -- ImGui.InputDouble(...)
  -- Parameters: text (label), double (value), double (step) [O], double (step_fast) [O], text (format) [O], ImGuiInputTextFlags (flags) [O]
  -- Returns: double (value), bool (used)
  -- Overloads
  value, used = ImGui.InputDouble("Label", value)
  value, used = ImGui.InputDouble("Label", value, 1)
  value, used = ImGui.InputDouble("Label", value, 1, 10)
  value, used = ImGui.InputDouble("Label", value, 1, 10, "%.4f")
  value, used = ImGui.InputDouble("Label", value, 1, 10, "%.4f", ImGuiInputTextFlags.None)
```
