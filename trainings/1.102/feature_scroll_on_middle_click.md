---
feature: "Scroll on Middle Click"
release: "1.102"
prerequisites:
  - "Mouse with middle button/scroll wheel"
  - "Basic understanding of VS Code editor"
audience: "All VS Code users who prefer mouse-based navigation"
---

# 🚀 Feature Training: `Scroll on Middle Click` in VS Code `1.102`

## 1. Overview

- **Feature Name:** `Scroll on Middle Click`
- **Release Version:** `1.102`
- **Feature Type:** `Editor Enhancement`
- **Summary:**  
  New editor feature that enables smooth scrolling by clicking and dragging with the middle mouse button, similar to browser autoscroll functionality.

## 2. Why It Matters

- **Improved Navigation:** Provides smooth, controlled scrolling in any direction within the editor
- **Browser-like Experience:** Familiar autoscroll behavior from web browsers now available in VS Code
- **Accessibility:** Alternative navigation method for users who prefer mouse-based scrolling
- **Efficiency:** Quick way to navigate through large files without using scroll bars
- **Target Users:** All VS Code users with a mouse, especially those working with large files
- **Status:** Optional feature that must be enabled via settings

## 3. Feature Details

### 3.1 Prerequisites

- Required VS Code version: `1.102+`
- Mouse with middle button (scroll wheel)
- No additional extensions required

### 3.2 How to Enable/Access

- **Settings Path:** `File > Preferences > Settings` (or `Ctrl+,`)
- **Setting Name:** `editor.scrollOnMiddleClick`
- **Default Value:** `false` (disabled by default)
- **Configuration:**

  ```json
  {
    "editor.scrollOnMiddleClick": true
  }
  ```

### 3.3 Step-by-Step Usage

1. **Enable the Feature:**
   - Open Settings (`Ctrl+,` / `Cmd+,`)
   - Search for "scrollOnMiddleClick"
   - Toggle `editor.scrollOnMiddleClick` to `true`

2. **Using Middle Click Scrolling:**
   - Click the middle mouse button (scroll wheel) in the editor
   - Cursor changes to a panning/scrolling icon
   - Move mouse up/down for vertical scrolling
   - Move mouse left/right for horizontal scrolling

3. **Control Scrolling Speed:**
   - Scrolling speed depends on distance from initial click point
   - Further mouse movement = faster scrolling
   - Closer to click point = slower scrolling

4. **Stop Scrolling:**
   - Click middle mouse button again, OR
   - Click any other mouse button to return to normal cursor

### 3.4 Example(s)

- **Simple example:**  
  When editing a long JavaScript file, middle-click in the editor and move your mouse down to smoothly scroll through the function definitions without using the scroll bar.

- **Advanced/tip:**  
  Use horizontal scrolling by moving the mouse left/right after middle-clicking to navigate wide code lines or side-by-side diff views effectively.

**Visual workflow:**

```
1. Middle-click in editor → 🎯 (panning cursor appears)
2. Move mouse down → ⬇️ (smooth vertical scroll)
3. Move mouse right → ➡️ (smooth horizontal scroll)  
4. Middle-click again → ↖️ (normal cursor returns)
```

## 4. Troubleshooting & FAQ

- **Q: The feature doesn't work. What should I check?**
  - A: Ensure `editor.scrollOnMiddleClick` is set to `true` in settings and you're clicking in the editor area (not sidebars).

- **Q: I can't select columns anymore with middle-click. Why?**
  - A: This feature conflicts with column selection. Disable `editor.scrollOnMiddleClick` to restore column selection behavior.

- **Q: Does this work in all VS Code areas?**
  - A: No, it's specific to the text editor. Sidebars, terminals, and other panels may not support this feature.

- **Q: Can I use this alongside other mouse features?**
  - A: Be aware of conflicts with `editor.columnSelection` and `editor.selectionClipboard` on Linux. Enable only one middle-click feature at a time.

**Known Conflicts:**

- **Column Selection:** Disable `editor.columnSelection` if using scroll on middle click
- **Selection Clipboard (Linux):** May conflict with `editor.selectionClipboard` setting
- **Multiple Cursors:** Previous middle-click drag behavior for cursor placement is overridden

## 5. Additional Resources

- Official VS Code release notes: [June 2025 Release Notes](https://code.visualstudio.com/updates/v1_102)
- Related settings: `editor.columnSelection`, `editor.selectionClipboard`
- Alternative navigation: Keyboard shortcuts, scroll bar, minimap navigation

## 6. Revision Log

| Date        | Author    | Change Summary                       |
|-------------|-----------|--------------------------------------|
| 2025-07-26  | AI Agent  | Initial micro-training for Scroll on Middle Click |
