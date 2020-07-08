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
```
