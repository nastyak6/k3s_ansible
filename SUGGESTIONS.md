# Suggestions

### Project
Good work: the idea was hard to understand, due to mess in the project, yet after trying to understand the project, I was able to make it work.

### README
- Missing link to
  - INSTALL.md
  - CONTRIBUTORS.md
  - TASKS.md

### INSTALL SCRIPT

- Misleading script name for installing k3s from online, not what was required
- Not clear what or which script to use
- k3s-uninstall.sh is not making sense for being in root folder

### ANSIBLE

- inventory.ini is already written state, which may not be an issue but comment in the file is not re-assuring what to do.
- files for roles are just in root folder, which is misleading to understand purpose of the project
- binaries folder holds another binary but not clear for what.
- __instead of emulating the k3s install script, you used the script__, it works and is fine, but what is the point of using ansible if install script is used ?
