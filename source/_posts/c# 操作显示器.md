---
categories: 
- 编程开发
tags:
- C#
---
#### C#关闭显示器,打开显示器

```c#
 private const uint WM_SYSCOMMAND = 0x0112;
 private const uint SC_MONITORPOWER = 0xF170; 
 [DllImport("user32.dll")]
 public static extern IntPtr SendMessage(IntPtr hWnd, uint msg, uint wParam, int lParam);
 private void button1_Click(object sender, EventArgs e)
 {
     SendMessage(Handle, WM_SYSCOMMAND, SC_MONITORPOWER, 2); //关闭显示器;
     TopMost = true;
     WindowState = FormWindowState.Maximized;   
 }
 private void Form1_MouseMove(object sender, MouseEventArgs e)
 {
     SendMessage(Handle, WM_SYSCOMMAND, SC_MONITORPOWER, -1); //打开显示器;
 }

```

