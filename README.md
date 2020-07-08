# sol2_ImGui_Bindings

## Windows
```lua
  -- ImGui.Begin(...)
  -- Parameters: text (name), bool (open) [O], ImGuiWindowFlags (flags) [O]
  -- Returns: bool (open), bool (shouldDraw)
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
