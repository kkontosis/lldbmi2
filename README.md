# LLDBMI2 (IntelliJ+D)

A simple MI interface to LLDB customized for [Intellij Plugin for the D Programming Language](https://github.com/intellij-dlanguage/intellij-dlanguage).

# Fork Related Notes

This is a customized version of the original [LLDBMI2](https://github.com/freedib/lldbmi2) that works with IntelliJ IDEA (D).

It helps with debugging the D programming language on Mac OS X, since GDB does not work very easily.

*User Notice*: This fork does not complete or fix the MI2 wrapper. It is a simple patch to facilitate D Debugging with IntelliJ D Language Plugin. Use it at your own risk.

*Developer Notice*: This fork is currently a hack. I may not have the time to ever clean this up.

*Current Status*: 
* Run to Cursor is currently not working.
* Other features may be of unknown status.

The documentation of the original LLDBMI2 follows.

# Context

Since Apple has withdrawn its support for GDB. The options to debug an application with CDT on Mac OS X are:

1. Use Xcode:
  - Natural for Mac OS X, but limited for sharing projects or cross compiling on Linux or Windows.
  - Not adequate for multi language programs (eg: C with Java or Perl).
2. Install GNU GDB:
  - Easy to install from Homebrew or Macports.
  - Does not support Mac OS X dynamic libraries preventing from debugging code inside these libraries.
3. Install LLDB-MI:
  - This program is promising, but is not yet mature.
  - With Eclipse, it must be run in a manual remote debugging session implying to open a shell window and start manually a debug server with the program being debugged as argument (if there is a better way, doc do not mention it).
  - The actual version doesn’t display nor update variables correctly.
  - Many error messages with Eclipse (command arguments nor recognized).
  - The code is complex and not easy to debug for a newcomer.

LLDBMI2 is a lightweight alternative to LLDB-MI on Mac OS X. It allows:
- Debug a local application
- Attach to a running process.

It should be useful for Mac OS x users until LLDB-MI gets enough maturity or when Eclipse will support directly LLDB.

# Limitations
No remote debugging.

No support for Non-stop debugging, Multi-process debugging and Reverse debugging until LLDB support them.

To display arrays of structures, theses structures must be defines with typedef (limitation of DWARF)
